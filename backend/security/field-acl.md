<a id="backend-security-bundle-field-acl"></a>

# Field ACL

Field ACL allows checking access to an entity field and supports the following permissions: **VIEW, CREATE, EDIT**.

## Prepare the System for Field ACL

By default, entity fields are not protected by ACL. The templates, datagrids, and other parts of the system that use the entity do not perform such checks.

Before you enable Field ACL for an entity, prepare the system parts that use the entity to check it.

## Check Field ACL in PHP Code

In PHP code, the isGranted method of the security.authorization_checker service checks access to the field.

The second parameter of this method should be an instance of <a href="https://github.com/symfony/security-acl/blob/master/Voter/FieldVote.php" target="_blank">FieldVote</a>:

*src/Acme/Bundle/DemoBundle/Controller/FavoriteController.php*
```php
    #[Route(path: '/new-edit', name: 'new_edit')]
    #[Template('@AcmeDemo/Favorite/index.html.twig')]
    #[AclAncestor('acme_demo_favorite_new_edit')]
    public function newEditAction()
    {
        $entity = $this->getUser();
        if (!$this->isGranted('VIEW', $entity)) {
            throw new AccessDeniedException();
        }
        // check access to the given entity field
        $authorizationChecker = $this->container->get('security.authorization_checker');
        if (!$authorizationChecker->isGranted('VIEW', new FieldVote($entity, '_field_name_'))) {
            throw new AccessDeniedException('Access denied');
        }

        return ['entity_class' => Favorite::class];
    }
```

As a result, the $isGranted variable is *true* if access is granted and *false* otherwise.

The $entity parameter should contain an instance of the entity you want to check.

If you have no entity instance but know the class name, the record ID, the owner ID, and the organization ID of this record, you can use the <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/SecurityBundle/Acl/Domain/DomainObjectReference.php" target="_blank">DomainObjectReference</a> as the domain object:

```php
// ....
use Oro\Bundle\SecurityBundle\Acl\Domain\DomainObjectReference;
use Symfony\Component\Security\Core\Authorization\AuthorizationCheckerInterface;
use Symfony\Component\Security\Acl\Voter\FieldVote;
// ...

$entityReference = new DomainObjectReference($entityClassName, $entityId, $ownerId, $organizationId);
$isGranted = $this->authorizationChecker->isGranted('VIEW', new FieldVote($entityReference, 'fieldName'));
```

## Check Field ACL in TWIG Templates

Use the is_granted twig function to check grants in twig templates. To check the field, use the field name as the third parameter of the function:

```php
{% if is_granted('VIEW', entity, 'fieldName') %}
    {# do some job #}
{% endif %}
```

<a id="backend-security-bundle-field-acl-enable-support"></a>

## Enable Support of Field ACL for an Entity

To manage field ACL, add the field_acl_supported attribute to the ‘security’ scope of the entity config.

This attribute tells the system it is prepared to check access to the entity fields.

You can achieve this with the Config annotation if you have access to both the entity and the process oro:platform:update command.

The following example illustrates the entity configuration:

*src/Acme/Bundle/DemoBundle/Entity/Favorite.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Oro\Bundle\EntityBundle\EntityProperty\DatesAwareInterface;
use Oro\Bundle\EntityBundle\EntityProperty\DatesAwareTrait;
use Oro\Bundle\EntityConfigBundle\Metadata\Attribute\Config;
use Oro\Bundle\EntityConfigBundle\Metadata\Attribute\ConfigField;
use Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityInterface;
use Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityTrait;
use Oro\Bundle\OrganizationBundle\Entity\OrganizationAwareInterface;
use Oro\Bundle\UserBundle\Entity\Ownership\AuditableUserAwareTrait;

/**
 * ORM Entity Favorite.
 */
#[ORM\Entity(repositoryClass: 'Acme\Bundle\DemoBundle\Entity\Repository\FavoriteRepository')]
#[ORM\Table(name: 'acme_demo_favorite')]
#[Config(
    defaultValues: [
        'ownership' => [
            'owner_type' => 'USER',
            'owner_field_name' => 'owner',
            'owner_column_name' => 'user_owner_id',
            'organization_field_name' => 'organization',
            'organization_column_name' => 'organization_id'
        ],
        'grid' => ['default' => 'acme-demo-favorite-grid'],
        'security' => ['type' => 'ACL', 'permissions' => 'All', 'group_name' => '', 'category' => ''],
        'dataaudit' => ['auditable' => true]
    ]
)]
class Favorite implements
    DatesAwareInterface,
    OrganizationAwareInterface,
    ExtendEntityInterface
{
}
```

If you cannot modify the Config annotation on the entity, set the field_acl_supported parameter with a migration:

*src/Acme/Bundle/DemoBundle/Migrations/Schema/v1_8/TurnFieldAclSupportForFavorites.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Migrations\Schema\v1_8;

use Doctrine\DBAL\Schema\Schema;
use Oro\Bundle\EntityConfigBundle\Migration\UpdateEntityConfigEntityValueQuery;
use Oro\Bundle\MigrationBundle\Migration\Migration;
use Oro\Bundle\MigrationBundle\Migration\QueryBag;

/**
 * Turn field acl supported for Favorites.
 */
class TurnFieldAclSupportForFavorites implements Migration
{
    #[\Override]
    public function up(Schema $schema, QueryBag $queries): void
    {
        $queries->addQuery(
            new UpdateEntityConfigEntityValueQuery(
                'Acme\Bundle\DemoBundle\Entity\Favorite',
                'security',
                'field_acl_supported',
                true
            )
        );
    }
}
```

## Enable Field ACL

Once the configuration is changed, the entity config page has two additional parameters: Field Level ACL and Show Restricted.

#### NOTE
Please do not enable these parameters from the code without enabling the field_acl_supported attribute for the entity.

With the Field Level ACL parameter, the system manager can enable or disable Field ACL for the entity.

When both the *Show Restricted* and *Field ACL* options are enabled but a user lacks access to the field, the field appears in read-only format on the create and edit pages.

## Limit Permissions List

A developer can limit the available permissions for the field with the permissions parameter in the Security scope.

List the permissions as a string with the ; delimiter.

For example:

*src/Acme/Bundle/DemoBundle/Entity/Favorite.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Entity;

use Doctrine\ORM\Mapping as ORM;
use Oro\Bundle\EntityBundle\EntityProperty\DatesAwareInterface;
use Oro\Bundle\EntityBundle\EntityProperty\DatesAwareTrait;
use Oro\Bundle\EntityConfigBundle\Metadata\Attribute\Config;
use Oro\Bundle\EntityConfigBundle\Metadata\Attribute\ConfigField;
use Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityInterface;
use Oro\Bundle\EntityExtendBundle\Entity\ExtendEntityTrait;
use Oro\Bundle\OrganizationBundle\Entity\OrganizationAwareInterface;
use Oro\Bundle\UserBundle\Entity\Ownership\AuditableUserAwareTrait;

/**
 * ORM Entity Favorite.
 */
#[ORM\Entity(repositoryClass: 'Acme\Bundle\DemoBundle\Entity\Repository\FavoriteRepository')]
#[ORM\Table(name: 'acme_demo_favorite')]
#[Config(
    defaultValues: [
        'ownership' => [
            'owner_type' => 'USER',
            'owner_field_name' => 'owner',
            'owner_column_name' => 'user_owner_id',
            'organization_field_name' => 'organization',
            'organization_column_name' => 'organization_id'
        ],
        'grid' => ['default' => 'acme-demo-favorite-grid'],
        'security' => ['type' => 'ACL', 'permissions' => 'All', 'group_name' => '', 'category' => ''],
        'dataaudit' => ['auditable' => true]
    ]
)]
class Favorite implements
    DatesAwareInterface,
    OrganizationAwareInterface,
    ExtendEntityInterface
{
    #[ORM\Column(name: 'viewCount', type: 'integer', nullable: true)]
    #[ConfigField(defaultValues: ['security' => ['permissions' => 'VIEW;CREATE']])]
    private $viewCount;
}
```

<!-- Frontend -->
