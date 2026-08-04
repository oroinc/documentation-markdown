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
    public function setAttributeFamily(AttributeFamily $attributeFamily): self
    {
        $this->attributeFamily = $attributeFamily;

        return $this;
    }

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
    /**
     * {@inheritdoc}
     */
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

## Attribute Families and Groups

An entity has no direct relation to the attribute. Instead, attributes are bound to the entity through the *AttributeFamily*. You can create a new attribute family for the entity using the *oro_attribute_family_create* route with the corresponding alias.

An *AttributeFamily* contains a collection of *AttributeGroups*. It requires *Code* and *Labels* values and must contain at least one attribute group.

Create attribute groups directly on the family create/edit page by adding a new group to the collection. Each group (a collection element) has a required field, ‘Label’, and a select control for picking one or many attributes previously created for the entity (in a specific class).

You can add attributes to a group, move them from one group to another, and delete them from a group. System attributes are an exception: on deletion, they move to the default group instead.

## Attribute ACL

Attributes provide supplementary logic that helps extend entity fields marked as attributes despite limited access to the entity management.

#### NOTE
Next, you can modify the shape of the Document so that there are several steps when creating the entity. For example, you can use OroProductBundle.
