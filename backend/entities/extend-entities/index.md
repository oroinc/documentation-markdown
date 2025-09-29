<a id="book-entities-extended-entities"></a>

# Extend Entities

Common Doctrine entities have a fixed structure. This means that you cannot add additional
attributes to existing entities. Of course, one can extend an entity class and add additional
fields and associations in the subclass. However, this approach does not work anymore when an entity should be
extended by different modules.

To solve this, you can use the <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityExtendBundle" target="_blank">EntityExtendBundle</a> which offers the following features:

* Dynamically add fields to entities through configuration.
* Users with appropriate permissions can add or remove dynamic fields from entities in the user
  interface without the assistance of a developer.
* Show dynamic fields in views, forms, and grids.
* Support for dynamic relationships between entities.

#### CAUTION
It is not recommended to rely on the existence of dynamic fields in your business logic since
they can be removed by administrative users.

<a id="book-entities-extended-entities-create"></a>

## Create Extended Entities

1. Create the *extend entity* class:
   *src/Acme/DemoBundle/Model/ExtendHotel.php*
   ```php
    namespace Acme\DemoBundle\Model;

    class ExtendHotel
    {
        /**
         * The real implementation of this method is auto generated.
         *
         * IMPORTANT: If the derived class has own constructor it must call parent constructor.
         */
        public function __construct()
        {
        }
    }
   ```

   The class name of an extended entity consists of two parts: Its name always **must** start with
   `Extend`. The suffix (here `Hotel`) must be the name of your entity class.

   The class itself is an empty skeleton. Its actual content will be generated dynamically in the
   application cache.
2. Let the *entity class* extend the *extend entity* class:
   *src/Acme/DemoBundle/Entity/Hotel.php*
   ```php
    namespace Acme\DemoBundle\Entity;

    use Acme\DemoBundle\Model\ExtendHotel;
    use Doctrine\ORM\Mapping as ORM;

    /**
     * @ORM\Entity
     * @ORM\Table(name="acme_hotel")
     */
    class Hotel extends ExtendHotel
    {
        /**
         * @ORM\Id
         * @ORM\Column(type="integer")
         * @ORM\GeneratedValue(strategy="AUTO")
         */
        private $id;

        /**
         * @ORM\Column(type="string", length=255)
         */
        private $name;

        public function getId()
        {
            return $this->id;
        }

        public function getName()
        {
            return $this->name;
        }

        public function setName($name)
        {
            $this->name = $name;
        }
    }
   ```
3. Add new fields using a migration script:
   *src/Acme/DemoBundle/Migrations/Schema/v2_0;*
   ```php
    namespace Acme\DemoBundle\Migrations\Schema\v2_0;

    use Doctrine\DBAL\Schema\Schema;
    use Oro\Bundle\MigrationBundle\Migration\Migration;
    use Oro\Bundle\MigrationBundle\Migration\QueryBag;
    use Oro\Bundle\EntityExtendBundle\EntityConfig\ExtendScope;

    class HotelRankingColumn implements Migration
    {
        /**
         * @inheritdoc
         */
        public function up(Schema $schema, QueryBag $queries)
        {
            $table = $schema->getTable('acme_hotel');
            $table->addColumn(
                'hotel_rating',
                'string',
                ['oro_options' => [
                    'extend' => [
                        'is_extend' => true,
                        'owner' => ExtendScope::OWNER_CUSTOM
                    ],
                    'entity' => ['label' => 'Hotel rating'],
                    'datagrid' => ['is_visible' => false]
                ]]
            );
        }
    }
   ```

   The example above adds a new column `hotel_ranking`. The third parameter configures the column
   as an extended field. The `ExtendScope::OWNER_CUSTOM` owner in the `oro_options` key
   indicates that the column was added dynamically. It will be visible and configurable in the UI.

   Note that this field is neither present in the `Hotel` entity class nor in the
   `ExtendHotel` class in your bundle, but it will only be part of the `ExtendHotel` class that
   will be generated in your application cache.
4. Finally, load the changed configuration using the `oro:entity-extend:update` command:
   ```bash
   php bin/console oro:entity-extend:update
   ```

#### NOTE
You can add, modify and remove custom fields in the UI under *System*/*Entities*/*Entity Management*.

<a id="book-entities-extended-entities-apply-changes"></a>

## Apply Changes

The following command updates the database schema and all related caches to reflect changes made in extended entities:

```bash
php bin/console oro:entity-extend:update
```

The `dry-run` can be used to show changes without applying them, for example:

```bash
php bin/console oro:entity-extend:update --dry-run
```

<a id="book-entities-extended-entities-add-fields"></a>

## Add Entity Fields

You may require to customize the default Oro entities to meet the needs of your application.

Let us customize the Contact entity to store the date when a contact becomes a member of your company’s partner network.
As an illustration, we will use the Contact entity from a custom AppBundle.

To achieve this, add a new field `partnerSince` to store the date and time of when a contact joined your network.
To add the field, create a migration:

*src/AppBundle/Migrations/Schema/v1_0/AddPartnerSinceToContact.php*
```php
 namespace AppBundle\Migrations\Schema\v1_0;

 use Doctrine\DBAL\Schema\Schema;
 use Oro\Bundle\EntityExtendBundle\EntityConfig\ExtendScope;
 use Oro\Bundle\MigrationBundle\Migration\Migration;
 use Oro\Bundle\MigrationBundle\Migration\QueryBag;

 class AddPartnerSinceToContact implements Migration
 {
     public function up(Schema $schema, QueryBag $queries)
     {
         $table = $schema->getTable('contact');
         $table->addColumn('partnerSince', 'datetime', [
             'oro_options' => [
                 'extend' => ['owner' => ExtendScope::OWNER_CUSTOM],
             ],
         ]);
     }
 }
```

#### NOTE
Please note that the entity that you add a new field to must have the `@Config` annotation
and should extend an Extend class:

*src/AppBundle/Entity/Contact.php*
```php
 namespace AppBundle\Entity;

 use Doctrine\ORM\Mapping as ORM;
 use Oro\Bundle\EntityConfigBundle\Metadata\Annotation\Config;
 use AppBundle\Entity\Model\ExtendContact;

 /**
  * @ORM\Entity()
  * @ORM\Table(name="contact")
  * @Config()
  */
 class Contact extends ExtendContact
 {
 }
```

*src/AppBundle/Model/ExtendContact.php*
```php
 namespace AppBundle\Model;

 class ExtendContact
 {
     /**
      * A skeleton method for the getter. You can add it to use autocomplete hints from the IDE.
      * The real implementation of this method is auto generated.
      *
      * @return \DateTime
      */
     public function getPartnerSince()
     {
     }

     /**
      * A skeleton method for the setter. You can add it to use autocomplete hints from the IDE.
      * The real implementation of this method is auto generated.
      */
     public function setPartnerSince(\DateTime $partnerSince)
     {
     }
 }
```

The important part in this migration (which is different from common Doctrine migrations) is the `oro_options` key.
It is passed through the `options` argument of the `addColumn()` method:

```php
:emphasize-lines: 3

// ...
         $table->addColumn('partnerSince', 'datetime', [
             'oro_options' => [
                 'extend' => ['owner' => ExtendScope::OWNER_CUSTOM],
             ],
         ]);
// ...
```

All options nested under this key are handled outside of the usual Doctrine migration workflow.

When the EntityExtendBundle of the OroPlatform finds the `extend` key, it generates an intermediate class
with getters and setters for the defined fields, thus making them accessible from every part of the code.
The intermediate class is generated automatically based on the configured data when the application cache is warmed up.

The `owner` attribute can have the following values:

* `ExtendScope::OWNER_CUSTOM` — The field is user-defined, and the core system should handle how the field appears
  in grids, forms, etc. (if not configured otherwise).
* `ExtendScope::OWNER_SYSTEM`— Nothing is rendered automatically, and the developer must explicitly specify how to
  show the field in different parts of the system (grids, forms, views, etc.).

#### NOTE
You can use the <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityExtendBundle/Migration/OroOptions.php" target="_blank">OroOptions</a> class to build `oro_options`, it can be helpful in some cases.

<a id="book-entities-extended-entities-add-enum-fields"></a>

## Add Entity Option Set Fields

The option set fields can be used to choose one or more options from a predefined set of options.
The [Option Set Fields](enums.md#book-entities-extended-entities-enums) section provides detailed information on
how to add such fields.

<a id="book-entities-extended-entities-add-relationships"></a>

## Add Entity Relationships

Adding relationships between entities is a common but, in some cases, complex task.
The [Extended Associations](associations.md#book-entities-extended-entities-associations)
and [Multi-Target Extended Associations](multi-target-associations.md#book-entities-extended-entities-multi-target-associations)
sections provide detailed information on how to add different kinds of relationships.

<a id="book-entities-extended-entities-custom-form-type-for-fields"></a>

## Define Custom Form Type for Fields

Extended fields are rendered as HTML controls, and control type (text, textarea, number, checkbox, etc) is guessed by
classes implementing <a href="https://github.com/symfony/symfony/blob/4.4/src/Symfony/Component/Form/FormTypeGuesserInterface.php" target="_blank">Symfony\\Component\\Form\\FormTypeGuesserInterface</a>.

In case of extended fields, OroPlatform has three guessers (with decreasing priority):
<a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/EntityBundle/Form/Guesser/FormConfigGuesser.php" target="_blank">FormConfigGuesser</a>, <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/EntityExtendBundle/Form/Guesser/ExtendFieldTypeGuesser.php" target="_blank">ExtendFieldTypeGuesser</a> and <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/EntityBundle/Form/Guesser/DoctrineTypeGuesser.php" target="_blank">DoctrineTypeGuesser</a>.

Each provides guesses, and the best guess is selected based on the guesser’s confidence (low, medium, high, very high).

There are a few ways to define a custom form type for a particular field:

1. Through the compiler pass to add or override the guesser’s mappings:
   > ```php
   > namespace Acme\Bundle\AcmeBundle\DependencyInjection\Compiler;

   > use Symfony\Component\DependencyInjection\Compiler\CompilerPassInterface;
   > use Symfony\Component\DependencyInjection\ContainerBuilder;
   > use Symfony\Component\DependencyInjection\Reference;

   > class AcmeExtendGuesserPass implements CompilerPassInterface
   > {
   >     const GUESSER_SERVICE_KEY = 'oro_entity_extend.form.guesser.extend_field';

   >     /**
   >      * {@inheritdoc}
   >      */
   >     public function process(ContainerBuilder $container)
   >     {
   >         $guesser = $container->findDefinition(self::GUESSER_SERVICE_KEY);
   >         $guesser->addMethodCall(
   >             'addExtendTypeMapping',
   >             ["extend-type", "form-type", [option1: 12, option2: false, ...]]
   >         );
   >     }
   > }
   > ```
2. With a custom guesser that will have higher priority or will provide a guess with the highest confidence value:
   > ```php
   > class CustomTypeGuesser implements FormTypeGuesserInterface
   > {
   >     /**
   >      * {@inheritdoc}
   >      */
   >     public function guessType($className, $property)
   >     {
   >         // some conditions here
   >         if ($className == '...' && $property == '') {
   >             $guessedType = '';
   >             $options = [...];
   >             return new TypeGuess($guessedType, $options, TypeGuess::HIGH_CONFIDENCE);
   >         }

   >         // not guessed
   >         return new ValueGuess(false, ValueGuess::LOW_CONFIDENCE);
   >     }

   >     /**
   >      * {@inheritdoc}
   >      */
   >     public function guessRequired($class, $property)
   >     {
   >         return new ValueGuess(false, ValueGuess::LOW_CONFIDENCE);
   >     }

   >     /**
   >      * {@inheritdoc}
   >      */
   >     public function guessMaxLength($class, $property)
   >     {
   >         return new ValueGuess(null, ValueGuess::LOW_CONFIDENCE);
   >     }

   >     /**
   >      * {@inheritdoc}
   >      */
   >     public function guessPattern($class, $property)
   >     {
   >         return new ValueGuess(null, ValueGuess::LOW_CONFIDENCE);
   >     }
   > }
   > ```
3. Register it in the dependency injection container:
   > ```yaml
   > acme.form.guesser.extend_field:
   >     class: Acme\Bundle\AcmeBundle\Form\Guesser\CustomTypeGuesser
   >     tags:
   >         - { name: form.type_guesser, priority: N }
   > ```

   > Here is an idea of what N should be, the existing guessers have the following priorities:

   > | Guesser                                                                                                                                                                    |   Priority |
   > |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|
   > | <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/EntityBundle/Form/Guesser/FormConfigGuesser.php" target="_blank">FormConfigGuesser</a>                 |         20 |
   > | <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/EntityExtendBundle/Form/Guesser/ExtendFieldTypeGuesser.php" target="_blank">ExtendFieldTypeGuesser</a> |         15 |
   > | <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/EntityBundle/Form/Guesser/DoctrineTypeGuesser.php" target="_blank">DoctrineTypeGuesser</a>             |         10 |

   > Select it according to what you need to achieve.
4. Using annotation to a field or a related entity (if an extended field is an association)
   > ```php
   > /*
   >  * @Config(
   >  *      defaultValues={
   >             ...
   >  *          "form"={
   >  *              "form_type"="Oro\Bundle\UserBundle\Form\Type\UserSelectType",
   >  *              "form_option"="{option1: ..., ...}"
   >  *          }
   >  *      }
   >  * )
   >  */
   > ```

<a id="book-entities-extended-entities-validation-for-fields"></a>

## Validation for Extended Fields

By default, all extended fields are not validated. In general extended fields are rendered as usual forms, the same way as not extended,
but there is a way to define validation constraints for all extended fields by their type.

This is done through the configuration of `oro_entity_extend.validation_loader`:

```yaml
oro_entity_extend.validation_loader:
    class: Oro\Bundle\EntityExtendBundle\Validator\ExtendFieldValidationLoader
    arguments:
        - '@oro_entity_config.provider.extend'
        - '@oro_entity_config.provider.form'
    calls:
        -
            - addConstraints
            -
                - integer
                -
                    - NotNull: ~
                    - Regex:
                        pattern: '/^[\d+]*$/'
                        message: 'This value should contain only numbers.'

        - [addConstraints, ['boolean', [{ NotBlank: ~ }]]]
```

There are two ways to pass the constraints :

* use a compiler pass to add the ‘addConstraints’ call with the necessary constraint configuration
* directly call the service

Keep in mind that all constraints defined here are applied to all extended fields with a corresponding type.

<a id="book-entities-extended-entities-extend-fields-view"></a>

## Extending Rendering of Extended Fields

Before extending field rendering on the view page, event `oro.entity_extend_event.before_value_render` is fired.
Using this event, you can customize field rendering.

As example of an event listener registration:

```yaml
oro_entity_extend.listener.extend_field_value_render:
    class: Oro\Bundle\EntityExtendBundle\EventListener\ExtendFieldValueRenderListener
    arguments:
        - '@oro_entity_config.config_manager'
        - '@router'
        - '@oro_entity_extend.extend.field_type_helper'
        - '@doctrine.orm.entity_manager'
    tags:
        - { name: kernel.event_listener, event: oro.entity_extend_event.before_value_render, method: beforeValueRender }
```

Each event listener tries to made a decision on how we need to show the field value and if it knows how  the value needs to be shown,
: it uses `$event->setFieldViewValue($viewData);` to change the field view value.  Example:

```php
$underlyingFieldType = $this->fieldTypeHelper->getUnderlyingType($type);
    if ($value && $underlyingFieldType == 'manyToOne') {
        $viewData = $this->getValueForManyToOne(
            $value,
            $this->extendProvider->getConfigById($event->getFieldConfigId())
        );

        $event->setFieldViewValue($viewData);
    }
```

In this code we:

* check if the value is not null and the field type is “manyToOne”.
* calculate the field view value and set it by calling `$event->setFieldViewValue($viewData);`

Variable `$viewData` can have a simple string or an array `['link' => 'example.com', 'title' => 'some text representation']`.
In case of a string, it will be formatted in a twig template automatically based on the field type. In case of an array, we show a
field with text equal to `'title'`. Title will also be escaped. If `'link'` option exists, we show the field as a link
with href that equals the `'link'` option value.

## Console Commands

* Clear cache.

  Use the `oro:entity-extend:cache:clear` command to clear extended entity cache.
  ```none
  php bin/console oro:entity-extend:cache:clear
  ```
* Skip warming up cache.

  Use the `--no-warmup` option to skip warming up the cache after cleaning:
  > ```none
  > php bin/console oro:entity-extend:cache:clear --no-warmup
  > ```
* Warm up cache.

  Use the `oro:entity-extend:cache:warmup` command to warms up extended entity cache and its related caches (Doctrine metadata, Doctrine proxy classes for extended entities, cache of entity aliases).
  ```none
  php bin/console oro:entity-extend:cache:warmup
  ```

  The `--cache-dir` option can be used to override the default cache directory location.
  ```none
  php bin/console oro:entity-extend:cache:warmup --cache-dir=<path>
  ```
* Update schema.

  Use the `oro:entity-extend:update-schema` command to updates database schema for extend entities.
  ```none
  php bin/console oro:entity-extend:update-schema
  ```

  The –dry-run option can be used to print the changes without applying them:
  ```none
  php bin/console oro:entity-extend:update --dry-run
  ```

#### BUSINESS TIP
## Business Tip

Looking for a way to leverage online commerce? Here’s everything you need to know about a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B online marketplace</a> and what makes it work.

* [Option Set Fields](enums.md)
* [Extended Associations](associations.md)
* [Multi-Target Extended Associations](multi-target-associations.md)
* [Serialized Fields](serialized-fields.md)

<!-- Frontend -->
