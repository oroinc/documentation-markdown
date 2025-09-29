<a id="backend-security-bundle-introduction"></a>

# Introduction to Security in Oro Applications

The [OroSecurityBundle](../../bundles/platform/SecurityBundle/index.md#bundle-docs-platform-security-bundle) sits on top of the Symfony security layer to reach protect your resources.
This means that each user of your application is granted access to a particular subset of your
company’s resources. Coincidentally, they have to be prevented from accessing resources, access was
not granted to them.

<a id="backend-security-bundle-access-control-list"></a>

## Access Control Lists

Access Control Lists are an essential part of the <a href="https://symfony.com/doc/4.4/components/security.html" target="_blank">Symfony Security Components</a>. They are leveraged
by the OroSecurityBundle to fulfill the requirements of companies in the business context.

#### HINT
You can find detailed information about Symfony ACL based security model in the Symfony documentation:

* <a href="https://symfony.com/doc/4.4/security/acl.html" target="_blank">https://symfony.com/doc/4.4/security/acl.html</a>

### Access Levels

Access can be granted to a user for a certain resource on several levels. The lowest level is
the *User* level. Being on this level means that users can only access resources that have been
assigned to them. At the other end of the hierarchy is the *Global* level. Users at this level have
the permission to access all records within the whole system without exception. The security bundle
comes with the following five levels (ordered up from the bottom of the hierarchy):

| Level           | Constant       | Description                                                                                                                                                                                                                                                                                                                               |
|-----------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *User*          | `BASIC_LEVEL`  | The user is granted access to their own records.                                                                                                                                                                                                                                                                                          |
| *Business Unit* | `LOCAL_LEVEL`  | The user is given access to the records in all<br/>business units they are assigned to.                                                                                                                                                                                                                                                   |
| *Division*      | `DEEP_LEVEL`   | This is the same as the *Business Unit* level except that<br/>the user can also access all resources that are owned by<br/>subordinate units of the business units they are assigned<br/>to.                                                                                                                                              |
| *Organization*  | `GLOBAL_LEVEL` | The user is given access to all records within the<br/>organization, regardless of the business unit the object<br/>belongs to or the user is assigned to.                                                                                                                                                                                |
| *Global*        | `SYSTEM_LEVEL` | The user can access all objects within the system.<br/><br/>#### NOTE<br/>This level is available only in Enterprise<br/>editions. Global access level makes sense if<br/>the user works in the scope of a global<br/>organization. If the user works in the scope<br/>of an ordinary organization, global level<br/>equals organization. |

Each record is associated with an owning organization. When a user logs into the system, they work in
the scope of one of their organizations.

#### NOTE
For all access levels, there is a class constant defined in the Oro\\Bundle\\SecurityBundle\\Acl\\AccessLevel class. Its value is shown in the *Constant* column.

There are two special constants `AccessLevel::UNKNOWN` (unknown access level, should not be
assigned to a user) and `AccessLevel::NONE_LEVEL` (globally deny access for the user).

<a id="permissions"></a>

### Permissions

A user can be assigned different modes to a resource. These modes describe what they are allowed to
do with the resource. Namely, the following permissions are supported for **entities**:

| Permission   |                                                                                                                                                                                               |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `VIEW`       | Whether or not a user is allowed to view a record.                                                                                                                                            |
| `CREATE`     | Whether or not a user is allowed to create a record. The access level set<br/>for this permission limits the number of owners that can be assigned to<br/>a created record.                   |
| `EDIT`       | Whether or not a user is allowed to modify a record.                                                                                                                                          |
| `DELETE`     | Whether or not a user is allowed to delete a record.                                                                                                                                          |
| `ASSIGN`     | Whether or not a user is allowed to assign a record to another user. This<br/>permission is only evaluated when an entity is edited.                                                          |
| `SHARE`      | Whether or not a user is allowed to assign a record to another user.<br/>Only works on entities’ view pages.<br/><br/>#### NOTE<br/>This permission is available only in Enterprise editions. |

#### SEE ALSO
Read the official documentation for a first insight in the <a href="https://github.com/symfony/acl-bundle/blob/master/src/Resources/doc/index.rst" target="_blank">usage of ACLs</a> examples.

The following permissions are supported for **fields**:

| Permission   |                                                     |
|--------------|-----------------------------------------------------|
| `VIEW`       | Whether or not a user is allowed to view a field.   |
| `EDIT`       | Whether or not a user is allowed to modify a field. |

#### Ownership Type

Each ACL-protected entity must have an ownership type. Various entities can act as one, such as user business unit, organization.
If the type of owner is not specified, but the entity is acl-protected, this type is called **None**.
The set of access levels available for permissions of this entity changes depending on the ownership type.

The following table shows what access levels can be assigned depending on the entity’s ownership type:

| Ownership type   | Possible access levels for an entity with this ownership type   |
|------------------|-----------------------------------------------------------------|
| User             | None, User, Business Unit, Division, Organization, Global       |
| Business Unit    | None, Business Unit, Division, Organization, Global             |
| Organization     | None, Organization, Global                                      |
| None             | None, Global                                                    |

Although ownership types uses the same concepts as an access level, their impact is different. For example:

* The **None** ownership type gives the widest access to entity records. It means ‘This record does not belong to any particular organization or business unit or user. Therefore, either all users can access it, or no one at all.’
* The **None** access level completely restricts access to entity records. It says ‘No one can perform this action on the entity’.

Every record of a security protected entity with ownership type User, Business unit and Organization has an organization.

Keep in mind that as soon as the entity is created, its ownership type cannot be changed. Consequently, you cannot change the predefined ownership types of system entities (such as an account or a business unit).

<a id="backend-security-bundle-configure-entities"></a>

## Configuring Permissions for Entities

To be able to protect access to your entities, you first have to configure which permissions
can be granted for a user to them. Use the `security` scope in the `defaultValues` section of
the `@Config` annotation:

```php
/**
 * @Config(
 *  defaultValues={
 *      "security"={
 *          "type"="ACL",
 *          "permissions"="All",
 *          "group_name"="SomeGroup",
 *          "category"="SomeCategory",
 *      }
 *  }
 * )
 */
 class MyEntity
```

#### NOTE
After changing ACL in the Config annotation, run the oro:entity-config:update command in console to apply changes.

The **permissions** parameter is used to specify the access list for the entity. This parameter is optional.
If it is not specified, or is “All”, it is considered that the entity access to all available security permissions.

You can create your list of accesses. For example, string “VIEW;EDIT” will set viewing and editing permissions parameters for the entity.

The **group_name** parameter is used to group entities by applications. It is used to split security into application scopes.

The **category** parameter is used to categorise an entity. It is used to split entities by section on the role privileges edit page.

By default (or when using the special `ALL` value for the `permissions` property as in the
example above), any [available permission](#permissions) can be granted to a user on an
entity. If you want to restrict the available permissions for an entity, you can list them
separated explicitly. For example, you limit it to the `VIEW` and `EDIT` permissions:

```php-annotations
/**
 * ...
 *     "security"={
 *       "type"="ACL",
 *       "permissions"="VIEW;EDIT",
 *       "group_name"="DemoGroup"
 *     }
 * ...
 */
```

Once an entity is marked as ACL-protected, you need to specify an ownership type for it.
It is done with the help of the `ownership` scope in the `defaultValues` section.

In this config, you should specify the ownership type that will be used for the entity, as well as
the names of the columns in the database and fields that will be used to store the link to the owner
of the record and the organization where this record was created.

For example, the config will be the following for the USER owner type:

```php-annotations
/**
 * @Config(
 *   defaultValues={
 *     ...
 *     "ownership"={
 *       "owner_type"="USER",
 *       "owner_field_name"="owner",
 *       "owner_column_name"="owner_id",
 *       "organization_field_name"="organization",
 *       "organization_column_name"="organization_id"
 *   }
 * )
```

For the business unit owner type:

```php-annotations
/**
 * @Config(
 *   defaultValues={
 *     ...
 *     "ownership"={
 *       "owner_type"="BUSINESS_UNIT",
 *       "owner_field_name"="owner",
 *       "owner_column_name"="owner_id",
 *       "organization_field_name"="organization",
 *       "organization_column_name"="organization_id"
 *   }
 * )
```

For an Organization owner type, you can specify only the `owner_field_name` and `owner_column_name`:

```php-annotations
/**
 * @Config(
 *   defaultValues={
 *     ...
 *     "ownership"={
 *       "owner_type"="ORGANIZATION",
 *       "owner_field_name"="owner",
 *       "owner_column_name"="owner_id"
 *   }
 * )
```

#### IMPORTANT
For the User and Business Unit ownership types, organization fields are **mandatory**.

<a id="backend-security-bundle-protect-resources"></a>

## Protecting Resources

After having configured which permissions a user can be granted to a particular entity, you have to
make sure that the permissions are taken into account when checking if a user has access to a
resource. Such check must be placed in the right places in the code.

### Restricting Access to Controller Methods

Let us assume that you have configured an entity to be protectable via ACLs. You have granted
some of its objects to a set of users. Now you can control who can enter certain resources through
the controller method. Restricting access can be done in two different ways:

1. Use the `@Acl` annotation on a controller method, providing the entity class name and the
   permission to check for:
   *src/Acme/DemoBundle/Controller/ProductController.php*
   ```php-annotations
    namespace Acme\DemoBundle\Controller;

    use Oro\Bundle\SecurityBundle\Annotation\Acl;
    use Symfony\Bundle\FrameworkBundle\Controller\Controller;

    class ProductController extends Controller
    {
        /**
         * @Acl(
         *   id="product_edit",
         *   type="entity",
         *   class="AcmeDemoBundle:Product",
         *   permission="EDIT"
         * )
         */
        public function editAction()
        {
            // ...
        }
    }
   ```
2. When you need to perform a particular check repeatedly, writing `@Acl` over and
   over again becomes a tedious task. This becomes even a more serious issue when your requirements
   change and you have to change a lot of ACLs.

   The ACL configuration from the example above looks like this:
   *src/Acme/DemoBundle/Resources/config/oro/acls.yml*
   ```yaml
    acls:
        product_edit:
            type: entity
            class: AcmeDemoBundle:Product
            permission: EDIT
   ```

   Annotation @AclAncestor enables you to reuse acl resources defined with the ACL annotation or described
   in the acls.yml file. The name of the ACL resource is used as the parameter of this annotation:
   *src/Acme/DemoBundle/Controller/ProductController.php*
   ```php-annotations
    namespace Acme\DemoBundle\Controller;

    use Oro\Bundle\SecurityBundle\Annotation\AclAncestor;
    use Symfony\Bundle\FrameworkBundle\Controller\Controller;

    class ProductController extends Controller
    {
        /**
         * @AclAncestor("product_edit")
         */
        public function editAction()
        {
            // ...
        }
    }
   ```

   Sometimes you want to protect a controller method coming from code that you do not control.
   Therefore, you cannot add the `@AclAncestor` annotation to it. Use the `bindings` key in the
   YAML configuration of your ACL to define which method(s) should be protected:
   *src/Acme/DemoBundle/Resources/config/oro/acls.yml*
   ```yaml
    acls:
        product_edit:
            type: entity
            class: AcmeDemoBundle:Product
            permission: EDIT
            bindings:
                - class: Acme\DemoBundle\Controller\ProductController
                  method: editAction
   ```

   You can read detailed explanations for all available YAML configuration options [in the reference section](../configuration/yaml/acls.md#access-control-lists).

**Using Param Converters**

* If the parameters of the method have an entity that is also used in the parameters of the ACL annotation, then access is checked directly on this object.
* If the parameters of the method have no type that is used in the annotation, then a check is performed at the class level when it is checked whether the user has access to this *type* of an entity, rather than to a specific instance of an entity.

#### SEE ALSO
It is also possible [to protect Doctrine queries](#backend-security-protecting-dql-queries).

### Data Grids

You can protect a datasource with ACL by adding the acl_resource parameter under the source node in the datagrid configuration:

```php
datagrids:
    DATAGRID_NAME_HERE:
        source:
            acl_resource: SOME_ACL_IF_NEEDED
```

<a id="backend-security-protecting-dql-queries"></a>

### Protecting Custom DQL Queries

When building custom DQL queries, you may want to reduce the result set being returned to
the set of domain objects the user is granted access to. To achieve this, use the ACL helper
provided by the OroSecurityBundle:

*src/Acme/DemoBundle/Controller/DemoController.php*
```php
 namespace Acme\DemoBundle\Controller;

 use Symfony\Bundle\FrameworkBundle\Controller\Controller;

 class DemoController extends Controller
 {
     public function protectedAction()
     {
         $repository = $this->getDoctrine()->getRepository('AcmeDemoBundle:Product');
         $queryBuilder = $repository
             ->createQueryBuilder('p');
             ->where('p.price > :price')
             ->orderBy('p.price', 'ASC')
             ->setParameter('price', 19.99);
         $aclHelper = $this->get('oro_security.acl_helper');
         $query = $aclHelper->apply($queryBuilder, 'VIEW');

         // ...
     }
 }
```

In this example, first, a query is built that selects all products from the database which are more
expensive than `19.99` order by their price. Then, the query builder is passed to the `apply()`
method of the `oro_security.acl_helper` service. This service, an instance of the
`Oro\Bundle\SecurityBundle\ORM\Walker\AclHelper` class, modifies the query only to the
return entities the user has access to.

### Manual Access Checks

Sometimes it is not possible to do an ACL check in the controller using annotations due to additional conditions.

In this case, you can use the `isGranted` function:

*src/Acme/DemoBundle/Controller/DemoController.php*
```php
 namespace Acme\DemoBundle\Controller;

 use Symfony\Bundle\FrameworkBundle\Controller\Controller;
 use Symfony\Component\Security\Core\Exception\AccessDeniedException;

 class DemoController extends Controller
 {
     public function protectedAction()
     {
         $entity = ...;

         if (!$this->isGranted('VIEW', $entity)) {
             throw new AccessDeniedException();
         }

         // ...
     }
 }
```

If you need to carry our an ACL check on an object that is not in the controller, use the `isGranted` method of the security.authorization_checker service.

The security.authorization_checker service is a public service that is used to check whether an access to a resource is granted or denied. This service represents the <a href="https://symfony.com/doc/current/components/security/authorization.html#authorization-checker" target="_blank">Authorization Checker</a>. The implementation of the Platform specific attributes and objects is in <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/SecurityBundle/Authorization/AuthorizationChecker.php" target="_blank">AuthorizationChecker class</a>.

The main entry point is isGranted method:

```php
isGranted($attributes[, $object])
```

**$attributes** can be a role name(s), permission name(s), an ACL annotation id, a string in format “permission;descriptor” (e.g., “VIEW;entity:AcmeDemoBundle:AcmeEntity” or “EDIT;action:acme_action”) or some other identifiers depending on registered security voters.

**$object** can be an entity type descriptor (e.g., “entity:Acme/DemoBundle/Entity/AcmeEntity” or  “action:some_action”), an entity object, instance of ObjectIdentity, DomainObjectReference or DomainObjectWrapper

**Examples**

Checking access to some ACL annotation resource

```php
$this->authorizationChecker->isGranted('some_resource_id')
```

Checking VIEW access to the entity by class name

```php
$this->authorizationChecker->isGranted('VIEW', 'Entity:MyBundle:MyEntity' );
```

Checking VIEW access to the entity’s field

```php
$this->authorizationChecker->isGranted('VIEW', new FieldVote($entity, $fieldName) );
```

Checking ASSIGN access to the entity object

```php
$this->authorizationChecker->isGranted('ASSIGN', $myEntity);
```

Checking access is performed in the following way: **Object-Scope**->\*\*Class-Scope\*\*->\*\*Default Permissions\*\*.

For example, we are checking View permission to $myEntity object of MyEntity class. When we call

```php
$this->authorizationChecker->isGranted('VIEW', $myEntity);
```

the first ACL for $myEntity object is checked; if nothing is found, then it checks ACL for MyEntity class and if no records are found, finally checks the Default(root) permissions.

Also there are two additional authorization checkers that may be helpful is some cases:

* <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/SecurityBundle/Authorization/ClassAuthorizationChecker.php" target="_blank">ClassAuthorizationChecker</a>
* <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/SecurityBundle/Authorization/RequestAuthorizationChecker.php" target="_blank">CRequestAuthorizationChecker</a>

### Restricting Access to Non-Entity” Resources

Sometimes when you do not want to protect an entity but just want to allow or deny access to a
certain part of your application. To achieve this, use the special `action` type for an ACL:

> ```php-annotations
> // ...

> /**
>  * @Acl(
>  *   id="protected_action",
>  *   type="action"
>  * )
>  */
> public function protectedAction()
> {
>     // ...
> }
> ```

> *src/Acme/DemoBundle/Resources/config/oro/acls.yml*
> ```yaml
>  acls:
>      protected_action:
>          type: action
> ```

### Manual Access Check on an Object Field

Developer can check access to the given entity field by passing instance FieldVote class to the isGranted method of the <a href="https://symfony.com/doc/current/components/security/authorization.html#authorization-checker" target="_blank">Authorization Checker</a>:

```php
$entity = $repository->findOneBy('id' => 10);

if (!$this->authorizationChecker->isGranted('VIEW', new FieldVote($entity, '_field_name_'))) {
    throw new AccessDeniedException('Access denided');
} else {
    // access is granted
}
```

### Check ACL for Search Queries

When collecting entities to search, information about the owner and the organization is added to the search index automatically.

Every search query is ACL protected with Search ACL helper. This helper limits data with the current access levels for entities which are used in the query.

## Organization Сontext

#### HINT
The ignore_preferred_organization_tokens parameter is available starting from OroCRM v4.2.8. To check which application version you are running, see the [system information](../../user/back-office/system/system-information/index.md#system-information).

As mentioned previously, each record is associated with an owning organization. When a user logs into the system,
they work in the scope of one of their organizations.

In Enterprise editions, a user can be assigned to multiple organizations.

During the login, if the security token supports organizations, then the current organization in the token is replaced
with the preferred one. If a user logs into the system for the first time, the first available organization is used.

After the login, the user can switch their current organization.

For the security token to ignore the preferable organization, for example an API token, add its class name
to the ignore_preferred_organization_tokens parameter of the OrganizationPro bundle in the app.yml file
of your bundle:

*src/Acme/DemoBundle/Resources/config/oro/app.yml*
```yaml
oro_organization_pro:
     ignore_preferred_organization_tokens:
         - Acme\Demo\Your\Token\Class
```

#### BUSINESS TIP
## Business Tip

Discover how <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a> improves operations, customer experiences, and sales by reading our guide.

<!-- Frontend -->
