<a id="dev-sanitize"></a>

# Data Sanitization

Data sanitization keeps sensitive data from being exposed when a database is distributed to environments other than the live one, such as a developer’s environment.

The sanitization mechanism lets developers define sanitization rules or raw SQL queries for entities and their fields, then dump those definitions as ready-to-use SQL queries. Run these queries against database copies before distributing them to potentially insecure environments.

#### NOTE
The supported SQL syntax is for PostgreSQL only. The PostgreSQL server will validate the generated SQL queries for syntax errors. No semantic analysis is performed, so the column and table names specified in raw SQL queries are their authors’ responsibility.

## How to Get a Dump of DB Sanitizing SQL Queries

To get a list of sanitizing SQL queries, run the following command:

```bash
php bin/console oro:sanitize:dump-sql
```

This outputs the SQL queries to the console.

To dump directly to a file, pass the file path as a command argument:

```bash
php bin/console oro:sanitize:dump-sql /tmp/sanitize.sql
```

The generated dump will look as follows both in the file and in the console:

```none
-- !!!Exercise caution when using TRUNCATE queries with CASCADE options --
TRUNCATE "acme_blog_post";
DELETE FROM "acme_demo_question" WHERE "created_at" < (NOW() - INTERVAL '5 days');
UPDATE "acme_demo_question" SET "due_date"=CURRENT_TIMESTAMP;
DELETE FROM "acme_demo_sms" WHERE "id" NOT IN(SELECT "id" FROM "acme_demo_sms" ORDER BY "id" DESC LIMIT 3);
UPDATE "acme_demo_sms" SET serialized_data = serialized_data || jsonb_build_object('delivery_date', CURRENT_TIMESTAMP(0));
```

This example truncates the **acme_blog_post** table, reduces the number of records in **acme_demo_question** and **acme_demo_sms**, and hides date information that should not be exposed. It contains only a few queries, which follow the sanitizing configuration described in the [Sanitizing Rules Defined in Files]() and [Sanitizing Rules Defined in the Entity Configuration]() topics below.

The full generated list of SQL queries also includes queries built from configurations defined in the core bundles of the Oro application.

#### NOTE
If the resulting SQL queries contain syntax errors, the customer is notified. Such queries are not written to the file, even if a file is specified; instead, they are output to the console and marked as invalid.

#### NOTE
If there are any errors in the rule configuration caused by incorrect field or entity names, or if a rule is assigned to a field that it cannot process, then the console output will identify the issues and prevent any queries from being executed.

## Sanitizing Rule Sources

You can specify sanitizing rules from two sources.

The first option stores the rule configuration in **sanitize.yml** files, placed in **Resources/config/oro** by convention. The [bundleless](../architecture/bundle-less-structure.md#dev-backend-architecture-bundle-less-structure) approach is also supported here. When several files configure the same entity or field, the last file read takes precedence.

The second option stores the rule configuration within the entity and its field configuration, in a dedicated scope. This approach is harder to maintain, but it ensures the sanitized configuration is fixed. It also takes priority over configuration read from a file.

The file-based approach is easier to maintain and is preferable in most cases. It is also the only option when the database table is not bound to an entity.

### Sanitizing Rules Defined in Files

*src/Acme/Bundle/DemoBundle/Resources/config/oro/sanitize.yml*
```yaml
oro_sanitize:
    raw_sqls:
        - '-- Sample comment as unbound raw SQL'
    entity:
        acme_blog_post: truncate
        # example of specifying an entity class
        Acme\Bundle\DemoBundle\Entity\Document:
            fields:
                subject: 
                    rule: md5
                    rule_options:
                        length: 10
                # example of specifying a field name but not a column name
                dueDate: date
        acme_demo_question:
            raw_sqls:
                - DELETE FROM "acme_demo_question" WHERE "created_at" < (NOW() - INTERVAL '5 days')
            fields:
                subject:
                    raw_sqls:
                        - 'UPDATE "acme_demo_question" SET "subject"=SUBSTRING(MD5("subject" || RANDOM()::TEXT) FROM 1 FOR 10)'
                due_date: date
        acme_demo_sms:
            rule: keep_last_rows
            rule_options:
                rows_count: 3
            fields:
                message: str_reverse
```

The **raw_sqls** node under the **oro_sanitize** node lists sanitizing SQL queries that are not bound to any entity or field.

Items keyed by entity class or table name go under the **entity** node. Each item can have its own **raw_sqls** items, rule definition, and **fields** section. An item can also be a single string value that defines the sanitizing rule, which is equivalent to setting a **rule** value. At least one of **raw_sqls**, **rule**, or **fields** must be set.

The **fields** items are keyed by field or column name. A field element is almost identical to an entity element: it has **raw_sqls** items and a rule definition, and it can also be a single string value that defines the sanitizing rule (equivalent to setting a **rule** value). At least one of **raw_sqls** or **rule** must be set.

The **rule** values are checked against the list of registered rule processors, for both entities and fields.

#### NOTE
If a file sets the **rule** or **raw_sqls** configuration for an entity or field that another file has already configured, the new configuration overwrites the old one.

### Sanitizing Rules Defined in the Entity Configuration

This can be done through schema migration or by defining rules in the entity’s configuration annotation.

Example of adding sanitizing rules to the entity configuration via migration:

*src/Acme/Bundle/DemoBundle/Migrations/Schema/v1_12/AddFieldsWithSanitizingRulesMigration.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Migrations\Schema\v1_12;

use Acme\Bundle\DemoBundle\Entity\Sms;
use Doctrine\DBAL\Schema\Schema;
use Oro\Bundle\EntityConfigBundle\Migration\UpdateEntityConfigFieldValueQuery;
use Oro\Bundle\EntityExtendBundle\EntityConfig\ExtendScope;
use Oro\Bundle\EntitySerializedFieldsBundle\Migration\Extension\SerializedFieldsExtension;
use Oro\Bundle\EntitySerializedFieldsBundle\Migration\Extension\SerializedFieldsExtensionAwareInterface;
use Oro\Bundle\MigrationBundle\Migration\Migration;
use Oro\Bundle\MigrationBundle\Migration\QueryBag;

class AddFieldsWithSanitizingRulesMigration implements Migration, SerializedFieldsExtensionAwareInterface
{
    protected SerializedFieldsExtension $serializedFieldsExtension;

    /**
     * @inheritDoc
     */
    public function setSerializedFieldsExtension(SerializedFieldsExtension $serializedFieldsExtension)
    {
        $this->serializedFieldsExtension = $serializedFieldsExtension;
    }

    /**
     * @inheritDoc
     */
    public function up(Schema $schema, QueryBag $queries)
    {
        $table = $schema->getTable('acme_demo_sms');
        // adding new field as extended one with sanitzing options
        $table->addColumn(
            'moderation_notes',
            'text',
            [
                'oro_options' => [
                    'extend' => ['is_extend' => true, 'owner' => ExtendScope::OWNER_CUSTOM],
                    // sanitizing rule configuration
                    'sanitize' => [
                        'raw_sqls' => ['UPDATE "acme_demo_sms" SET "moderation_notes"=NULL']
                    ]
                ]
            ]
        );

        // adding new serialized data field with sanitzing options
        $this->serializedFieldsExtension->addSerializedField(
            $table,
            'delivery_date',
            'datetime',
            [
                'extend' => ['owner' => ExtendScope::OWNER_CUSTOM],
                'entity' => ['label' => 'Delivery Date'],
                // sanitizing rule configuration
                'sanitize' => ['rule' => 'date']
            ]
        );

        // adding sanitizing options to existing field
        $queries->addQuery(
            new UpdateEntityConfigFieldValueQuery(Sms::class, 'fromContact', 'sanitize', 'rule','str_reverse')
        );
    }
}
```

This example covers creating new ordinary and serialized fields with a sanitizing configuration, and assigning a sanitizing configuration to an existing field. When a rule requires additional setup, add the **rule_options** as well. Note that when updating an existing field, each configuration value you update requires a separate **UpdateEntityConfigFieldValueQuery** instance.

Example of adding sanitizing rules to a newly created entity using a config annotation:

*src/Acme/Bundle/DemoBundle/Entity/Sms.php*
```php
namespace Acme\Bundle\DemoBundle\Entity;
use Doctrine\ORM\Mapping as ORM;
    // ...
use Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityInterface;
use Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityTrait;
    // ...
/**
 * ORM Entity Sms.
 */
#[ORM\Entity(repositoryClass: 'Acme\Bundle\DemoBundle\Entity\Repository\SmsRepository')]
class Sms implements
    ExtendEntityInterface
{
    // ...
    use ExtendEntityTrait;
    // ...
    #[ORM\Column(name: 'message', type: 'text', nullable: true)]
    #[ConfigField(defaultValues: ['dataaudit' => ['auditable' => true], 'sanitize' => ['rule' => 'str_reverse']])]
    private $message;
    // ...
}
```

#### NOTE
Rules are not applied to relations, but only to scalar fields or serialized ones.

## Predefined Sanitizing Rules

Predefined rule processors for entities:

* **truncate** — builds a table truncation query. The rule has no options.
* **truncate_cascade** — builds a table truncation query with a cascade option. The rule has no options.

Predefined rule processors for fields:

* **date** — builds a query to replace the field value with the current date. The rule can only be applied to the date field. The rule has no options.
* **md5** — builds a query to replace a field value with its own MD5 hash, salted with a random value. The rule can only be applied to the string (text, varchar) field. The rule has the **length** option. If none is specified, then the read length of the field is used.
* **email** — builds a query to replace the email’s server name with either an MD5 hashed server name or a custom server name if specified in the application’s configuration. Additionally, if the primary key value of the DB record is numeric, the query salts the mailbox name with the key. The rule can only be applied to the string (text, varchar) field. The rule has no options.
* **set_null** — builds a query to replace a field value with a null. There are no field-type restrictions. The rule has no option.
* **digits_mask** — builds a query to replace the field value with a **phone** number mask. The mask should look like the following: **1 (800) XXX-XXXX**. The **X** symbol in the mask will be replaced with one of the digits from the random value based on the 10000000 number. The length of the value will correspond to the number of **X** symbols in the mask. The rule can only be applied to the string (text, varchar) field. The rule has a **mask** option, as shown in the example above.
* **generic_phone** — is a special case of a **digits_mask** rule with a predefined mask specified in the application configuration. The rule has no options.

The Oro application settings example for the **email** and **generic_phone** rules:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/app.yml*
```php
oro_sanitize:
    # Custom email domain for the 'email' sanitizing rule
    custom_email_domain: example.com
    # Digits mask for the 'generic_phone' sanitizing rule. The default value is shown
    generic_phone_mask: (XXX) XXX-XXXX
```

## Guessing Field Sanitizing Rules

If a field has no sanitizing rule specified directly, the rule processor’s guessing mechanism tries to find one.

The sanitize functionality comes with the following pre-defined field rule processor guessers:

* Email field guesser. It relies on the field’s type, which must be a string and its name. The name should be either the word **email** itself or part highlighted with camel case or under case. For example, **email**, **emailSecond**, **email_Third**, **new_email**, or **anotherEmail**. The guessed rule processor is **email**.
* Full name parts guesser. These parts are the middle name and last name. It relies on the **middleName** and **lastName** field names and specific interfaces implemented by the processed entity. The guessed rule processor is **md5**.
* Crypted string field guesser. It relies on the **crypted_string** field type, which is commonly used to extend integration data tables. The guessed rule process is **md5**.

## Custom Sanitizing Rule Processor

When sanitizing involves repeating actions, you can implement a custom sanitizing rule processor instead of writing raw SQL queries.

### Custom Entity Sanitizing Rule Processor

An example of the entity rule sanitizing processor is keeping the last added rows.

To define a custom rule processor, add a service that implements **Oro\\Bundle\\SanitizeBundle\\RuleProcessor\\Entity\\ProcessorInterface** and has the **oro_sanitize.entity_rule.processor** tag:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_demo.sanitize.entity_rule.keep_last_processor:
        class: Acme\Bundle\DemoBundle\Sanitize\RuleProcessor\Entity\KeepLastRowsProcessor
        arguments:
            - '@doctrine.dbal.default_connection'
        tags:
            - { name: 'oro_sanitize.entity_rule.processor'}
```

The sanitizing rule implementation:

*src/Acme/Bundle/DemoBundle/Sanitize/RuleProcessor/Entity/KeepLastRowsProcessor.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Sanitize\RuleProcessor\Entity;

use Doctrine\DBAL\Connection;
use Doctrine\ORM\Mapping\ClassMetadata;
use Oro\Bundle\SanitizeBundle\RuleProcessor\Entity\ProcessorInterface;

/**
 * Sanitizing rule processor for an entity that keeps last added rows regarding primary key.
 */
class KeepLastRowsProcessor implements ProcessorInterface
{
    private const KEEP_LAST_ROWS_DEFAULT_COUNT = 10;

    public function __construct(private Connection $connection)
    {
    }

    public static function getProcessorName(): string
    {
        return 'keep_last_rows';
    }

    /**
     * {@inheritdoc}
     */
    public function getSqls(ClassMetadata $metadata, array $sanitizeRuleOptions = []): array
    {
        try {
            $idFieldType = $metadata->getFieldMapping($metadata->getSingleIdentifierFieldName())['type'];
            if (!in_array($idFieldType, ['integer', 'bigint', 'smallint'], true)) {
                throw new \RuntimeException();
            }
        } catch (\Throwable $e) {
            throw new \Exception(spritnf(
                "Could not detect single identifier numeric field name for '%s' entity",
                $metadata->getName()
            ));
        }

        return [sprintf(
            'DELETE FROM %1$s WHERE %2$s NOT IN(SELECT %2$s FROM %1$s ORDER BY %2$s DESC LIMIT %3$s)',
            $this->connection->quoteIdentifier($metadata->getTableName()),
            $this->connection->quoteIdentifier($metadata->getSingleIdentifierFieldName()),
            ((int) ($sanitizeRuleOptions['rows_count'] ?? 0)) ?: self::KEEP_LAST_ROWS_DEFAULT_COUNT
        )];
    }
}
```

An entity sanitizing rule processor must implement the following routines:

* **getProcessorName** (static method) — supplies the name of the processor.
* **getSqls** — returns valid SQL queries for an entity.

### Custom Field Sanitizing Rule Processor

An example of a field rule sanitizing processor is a simple string reverse action.

To define a custom rule processor, add a service that implements **Oro\\Bundle\\SanitizeBundle\\RuleProcessor\\Field\\ProcessorInterface** and has the **oro_sanitize.field_rule.processor** tag:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_demo.sanitize.field_rule.reverse_processor:
        class: Acme\Bundle\DemoBundle\Sanitize\RuleProcessor\Field\ReverseProcessor
        parent: oro_sanitize.field_rule.generic_processor
        tags:
            - { name: 'oro_sanitize.field_rule.processor' }
```

To simplify defining a sanitizing rule processor service, use the parent abstract definition **oro_sanitize.field_rule.generic_processor**, which provides a common setup for dependency injection.

The sanitizing rule implementation:

*src/Acme/Bundle/DemoBundle/Sanitize/RuleProcessor/Field/ReverseProcessor.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Sanitize\RuleProcessor\Field;

use Doctrine\ORM\Mapping\ClassMetadata;
use Oro\Bundle\SanitizeBundle\RuleProcessor\Field\Helper\ProcessorHelper;
use Oro\Bundle\SanitizeBundle\RuleProcessor\Field\JsonBuildPairsPostProcessor;
use Oro\Bundle\SanitizeBundle\RuleProcessor\Field\ProcessorInterface;
use Oro\Bundle\SanitizeBundle\RuleProcessor\Field\SerializeFieldCheckerTrait;

/**
 * Reverse string sanitizing rule processor for a field.
 */
class ReverseProcessor implements ProcessorInterface
{
    use SerializeFieldCheckerTrait;

    public function __construct(
        private JsonBuildPairsPostProcessor $jsonBuildPairsPostProcessor,
        private ProcessorHelper $helper
    ) {
    }

    public static function getProcessorName(): string
    {
        return 'str_reverse';
    }

    public function getIncompatibilityMessages(
        string $fieldName,
        ClassMetadata $metadata,
        array $sanitizeRuleOptions = []
    ): array {
        if (!$this->helper->isStringField($fieldName, $metadata)) {
            return [sprintf(
                ProcessorHelper::NON_DATE_FIELD_PROCESSED,
                $fieldName,
                $metadata->getName(),
                self::getProcessorName()
            )];
        }

        return [];
    }

    /**
     * {@inheritdoc}
     */
    public function getSqls(
        string $fieldName,
        ClassMetadata $metadata,
        array $sanitizeRuleOptions = []
    ): array {
        $quotedColumnName = $this->helper->getQuotedColumnName($fieldName, $metadata);
        return [sprintf(
            "UPDATE %s SET %s=%s",
            $this->helper->quoteIdentifier($metadata->getTableName()),
            $quotedColumnName,
            $this->getUpdateSqlValue($quotedColumnName)
        )];
    }

    protected function doPrepareSerializedFieldUpdate(
        string $fieldName,
        ClassMetadata $metadata,
        array $sanitizeRuleOptions = []
    ): void {
        $updateSqlValue = $this->getUpdateSqlValue(
            sprintf("serialized_data->>%s", $this->helper->quoteString($fieldName))
        );
        $this->jsonBuildPairsPostProcessor
            ->addJsonBuildPairForTable($metadata->getTableName(), $fieldName, $updateSqlValue);
    }

    private function getUpdateSqlValue(string $quotedColumnName): string
    {
        return sprintf('REVERSE(%s)', $quotedColumnName);
    }
}
```

A field sanitizing rule processor must implement the following routines:

* **getProcessorName** (static method) — supplies the name of the processor.
* **getIncompatibilityMessages** — returns information about incompatibilities.
* **prepareSerialisedFieldUpdate** — prepares a valid SQL update part for the serialized field.
* **getSqls** — returns valid SQL queries for scalar fields.

In the example above, the **SerializeFieldCheckerTrait** trait method wraps the **prepareSerialisedFieldUpdate** method. The trait method adds validation to check whether the processed field is serialized. This extra validation is not required; it only guards against misuse of a field rule processor.

You can also reconfigure existing field rule processors using a dedicated wrapping component. Define such processors as follows:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_demo.sanitize.field_rule.toll_free_phone_processor:
        class: Oro\Bundle\SanitizeBundle\RuleProcessor\Field\WrappedProcessor
        arguments:
            - '@Oro\Bundle\SanitizeBundle\RuleProcessor\Field\DigitsMaskProcessor'
        calls:
            - ['setOptions', [{mask: '1 (800) XXX-XXX-XXXX'}]]
        tags:
            - { name: 'oro_sanitize.field_rule.processor', processor_name: 'toll_free_phone' }
```

This example defines the toll-free phone-like random number generator.

Be sure to name the wrapping processor in the **processor_name** tag property instead of calling the discouraged **getProcessorName** method.
