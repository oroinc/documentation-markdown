<a id="bundle-docs-platform-notification-bundle"></a>

# OroNotificationBundle

<a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/NotificationBundle" target="_blank">OroNotificationBundle</a> extends the OroEmailBundle capabilities and enables the email notification feature in Oro applications. It provides the UI and CLI tool to send and manage email notifications.

## Console Commands

The *oro:maintenance-notification* command sends an email notification to the recipients listed in **System Configuration > General Setup > Email Configuration > Maintenance Notifications > Recipients**.

If the recipient list in the system configuration is left empty, the notification will be sent to all active application users.

```bash
php bin/console oro:maintenance-notification --env=prod
```

The text of the message can be provided either as the value of the `--message` option or it can be read from a text file specified in the –file option:

```bash
php bin/console oro:maintenance-notification --message=<message-text> --env=prod
php bin/console oro:maintenance-notification --file=<path-to-text-file> --env=prod
```

The `--subject` option can be used to override the default subject provided by the configured email template:

```bash
php bin/console oro:maintenance-notification --message=<message> --subject=<subject> --env=prod
```

The `--sender_name` and `--sender_email` options can be used to override the default name and email address of the sender:

```bash
php bin/console oro:maintenance-notification --message=<message> --sender_name=<name> --sender_email=<email> --env=prod
```

## Create Notification Rule

For detailed steps on how to create a notification rule, please see [user documentation](../../../user/back-office/system/emails/notification-rules.md#system-notification-rules).

Contact Emails enables you to check recipients stored in the entity fields marked as Contact Information > Email.

#### HINT
For more information about configuring such fields, see [Create Entity Fields](../../../user/back-office/system/entities/entity-fields/index.md#doc-entity-fields-create).

When you create the rule, specify the events that will create jobs for the consumer to submit emails chosen in the Recipient list group.
Make sure that the consumer is running.

## Extend Additional Associations

To add new associations to Additional Associations group, create a class that implements <a href="https://github.com/oroinc/platform/blob/master/src/Oro/Bundle/NotificationBundle/Provider/AdditionalEmailAssociationProviderInterface.php" target="_blank">AdditionalEmailAssociationProviderInterface</a> and registered in the DI container with the oro_notification.additional_email_association_provider tag.

An example:

1. Create an additional associations provider:
   > ```php
   > namespace Acme\Bundle\DemoBundle\Provider;

   > use Acme\Bundle\DemoBundle\Entity\Some;
   > use Acme\Bundle\DemoBundle\Entity\Target;
   > use Oro\Bundle\NotificationBundle\Provider\AdditionalEmailAssociationProviderInterface;
   > use Symfony\Contracts\Translation\TranslatorInterface;

   > class MyAdditionalEmailAssociationProvider implements AdditionalEmailAssociationProviderInterface
   > {
   >     private TranslatorInterface $translator;

   >     /**
   >      * @param TranslatorInterface $translator
   >      * @return void
   >      */
   >     public function __construct(TranslatorInterface $translator)
   >     {
   >         $this->translator = $translator;
   >     }

   >     /**
   >      * @inheritDoc
   >      */
   >     public function getAssociations(string $entityClass): array
   >     {
   >         if (!is_a($entityClass, Some::class, true)) {
   >             return [];
   >         }

   >         return [
   >             'someAssociation' => [
   >                 'label'        => $this->translator->trans('acme.my_entity.some_association'),
   >                 'target_class' => Target::class
   >             ]
   >         ];
   >     }

   >     /**
   >      * @inheritDoc
   >      */
   >     public function isAssociationSupported($entity, string $associationName): bool
   >     {
   >         return
   >             $entity instanceof Some
   >             && 'someAssociation' === $associationName;
   >     }

   >     /**
   >      * @inheritDoc
   >      */
   >     public function getAssociationValue($entity, string $associationName)
   >     {
   >         // get target entity logic
   >         // return target entity
   >     }
   > }
   > ```
2. Register the provider in the DI container:
   > ```yaml
   > services:
   >     acme.additional_email_association_provider.my:
   >         class: Acme\Bundle\DemoBundle\Provider\MyAdditionalEmailAssociationProvider
   >         public: false
   >         arguments:
   >             - '@translator'
   >         tags:
   >             - { name: oro_notification.additional_email_association_provider }
   > ```

<a id="notification-bundle-event"></a>

## Register an Event to Send Notification Emails

To allow creating [notification rules](../../../user/back-office/system/emails/notification-rules.md#system-notification-rules) for new types of events, register them in the `Resources/config/oro/app.yml` file in your bundle.

*Resources/config/oro/app.yml*
```yaml
oro_notification:
    events:
        - my_custom_event_1
        - my_custom_event_2
```

<!-- Frontend -->
