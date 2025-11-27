<a id="draft-bundle-use-draft"></a>

# How to Use Drafts

This topic describes how to use *draft*.

For example, let’s create a simple bundle using instructions provided in the [How to create a new bundle](../../../backend/extension/create-bundle.md#how-to-create-new-bundle) topic.

Following the steps described below, the released bundle will implement all the functionality provided by DraftBundle.

## Add and Configure an Entity

Create an entity with 2 fields: **title** and **content** and implement the entity from `DraftableInterface`.

| Name    | Type   |
|---------|--------|
| title   | string |
| content | text   |

#### NOTE
For simplicity, use the predefined `DraftableTrait` trait:

```php
<?php

namespace Acme\Bundle\CMSBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Oro\Bundle\DraftBundle\Entity\DraftableInterface;
use Oro\Bundle\DraftBundle\Entity\DraftableTrait;
use Oro\Bundle\EntityBundle\EntityProperty\DatesAwareInterface;
use Oro\Bundle\EntityBundle\EntityProperty\DatesAwareTrait;
use Oro\Bundle\EntityConfigBundle\Metadata\Attribute\Config;
use Oro\Bundle\EntityConfigBundle\Metadata\Attribute\ConfigField;
use Oro\Bundle\UserBundle\Entity\Ownership\UserAwareTrait;

/**
 * Represents Acme Block
 */
#[ORM\Entity]
#[ORM\Table(name: 'acme_cms_block')]
#[Config(
    routeName: 'acme_cms_block_index',
    routeView: 'acme_cms_block_view',
    routeUpdate: 'acme_cms_block_update',
    defaultValues: [
        'entity' => ['icon' => 'fa-book'],
        'ownership' => [
            'owner_type' => 'USER',
            'owner_field_name' => 'owner',
            'owner_column_name' => 'user_owner_id',
            'organization_field_name' => 'organization',
            'organization_column_name' => 'organization_id'
        ],
        'security' => ['type' => 'ACL', 'group_name' => '']
    ]
)]
class Block implements DraftableInterface, DatesAwareInterface
{
    use DraftableTrait;
    use UserAwareTrait;
    use DatesAwareTrait;

    /**
     * @var integer
     */
    #[ORM\Column(name: 'id', type: 'integer')]
    #[ORM\Id]
    #[ORM\GeneratedValue(strategy: 'AUTO')]
    protected $id;

    /**
     * @var string
     */
    #[ORM\Column(type: 'string', nullable: false, length: 255, unique: true)]
    #[ConfigField(defaultValues: ['draft' => ['draftable' => true]])]
    protected $title;

    /**
     * @var string
     */
    #[ORM\Column(type: 'text', nullable: true)]
    #[ConfigField(defaultValues: ['draft' => ['draftable' => true]])]
    protected $content;

    /**
     * @return integer
     */
    public function getId()
    {
        return $this->id;
    }

    /**
     * @return string
     */
    public function getTitle(): ?string
    {
        return $this->title;
    }

    public function setTitle(string $title): Block
    {
        $this->title = $title;

        return $this;
    }

    /**
     * @return string
     */
    public function getContent(): ?string
    {
        return $this->content;
    }

    /**
     * @param string|null $content
     *
     * @return $this
     */
    public function setContent(?string $content): Block
    {
        $this->content = $content;

        return $this;
    }
}
```

Then, add the entity configuration to the **title** and **content** fields. The **draftable** parameter ensures that the field is involved in the draft operation.

Follow the instructions provided in the [Configure Entities](../../../backend/entities/config-entities/index.md#book-entities-entity-configuration) topic.

```php
    /**
     * @var string
     */
    #[ORM\Column(type: 'string', nullable: false, length: 255, unique: true)]
    #[ConfigField(defaultValues: ['draft' => ['draftable' => true]])]
    protected $title;

    /**
     * @var string
     */
    #[ORM\Column(type: 'text', nullable: true)]
    #[ConfigField(defaultValues: ['draft' => ['draftable' => true]])]
    protected $content;
```

#### IMPORTANT
To be able to restrict the entity from using ACL, follow the instructions provided in the [Protect Entities Using ACLs](../../../backend/entities/acls.md#coobook-entities-acl-enable) topic.

Restrictions for drafts have specific peculiarities. For more information, see the [How to use draft ACL](how-to-use-draft-acl.md#draft-bundle-use-draft-acl) topic.

## Create an Installer/Migration

An installer [migration](../../../backend/entities/migration.md#backend-entities-migrations) ensures that upon the application installation, the database will contain the entity with the fields defined within bundle.
Follow the instructions provided in the [How to generate an installer](../../../backend/entities/migration.md#installer-generate) topic for more details.

The fields responsible for the draft must match the interface and have the appropriate types.

| Name             | Type      | Attributes   |
|------------------|-----------|--------------|
| draft_project_id | ManyToOne | nullable     |
| draft_source_id  | ManyToOne | nullable     |
| draft_uuid       | guid      | nullable     |
| draft_owner_id   | ManyToOne | nullable     |

After you complete it, you will have the `installer` with the following content:

```php
<?php

namespace Acme\Bundle\CMSBundle\Migrations\Schema;

use Doctrine\DBAL\Schema\Schema;
use Oro\Bundle\MigrationBundle\Migration\Installation;
use Oro\Bundle\MigrationBundle\Migration\QueryBag;

/**
 * Creates all tables required for Acme CMSBundle.
 */
class AcmeCMSBundleInstaller implements Installation
{
    /**
     * {@inheritdoc}
     */
    public function getMigrationVersion()
    {
        return 'v1_0';
    }

    /**
     * {@inheritdoc}
     */
    public function up(Schema $schema, QueryBag $queries)
    {
        /** Tables updates **/
        $this->createAcmeCmsBlockColumns($schema);

        /** Foreign keys generation **/
        $this->addAcmeCmsBlockForeignKeys($schema);
    }

    private function createAcmeCmsBlockColumns(Schema $schema): void
    {
        $table = $schema->createTable('acme_cms_block');
        $table->addColumn('id', 'integer', ['autoincrement' => true]);
        $table->addColumn('title', 'string', ['length' => 255, 'notnull' => true]);
        $table->addColumn('content', 'text', ['notnull' => false]);
        $table->addColumn('created_at', 'datetime', ['comment' => '(DC2Type:datetime)']);
        $table->addColumn('updated_at', 'datetime', ['comment' => '(DC2Type:datetime)']);
        $table->addColumn('user_owner_id', 'integer', ['notnull' => false]);
        $table->addColumn('organization_id', 'integer', ['notnull' => false]);
        $table->addColumn('draft_project_id', 'integer', ['notnull' => false]);
        $table->addColumn('draft_source_id', 'integer', ['notnull' => false]);
        $table->addColumn('draft_uuid', 'guid', ['notnull' => false]);
        $table->addColumn('draft_owner_id', 'integer', ['notnull' => false]);
        $table->setPrimaryKey(['id']);
        $table->addIndex(['user_owner_id'], 'IDX_11767F6E9EB185F9');
        $table->addIndex(['organization_id'], 'IDX_11767F6E32C8A3DE');
        $table->addIndex(['draft_project_id'], 'IDX_11767F6E29386E37');
        $table->addIndex(['draft_source_id'], 'IDX_11767F6E754B6AC7');
        $table->addIndex(['draft_owner_id'], 'IDX_11767F6EDCA3D9F3');
        $table->addUniqueIndex(['title'], 'UNIQ_11767F6E2B36786B');
    }

    private function addAcmeCmsBlockForeignKeys(Schema $schema): void
    {
        $table = $schema->getTable('acme_cms_block');
        $table->addForeignKeyConstraint(
            $schema->getTable('acme_cms_block'),
            ['draft_source_id'],
            ['id'],
            ['onDelete' => 'CASCADE']
        );
        $table->addForeignKeyConstraint(
            $schema->getTable('oro_draft_project'),
            ['draft_project_id'],
            ['id'],
            ['onDelete' => 'CASCADE']
        );
        $table->addForeignKeyConstraint(
            $schema->getTable('oro_user'),
            ['draft_owner_id'],
            ['id'],
            ['onDelete' => 'CASCADE']
        );
        $table->addForeignKeyConstraint(
            $schema->getTable('oro_user'),
            ['user_owner_id'],
            ['id'],
            ['onDelete' => 'SET NULL', 'onUpdate' => null]
        );
        $table->addForeignKeyConstraint(
            $schema->getTable('oro_organization'),
            ['organization_id'],
            ['id'],
            ['onDelete' => 'SET NULL', 'onUpdate' => null]
        );
    }
}
```

## Create a Controller

To work with draft entities, you must use the controller for the actions of non-draft entities.

For more details on how to create a controller and navigation, see the following guides:

* [Entity controller](../../../backend/entities/crud.md#cookbook-entity-controller)
* [Navigation](../../../backend/navigation/index.md#doc-managing-app-menu)

```php
<?php

namespace Acme\Bundle\CMSBundle\Controller;

use Acme\Bundle\CMSBundle\Entity\Block;
use Acme\Bundle\CMSBundle\Form\Type\BlockType;
use Oro\Bundle\FormBundle\Model\UpdateHandlerFacade;
use Oro\Bundle\SecurityBundle\Attribute\Acl;
use Oro\Bundle\SecurityBundle\Attribute\AclAncestor;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\RedirectResponse;
use Symfony\Component\Routing\Annotation\Route;
use Symfony\Contracts\Translation\TranslatorInterface;

/**
 * Acme CMS Block controller
 */
class BlockController extends AbstractController
{
    #[Route(path: '/', name: 'acme_cms_block_index')]
    #[Template]
    #[AclAncestor('acme_cms_block_view')]
    public function indexAction(): array
    {
        return ['entity_class' => Block::class];
    }

    #[Route(path: '/view/{id}', name: 'acme_cms_block_view', requirements: ['id' => '\d+'])]
    #[Template]
    #[Acl(id: 'acme_cms_block_view', type: 'entity', class: 'Acme\Bundle\CMSBundle\Entity\Block', permission: 'VIEW')]
    public function viewAction(Block $block): array
    {
        return ['entity' => $block];
    }

    #[Route(path: '/create', name: 'acme_cms_block_create')]
    #[Template('@AcmeCMS/Block/update.html.twig')]
    #[Acl(id: 'acme_cms_block_create', type: 'entity', class: 'Acme\Bundle\CMSBundle\Entity\Block', permission: 'CREATE')]
    public function createAction(): array|RedirectResponse
    {
        $block = new Block();

        return $this->update($block);
    }

    #[Route(path: '/update/{id}', name: 'acme_cms_block_update', requirements: ['id' => '\d+'])]
    #[Template]
    #[Acl(id: 'acme_cms_block_update', type: 'entity', class: 'Acme\Bundle\CMSBundle\Entity\Block', permission: 'EDIT')]
    public function updateAction(Block $block): array|RedirectResponse
    {
        return $this->update($block);
    }

    protected function update(Block $block): array|RedirectResponse
    {

        return $this->container->get(UpdateHandlerFacade::class)->handleUpdate(
            $block,
            $this->createForm(BlockType::class, $block),
            $this->container->get(TranslatorInterface::class)->trans('acme.cms.controller.saved.message')
        );
    }

    /**
     * {@inheritDoc}
     */
    public static function getSubscribedServices(): array
    {
        return array_merge(
            parent::getSubscribedServices(),
            [
                UpdateHandlerFacade::class,
                TranslatorInterface::class,
            ]
        );
    }
}
```

#### NOTE
A draft realizes the **DraftKernelListener** class. Listener receives the controller’s original argument, replaces it with a draft, and injects the argument to the controller again. It allows us to use a single entry point for all entities.

## Add a Draft Grid

To manage the entity, we need to create a grid to display original and draft entities. Follow the instructions provided in the [Configure grid](../../../backend/configuration/yaml/datagrids.md#reference-format-datagrids) topic for more details.

1. Create a grid for entities

```php
    acme-cms-block-grid:
        acl_resource: acme_cms_block_view
        options:
            entity_pagination: true
            entityHint: acme.cms.block.entity_label
        source:
            type: orm
            query:
                select:
                    - acme_cms_block.id
                    - acme_cms_block.title
                from:
                    - { table: Acme\Bundle\CMSBundle\Entity\Block, alias: acme_cms_block }
        columns:
            id:
                label: acme.cms.block.id.label
            title:
                label: acme.cms.block.title.label
        properties:
            id: ~
            view_link:
                type:   url
                route:  acme_cms_block_view
                params: [ id ]
        actions:
            view:
                type:          navigate
                label:         oro.grid.action.view
                link:          view_link
                icon:          eye
                acl_resource:  acme_cms_block_view
                rowAction:     true
```

1. Create a grid for draft entities

```php
    acme-cms-block-drafts-grid:
        extends: acme-cms-block-grid
        options:
            entity_pagination: true
            entityHint: acme.cms.block.draft.entity_plural_label
            showDrafts: true
        source:
            query:
                select:
                    - CONCAT(draftOwner.firstName, ' ', draftOwner.lastName) as ownerName
                join:
                    left:
                        - { join: acme_cms_block.draftOwner, alias: draftOwner }
                where:
                    and:
                        - acme_cms_block.draftSource = :draft_source_id
                        - acme_cms_block.draftUuid IS NOT NULL
            bind_parameters:
                - draft_source_id
        columns:
            ownerName:
                label: acme.cms.block.draft.owner.label
```

#### IMPORTANT
Use the `showDrafts` option in the grid configuration.
This parameter is responsible for the enable/disable draft filter.
This configuration changes the behavior of the grid, and the grid only reflects draft entities.

1. Add grid operations to the grid with draft entities

Operations for the draft entities must be configured separately in `action.yml`.

Follow the instructions provided in the [Work with Operations](../../../backend/entities-data-management/actions/index.md#bundle-docs-platform-action-bundle-operations) topic.

```php
    ACME_BLOCK_CREATE_DRAFT:
        extends: CREATE_DRAFT
        entities:
            - Acme\Bundle\CMSBundle\Entity\Block

    ACME_BLOCK_PUBLISH_DRAFT:
        extends: PUBLISH_DRAFT
        entities:
            - Acme\Bundle\CMSBundle\Entity\Block
        datagrids:
            - acme-cms-block-drafts-grid

    ACME_BLOCK_DUPLICATE_DRAFT:
        extends: DUPLICATE_DRAFT
        entities:
            - Acme\Bundle\CMSBundle\Entity\Block
        datagrids:
            - acme-cms-block-drafts-grid

    ACME_BLOCK_UPDATE_DRAFT:
        extends: UPDATE_DRAFT
        datagrids:
            - acme-cms-block-drafts-grid

    ACME_BLOCK_DELETE_DRAFT:
        extends: DELETE_DRAFT
        datagrids:
            - acme-cms-block-drafts-grid
```

## Create a Form Type

Create a form type to handle the draft entity.

Follow the instructions provided in the [The Form Type](../../../backend/entities/crud.md#cookbook-entity-form-type) topic for more details.

```php
<?php

namespace Acme\Bundle\CMSBundle\Form\Type;

use Acme\Bundle\CMSBundle\Entity\Block;
use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\Extension\Core\Type\TextareaType;
use Symfony\Component\Form\Extension\Core\Type\TextType;
use Symfony\Component\Form\FormBuilderInterface;
use Symfony\Component\OptionsResolver\OptionsResolver;

/**
 * Block form type
 */
class BlockType extends AbstractType
{
    public const NAME = 'acme_cms_block';

    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder
            ->add(
                'title',
                TextType::class,
                [
                    'label' => 'Title',
                    'required' => true,
                ]
            )
            ->add(
                'content',
                TextareaType::class,
                [
                    'label' => 'Content',
                    'required' => true,
                ]
            );
    }

    /**
     * {@inheritDoc}
     */
    public function configureOptions(OptionsResolver $resolver)
    {
        $resolver->setDefaults([
            'data_class' => Block::class,
            'csrf_token_id' => 'acme_cms_block',
            'ownership_disabled' => true,
        ]);
    }

    /**
     * @return string
     */
    public function getName()
    {
        return $this->getBlockPrefix();
    }

    /**
     * {@inheritdoc}
     */
    public function getBlockPrefix()
    {
        return self::NAME;
    }
}
```

## Use the Extension

Using the extension, you can change the property value when creating the draft entity. Follow the instructions provided in the [How to use draft extension](how-to-use-draft-extension.md#draft-bundle-use-draft-extension) topic.

Take the following three steps to create an extension:

1. Create a filter
2. Create a matcher
3. Create an extension

### Create a Filter

`Filter` is a class that can modify the property value and be used in conjunction with `Matcher`.

```php
<?php

namespace Acme\Bundle\CMSBundle\Duplicator\Filter;

use Acme\Bundle\CMSBundle\Entity\Block;
use Oro\Component\Duplicator\Filter\Filter;

/**
 * Modifies the value of the title field
 */
class UniqueTitleFilter implements Filter
{
    /**
     * @param Block $object
     * @param string $property
     * @param callable $objectCopier
     */
    public function apply($object, $property, $objectCopier): void
    {
        $resolvedField = sprintf('%s_%s', $object->getTitle(), uniqid());
        $object->setTitle($resolvedField);
    }
}
```

### Create a Matcher

`Matcher` is a class that points to the field that `Filter` can work on. Matcher checks whether the specified field meets the criteria and applies the filter to this field.

```php
<?php

namespace Acme\Bundle\CMSBundle\Duplicator\Matcher;

use Acme\Bundle\CMSBundle\Entity\Block;
use DeepCopy\Matcher\Matcher;

/**
 * Determines that a filter can be applied to the title property only
 */
class BlockTitleMatcher implements Matcher
{
    /**
     * @param Block $object
     * @param string $property
     *
     * @return bool
     */
    public function matches($object, $property): bool
    {
        return 'title' === $property;
    }
}
```

### Create an Extension

`Extension` is a class that combines the logic of `Filter` and `Matcher`.

```php
<?php

namespace Acme\Bundle\CMSBundle\Duplicator\Extension;

use Acme\Bundle\CMSBundle\Duplicator\Filter\UniqueTitleFilter;
use Acme\Bundle\CMSBundle\Duplicator\Matcher\BlockTitleMatcher;
use Acme\Bundle\CMSBundle\Entity\Block;
use DeepCopy\Filter\Filter;
use DeepCopy\Matcher\Matcher;
use Oro\Bundle\DraftBundle\Duplicator\Extension\AbstractDuplicatorExtension;
use Oro\Bundle\DraftBundle\Entity\DraftableInterface;
use Oro\Bundle\DraftBundle\Manager\DraftManager;

/**
 * Responsible for copying behavior of Block type parameter.
 */
class BlockTitleExtension extends AbstractDuplicatorExtension
{
    public function getFilter(): Filter
    {
        return new UniqueTitleFilter();
    }

    public function getMatcher(): Matcher
    {
        return new BlockTitleMatcher();
    }

    public function isSupport(DraftableInterface $source): bool
    {
        return
            $this->getContext()->offsetGet('action') === DraftManager::ACTION_CREATE_DRAFT &&
            $source instanceof Block;
    }
}
```

## Create a Template

Draft entities use the default templates, so you can use them.
To identify a draft entity, you can create a block that shows whether the entity is a draft entity.

Follow the instructions provided in the [Template](../../../frontend/storefront/templates.md#templates-twig) topic.

```php

{% block breadcrumbs %}
    {% import '@OroUI/macros.html.twig' as UI %}
    {{ parent() }}
    {% if entity.draftUuid %}
        <span class="page-title-draft">
            {{ UI.badge('oro.draft.label'|trans, 'tentatively') }}
        </span>
    {% endif %}
{% endblock breadcrumbs %}
```

<!-- Frontend -->
