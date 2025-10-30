# Public and Private Emails

During synchronization of email boxes, there are a set of emails that belongs to the business entities, such as
to the Contact or Lead, and not belongs to them, for example, the correspondence between two users.

There are two types of emails in the system. The first type includes emails with addresses tied to business entities, such as contacts, leads. The second type includes the rest, such as correspondence between two users in the system.

Public and private emails were introduced to process access to these two different  types of emails.

A public email is an email where at least one of the addresses used by recipients or senders is public.
In other cases, the email is considered private.

The `public email address` is an address that belongs to public email owners, not private owners. If a public and a private owner use the same email address, then this email address will be considered private.

The default list of public email owner entities:

- <a href="https://github.com/oroinc/crm/tree/6.1/src/Oro/Bundle/ContactBundle/Entity/Contact.php" target="_blank">Contact entity</a>
- <a href="https://github.com/oroinc/crm/tree/6.1/src/Oro/Bundle/SalesBundle/Entity/Lead.php" target="_blank">Lead entity</a>
- <a href="https://github.com/oroinc/customer-portal/tree/6.1/src/Oro/Bundle/CustomerBundle/Entity/CustomerUser.php" target="_blank">Customer User entity</a>
- <a href="https://github.com/oroinc/orocommerce/tree/6.1/src/OroBundle/RFPBundle/Entity/Request.php" target="_blank">RFP Request entity</a>

The default list of private email owner entities:

- <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UserBundle/Entity/User.php" target="_blank">User entity</a>
- <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/EmailBundle/Entity/Mailbox.php" target="_blank">Mailbox entity</a>

## ACL Restrictions of Public and Private Emails

To separate limit access to the public and private emails, use the following permissions for the User Emails entity:

* `View` to limit access to public emails.
* `View Private` to limit access to private emails.

By default, all roles except the Administrator role have the `NONE` access level to the `View Private` permission. This means that only
an administrator can view private emails by default.

#### NOTE
Private emails are not be displayed on the activity lists regardless of the access level set for the `View Private` permission.

## Add Entity as Public Email Address Owner

To make an entity a public owner:

1. Make sure that the entity is an email owner
2. Mark the desired entity as public in the `public_email_owners` section of the email bundle config.

For more information on how to make an entity an email owner, see the [Email Address Owners](emails.md#id1) topic.

The following example shows how to make a User entity a Public Owner:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/app.yml*
```yaml
 oro_email:
   public_email_owners:
     - Oro\Bundle\UserBundle\Entity\User
```

Next, update the existing emails data with the new configuration using the `oro:email:update-visibilities` console command:

```bash
php bin/console oro:email:update-visibilities
```

This command sends a Message Queue message to update visibility for emails.

<!-- Frontend -->
