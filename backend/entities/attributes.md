<a id="dev-entities-attributes"></a>

# Attributes Configuration

Attributes allow you to create additional entity fields dynamically. An attribute is a configuration field with an assigned value. Every attribute has a dedicated CRUD and field types, similar to the extend fields. For easier management, attributes can be grouped and nested into attribute families.

## Enabling Attributes for an Entity

You can enable attributes for any extendable and configurable entity by doing the following:

1. Add #[Config] attribute to the class with the ‘attribute’ scope and add key ‘has_attributes’ set to true.
2. Add the **attributeFamily** field with many-to-one relation to `Oro\Bundle\EntityConfigBundle\Attribute\Entity\AttributeFamily`. Make the field configurable, activate import if necessary, and add migration.
3. Implement **AttributeFamilyAwareInterface** and accessors for the **attributeFamily** field.

The following example illustrates enabling attributes for the *Document* entity:

*src/Acme/Bundle/DemoBundle/Entity/Document.php*
```php
/**
 * ORM Entity Document.
 */
#[Config(
    defaultValues: [
        'attribute' => ['has_attributes' => true]
    ]
)]
class Document implements
    AttributeFamilyAwareInterface,
    // ...
{
    // ...
    /**
     * @var AttributeFamily
     */
    #[ORM\ManyToOne(targetEntity: 'Oro\Bundle\EntityConfigBundle\Attribute\Entity\AttributeFamily')]
    #[ORM\JoinColumn(name: 'attribute_family_id', referencedColumnName: 'id', onDelete: 'RESTRICT')]
    #[ConfigField(defaultValues: ['dataaudit' => ['auditable' => false], 'importexport' => ['order' => 10]])]
    protected $attributeFamily;

    /**
     * @param AttributeFamily $attributeFamily
     */
    #[\Override]
    public function setAttributeFamily(AttributeFamily $attributeFamily): self
    {
        $this->attributeFamily = $attributeFamily;

        return $this;
    }

    #[\Override]
    public function getAttributeFamily(): ?AttributeFamily
    {
        return $this->attributeFamily;
    }
}
```

*src/Acme/Bundle/DemoBundle/Migrations/Schema/v1_9/AddAttributeFamilyField.php*
```php
namespace Acme\Bundle\DemoBundle\Migrations\Schema\v1_9;

use Doctrine\DBAL\Schema\Schema;
use Oro\Bundle\MigrationBundle\Migration\Migration;
use Oro\Bundle\MigrationBundle\Migration\QueryBag;

class AddAttributeFamilyField implements Migration
{
    #[\Override]
    public function up(Schema $schema, QueryBag $queries)
    {
        $this->addAttributeFamilyField($schema);
    }

    public function addAttributeFamilyField(Schema $schema)
    {
        $table = $schema->getTable('acme_demo_document');
        $table->addColumn('attribute_family_id', 'integer', ['notnull' => false]);
        $table->addIndex(['attribute_family_id']);

        $table->addForeignKeyConstraint(
            $schema->getTable('oro_attribute_family'),
            ['attribute_family_id'],
            ['id'],
            ['onUpdate' => null, 'onDelete' => 'RESTRICT']
        );
    }
}
```

#### NOTE
Remember to clear cache and update configuration after these changes.

## Creating an Attribute

After enabling attributes for an entity, use routes such as *oro_attribute_index* and *oro_attribute_family_index* to create and manage the attributes. Pass your entity class alias in the route parameters so the controller’s action can identify the entity. The action is unavailable when the alias is missing or invalid, or when no attributes are configured for the entity.

You can add routes to the navigation tree to simplify access, like in the following example:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/navigation.yml*
```yaml
            document_attributes_index:
                label: acme.demo.menu.document_attributes
                route: 'oro_attribute_index'
                route_parameters:
                    alias: 'document'
                extras:
                    routes: ['oro_attribute_*']
            document_attribute_families:
                label: acme.demo.menu.document_attribute_families
                route: 'oro_attribute_family_index'
                route_parameters:
                    alias: 'document'
                extras:
                    routes: ['oro_attribute_family_*']
```

The `oro_attribute_create` route creates a new attribute in two steps.

In step 1, the user provides the attribute code (a unique slug) and the attribute type (string, bigint, select, etc.), which defines the data captured in the next step.

In step 2, the user provides a label to display the attribute on the website (e.g., OroCommerce Web Store) and any other information to capture about the attribute.

The Oro application stores the attribute either as a *serialized field* or as a *table column*. The storage type is selected based on the attribute type (simple types vs. Select and Multi-Select) and on the *Filterable* and *Sortable* settings.

The product attribute storage type is set to *table column* for an attribute with the Select or Multi-Select data type, and for an attribute of any type with the Filterable or Sortable option enabled. This storage type requires a reindex, which the user launches by clicking **Update schema** on the *All Product Attributes* page. This physically creates the field in the table.

#### NOTE
Attributes created by the user are labeled as custom, while attributes created during migrations are labeled as a system. For system attributes, deleting is disabled.

#### WARNING
Schema changes are permanent and cannot be easily rolled back. We recommend that developers back up data before any database schema change if changes have to be rolled back.

### Creating an Attribute Programmatically

#### IMPORTANT
This applies to the Enterprise edition, where an attribute can be organization specific.

Do not set the `field_name` option yourself. Create the field through `Oro\Bundle\EntityConfigProBundle\Form\Handler\CreateUpdateConfigFieldHandler::createFieldModel()` or through the attribute import. Both take the attribute name and derive the field name from it with `FieldConfigHelper::getAttributeUniqueFieldName()`. The organization of the attribute comes from the current security token.

For an organization specific attribute, setting the `field_name` option to the field name of the same field maps the attribute to itself in the entity schema. Saving such a configuration when the schema of the field is updated logs a warning. A global attribute has no generated suffix, so its `field_name` option and its field name are legitimately equal. Use the `oro:entity-config:attribute:fix-field-names` command to repair the configuration that already contains it.

## Attribute Families and Groups

An entity has no direct relation to the attribute. Instead, attributes are bound to the entity through the *AttributeFamily*. You can create a new attribute family for the entity using the *oro_attribute_family_create* route with the corresponding alias.

An *AttributeFamily* contains a collection of *AttributeGroups*. It requires *Code* and *Labels* values and must contain at least one attribute group.

Create attribute groups directly on the family create/edit page by adding a new group to the collection. Each group (a collection element) has a required field, ‘Label’, and a select control for picking one or many attributes previously created for the entity (in a specific class).

You can add attributes to a group, move them from one group to another, and delete them from a group. System attributes are an exception: on deletion, they move to the default group instead.

## Accessing Attribute Values from Code

Use the field name returned by `FieldConfigModel::getFieldName()` for all entity access. Take the attributes from the attribute manager and read the values with the property accessor:

```php
foreach ($this->attributeManager->getAttributesByFamily($family) as $attribute) {
    $value = $this->propertyAccessor->getValue($product, $attribute->getFieldName());
}
```

Write the values the same way, with `PropertyAccessorInterface::setValue()`.

#### WARNING
Access the attribute values as properties, not as methods. Do not compose `get<AttributeName>()` calls: property access is served both for an attribute stored as a table column and for an attribute stored as a serialized field, while method access is not available for a serialized field of a type other than Select and Multi-Select.

#### IMPORTANT
The following applies to the Enterprise edition, where an attribute can be organization specific.

An organization specific attribute has one field per organization, and the field name carries a generated suffix, such as `my_attribute_68bd1a2b3c4d5`. The name that the user entered and that the UI shows, such as `my_attribute`, is stored in the `field_name` option of the `attribute` scope, and the copy of the attribute in every organization shares it. Only the field name is a field on the entity.

Prefer `AttributeManager::getActiveAttributesByClassForOrganization()` so that you get the fields of the current organization rather than the fields of every organization.

When you only have the name that the user entered, for example from an import file, a mapping table, or the configuration, convert it to the field name before you touch the entity with `EntityConfigHelper::getRealAttributeFieldName()`. It returns the name of an active field whose name matches the given one when both are normalized (case and underscores are ignored), such as a global attribute. Otherwise it returns the name of the active field of the organization of the current security token whose `field_name` option holds the given name, and throws an exception when there are several. When nothing matches, it returns the given name unchanged. Without a security token, for example in a console command or a message queue consumer, the organization specific fields are not found:

```php
$fieldName = $this->entityConfigHelper->getRealAttributeFieldName(Product::class, $attributeName);
```

#### NOTE
`AttributeManager::getAttributeByFamilyAndName()` matches on the field name, not on the name stored in the `field_name` option. Passing the latter to it returns `null`.

## Attribute ACL

Attributes provide supplementary logic that helps extend entity fields marked as attributes despite limited access to the entity management.

#### NOTE
Next, you can modify the shape of the Document so that there are several steps when creating the entity. For example, you can use OroProductBundle.
