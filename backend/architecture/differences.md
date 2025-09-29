<a id="book-differences"></a>

# Differences to Common Symfony Applications

Starting your first project using OroPlatform or OroCRM will be easy if you’re familiar with building Symfony applications from scratch. However,
there are some differences you need to understand to develop your application efficiently.

This article will give you a short overview of how OroPlatform differs from typical Symfony applications. Each section will link to other resources where you can learn more about a particular feature.

## The Application Kernel

In Symfony applications, you register your and all the third-party bundles from the `vendor` directory in the `AppKernel` class. This is unnecessary when using OroPlatform. It comes with its own kernel that discovers bundles under the `src` and the `vendor` directories automatically if they contain a `bundles.yml` configuration file in their `Resources/config/oro` directory.

This file must contain a list of bundle classes to initialize under the `bundles` key. Usually, it is only a one class name:

*src/Acme/DemoBundle/Resources/config/oro/bundles.yml*
```yaml
 bundles:
     - Acme\DemoBundle\AcmeDemoBundle
```

Optionally, you can specify a priority. The priority defines the order in which bundles will be loaded. If you omit the priority, its value will implicitly be 0:

*src/Acme/DemoBundle/Resources/config/oro/bundles.yml*
```yaml
 bundles:
     - { name: Acme\DemoBundle\AcmeDemoBundle, priority: 10 }
```

#### CAUTION
A higher priority does not mean that one bundle is loaded before another bundle with a lower priority. Instead, lower prioritized bundles are loaded first.

#### TIP
The default priority for all bundles is 0.

## Routing Configuration

You can configure routes for your controller actions the same way as in Symfony. However, you would usually need to manually perform import for your routing configuration in the main `routing.yml` file in your `config` directory like this:

*config/routing.yml*
```yaml
 default_controller:
     resource: "@AcmeDemoBundle/Controller/DefaultController.php"
     type:     annotation

 acme_demo:
     resource: "@AcmeDemoBundle/Resources/config/routing.yml"
     prefix: /demo
```

With OroPlatform, you can still configure your routes the way you like. As long as you create the main `routing.yml` file in the bundle’s `Resources/config/oro` directory, you do not have to register your routing config in the application config; it will be discovered automatically.

## Access Control Lists

<a href="https://symfony.com/doc/5.4/security/acl.html" target="_blank">Access Control Lists</a> (ACLs) usually involve working with the ACL provider, object identities, ACEs, the mask builder, etc. OroPlatform makes
things more accessible by providing the <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/SecurityBundle/Annotation/Acl.php" target="_blank">@Acl</a> annotation that you can use to define an ACL and protect a controller in a single step:

*src/Acme/DemoBundle/Controller/BlogController.php*
```php
 namespace Acme\DemoBundle\Controller;

 use Oro\Bundle\SecurityBundle\Annotation\Acl;

 // ...

 /**
  * @Acl(
  *     id="acme_demo.blog_post_view",
  *     type="entity",
  *     class="AcmeDemoBundle:BlogPost",
  *     permission="VIEW"
  * )
  */
 public function indexAction()
 {
     // ...
 }
```

Furthermore, once an ACL has been defined, you can reuse it using the <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/SecurityBundle/Annotation/AclAncestor.php" target="_blank">@AclAncestor</a> annotation:

*src/Acme/DemoBundle/Controller/BlogController.php*
```php
 namespace Acme\DemoBundle\Controller;

 use Oro\Bundle\SecurityBundle\Annotation\AclAncestor;

 // ...

 /**
  * @AclAncestor("acme_demo.blog_post_view")
  */
 public function postAction()
 {
     // ...
 }
```

#### SEE ALSO
For more information, see [Security documentation](../../bundles/platform/SecurityBundle/index.md#bundle-docs-platform-security-bundle).

## Extension Management

With the <a href="https://getcomposer.org/" target="_blank">Composer</a>, you can easily pull in third-party libraries and bundles for the application. Aside from using Composer to manage dependency management, OroPlatform supports Oro extensions. An extension is a package that adds new features to the Platform. To achieve this, the <a href="https://github.com/oroinc/platform/tree/5.0/src/Oro/Bundle/DistributionBundle" target="_blank">OroDistributionBundle</a> leverages Composer and <a href="https://packagist.org/" target="_blank">Packagist</a>. All extensions feature on the <a href="https://extensions.oroinc.com/orocommerce/" target="_blank">Oro Extensions Store</a>. You do not have to use the command line to install extensions unless you want to, and a user with admin permissions can install them on their own in the UI.

#### SEE ALSO
You can also [add your own extension](../extension/add-extension.md#dev-extend-how-to-publish-extension-on-the-marketplace) to the Oro Extensions Store.

<!-- Frontend -->
