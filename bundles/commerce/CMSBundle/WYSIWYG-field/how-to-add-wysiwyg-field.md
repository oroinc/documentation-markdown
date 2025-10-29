<a id="how-to-add-wysiwyg-field"></a>

# How to Add WYSIWYG Field

There are two ways to add a WYSIWYG field - via the Entity Management UI and programmatically.

<a id="how-to-add-wysiwyg-field-via-ui"></a>

## Add a WYSIWYG Field via Entity Management UI

To add a WYSIWYG field via the Entity Management UI:

1. Create [an extended entity field](../../../../user/back-office/system/entities/entity-fields/index.md#doc-entity-fields-create) of the WYSIWYG type.
2. The system manages the WYSIWYG fields similarly to all other extended fields, considering the `Show on Form` and `Show on View` entity field config options.

For example, if you add a WYSIWYG field called `teaser` to an entity, the system automatically creates the `teaser_style` and `teaser_properties` fields. Entity getters and setters of these fields will be `getTeaserStyle`/`setTeaserStyle` and `getTeaserProperties`/`setTeaserProperties` correspondingly.

<a id="how-to-add-wysiwyg-field-programmatically"></a>

## Add a WYSIWYG Field Programmatically

You can add a WYSIWYG field programmatically in two ways:

1. [As an extended field](#how-to-add-wysiwyg-field-programmatically-as-extended) if the target entity class cannot be modified. Use the option if you add the field to the default Oro entity or any other entity provided by a vendor.
2. [Explicitly](#how-to-add-wysiwyg-field-programmatically-explicitly) if the target entity class can be modified. Use the option if you want to create and manage the WYSIWYG field, and have a total control over its validation and representation.

<a id="how-to-add-wysiwyg-field-programmatically-as-extended"></a>

### Add a WYSIWYG Field as Extended Field

In terms of the final outcome, this way is similar to [adding a field via the entity management UI](#how-to-add-wysiwyg-field-via-ui), as the system is responsible for the WYSIWYG field management, its validation, and representation.

To add a WYSIWYG field as an [extended field](../../../../backend/entities/extend-entities/index.md#book-entities-extended-entities-add-fields):

1. Create a migration that adds 3 columns of the following types: `wysiwyg`, `wysiwyg_style`, and `wysiwyg_properties`.

```php
<?php

namespace Acme\Bundle\WysiwygBundle\Migrations\Schema\v1_1;

use Doctrine\DBAL\Schema\Schema;
use Oro\Bundle\EntityConfigBundle\Entity\ConfigModel;
use Oro\Bundle\EntityExtendBundle\EntityConfig\ExtendScope;
use Oro\Bundle\EntityExtendBundle\Migration\ExtendOptionsManager;
use Oro\Bundle\EntityExtendBundle\Migration\OroOptions;
use Oro\Bundle\MigrationBundle\Migration\Migration;
use Oro\Bundle\MigrationBundle\Migration\QueryBag;

class AddTeaserField implements Migration
{
    #[\Override]
    public function up(Schema $schema, QueryBag $queries): void
    {
        if (!$schema->hasTable('acme_blog_post')) {
            return;
        }

        $table = $schema->getTable('acme_blog_post');
        if ($table->hasColumn('teaser')) {
            return;
        }

        $table->addColumn('teaser', 'wysiwyg', [
            'notnull' => false,
            'comment' => '(DC2Type:wysiwyg)',
            OroOptions::KEY => [
                'extend' => ['is_extend' => true, 'owner' => ExtendScope::OWNER_CUSTOM],
                'entity' => ['label' => 'acme.wysiwyg.blogpost.teaser.label'],
            ],
        ]);
        $table->addColumn(
            'teaser_style',
            'wysiwyg_style',
            [
                'notnull' => false,
                OroOptions::KEY => [
                    ExtendOptionsManager::MODE_OPTION => ConfigModel::MODE_HIDDEN,
                    'extend' => ['is_extend' => true, 'owner' => ExtendScope::OWNER_CUSTOM],
                ],
            ]
        );
        $table->addColumn(
            'teaser_properties',
            'wysiwyg_properties',
            [
                'notnull' => false,
                OroOptions::KEY => [
                    ExtendOptionsManager::MODE_OPTION => ConfigModel::MODE_HIDDEN,
                    'extend' => ['is_extend' => true, 'owner' => ExtendScope::OWNER_CUSTOM],
                ],
            ]
        );
    }
}
```

2. Entity getters and setters are generated automatically: `getTeaser/setTeaser`, `getTeaserStyle`/`setTeaserStyle`,
`getTeaserProperties`/`setTeaserProperties`.

#### NOTE
You can add an extended field to the Product entity as a product attribute during the schema migration. For that, set the `attribute.is_attribute` entity field config option to `true` in the Oro options of the field column.

<a id="how-to-add-wysiwyg-field-programmatically-explicitly"></a>

### Add a WYSIWYG Field Explicitly

To add a WYSIWYG field explicitly:

1. Create a migration that adds 3 columns of the following types: `wysiwyg`, `wysiwyg_style`, and `wysiwyg_properties`:

```php
<?php

namespace Acme\Bundle\WysiwygBundle\Migrations\Schema\v1_1;

use Doctrine\DBAL\Schema\Schema;
use Oro\Bundle\MigrationBundle\Migration\Migration;
use Oro\Bundle\MigrationBundle\Migration\QueryBag;

class AddExtraContentField implements Migration
{
    #[\Override]
    public function up(Schema $schema, QueryBag $queries): void
    {
        if (!$schema->hasTable('acme_blog_post')) {
            return;
        }

        $table = $schema->getTable('acme_blog_post');
        if ($table->hasColumn('extra_content')) {
            return;
        }

        $table->addColumn('extra_content', 'wysiwyg', ['notnull' => false, 'comment' => '(DC2Type:wysiwyg)']);
        $table->addColumn('extra_content_style', 'wysiwyg_style', ['notnull' => false]);
        $table->addColumn('extra_content_properties', 'wysiwyg_properties', ['notnull' => false]);
    }
}
```

1. Add the corresponding properties, getters, and setters to the target entity class:

*src/Acme/WysiwygBundle/Entity/BlogPost.php*
```php
class BlogPost implements DatesAwareInterface, ExtendEntityInterface
{
    // ...

    #[ORM\Column(name: 'extra_content', type: 'wysiwyg', nullable: true)]
    #[ConfigField(defaultValues: ['attachment' => ['acl_protected' => false]])]
    protected $extraContent;

    #[ORM\Column(name: 'extra_content_style', type: 'wysiwyg_style', nullable: true)]
    #[ConfigField(defaultValues: ['attachment' => ['acl_protected' => false]])]
    protected $extraContentStyle;

    #[ORM\Column(name: 'extra_content_properties', type: 'wysiwyg_properties', nullable: true)]
    protected $extraContentProperties;

    public function getExtraContent(): ?string
    {
        return $this->extraContent;
    }

    public function setExtraContent(?string $extraContent): self
    {
        $this->extraContent = $extraContent;

        return $this;
    }

    public function getExtraContentStyle(): ?string
    {
        return $this->extraContentStyle;
    }

    public function setExtraContentStyle(?string $extraContentStyle): self
    {
        $this->extraContentStyle = $extraContentStyle;

        return $this;
    }

    public function getExtraContentProperties(): ?array
    {
        return $this->extraContentProperties;
    }

    public function setExtraContentProperties(?array $extraContentProperties): self
    {
        $this->extraContentProperties = $extraContentProperties;

        return $this;
    }

    // ...
}
```

#### NOTE
The entity field config `attachment.acl_protected` is set to `false` to disable ACL for the images and files uploaded     to the WYSIWYG field to make them publicly accessible.

1. Declare validation constraints:

*src/Acme/WysiwygBundle/Resources/config/validation.yml*
```yaml
Acme\Bundle\WysiwygBundle\Entity\BlogPost:
    properties:
        # ...

        extraContent:
            - Oro\Bundle\CMSBundle\Validator\Constraints\TwigContent: ~
            - Oro\Bundle\CMSBundle\Validator\Constraints\WYSIWYG: ~
        extraContentStyle:
            - Oro\Bundle\CMSBundle\Validator\Constraints\TwigContent: ~
            - Oro\Bundle\CMSBundle\Validator\Constraints\WYSIWYG: ~

        # ...
```

For more details on the WYSIWYG field representation, refer to the [How to Display a WYSIWYG Field](how-to-display-wysiwyg-field.md#how-to-display-wysiwyg-field) topic.

<!-- Frontend -->
