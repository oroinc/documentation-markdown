<a id="index-0"></a>

<a id="how-to-create-new-bundle"></a>

<a id="dev-cookbook-framework-how-to-create-new-bundle"></a>

# Create a Bundle

## Create a Bundle Manually

First, specify the name and namespace of your bundle. The Symfony framework already provides
<a href="https://symfony.com/doc/6.4/bundles/best_practices.html#bundle-name" target="_blank">best practices for bundle structure and bundle name</a>, and we recommend following them.

Suppose you want to create the AcmeDemoBundle under the namespace `Acme\Bundle\DemoBundle`
in the `/src` directory. Create the corresponding directory structure and the bundle file with the following content:

*src/Acme/Bundle/DemoBundle/AcmeDemoBundle.php*
```php

namespace Acme\Bundle\DemoBundle;

use Symfony\Component\HttpKernel\Bundle\Bundle;

class AcmeDemoBundle extends Bundle
{
}
```

This is a regular Symfony bundle. The only difference is how you enable it (see [Enable a Bundle]()).

## Create a Bundle Service Container Extension

To load configuration files, create a Service Container Extension. See <a href="https://symfony.com/doc/6.4/configuration.html#configuration-files" target="_blank">Symfony Configuration Files</a>

*src/Acme/Bundle/DemoBundle/DependencyInjection/AcmeDemoExtension.php*
```php

namespace Acme\Bundle\DemoBundle\DependencyInjection;

use Symfony\Component\Config\FileLocator;
use Symfony\Component\DependencyInjection\ContainerBuilder;
use Symfony\Component\DependencyInjection\Loader;
use Symfony\Component\HttpKernel\DependencyInjection\Extension;

class AcmeDemoExtension extends Extension
{
    #[\Override]
    public function load(array $configs, ContainerBuilder $container)
    {
        $loader = new Loader\YamlFileLoader($container, new FileLocator(__DIR__ . '/../Resources/config'));
        // register services configuration
        $loader->load('services.yml');
        // register other configurations in the same way
    }
}
```

Create a basic `Resources/config/services.yml` to define service parameters. See <a href="https://symfony.com/doc/6.4/service_container.html#service-parameters" target="_blank">Symfony Service Parameters</a>

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
 services:
```

<!-- Create bundle automatically -->
<!-- --------------------------- -->
<!-- Also new bundle can be generated using `Symfony command generate:bundle`_: -->
<!-- .. _Symfony command generate:bundle: http://symfony.com/doc/2.4/bundles/SensioGeneratorBundle/commands/generate_bundle.html -->
<!-- .. code-block:: none -->
<!-- user@host:/var/www/vhosts/platform-application$ php bin/console generate:bundle -->
<!-- Bundle namespace: Acme/Bundle/DemoBundle -->
<!-- Bundle name [AcmeDemoBundle]: -->
<!-- Target directory [/var/www/vhosts/platform-application/src]: -->
<!-- Configuration format (yml, xml, php, or annotation): yml -->
<!-- Do you want to generate the whole directory structure [no]? -->
<!-- Do you confirm generation [yes]? -->
<!-- Generating the bundle code: OK -->
<!-- Checking that the bundle is autoloaded: OK -->
<!-- Confirm automatic update of your Kernel [yes]? no -->
<!-- Enabling the bundle inside the Kernel: FAILED -->
<!-- Confirm automatic update of the Routing [yes]? no -->
<!-- Importing the bundle routing resource: FAILED -->
<!-- It is important that you do not need to update Kernel and routing, as OroPlatform provides its own way to do that, -->
<!-- which will be described in the `Enable bundle`_ chapter and in following articles. -->
<!-- .. note:: -->
<!-- Automatic bundle generation is provided by the ``sensio/generator-bundle`` package, which is defined in the -->
<!-- ``require-dev`` section of the ``composer.json`` file in the OroPlatform repository. Therefore, in order to use -->
<!-- automatic generation, please, make sure that this package has been installed (one of the ways to do so is to execute -->
<!-- ``composer update`` at the project's root directory to get all packages from the ``require-dev`` section). -->

## Enable a Bundle

You now have all the files required to enable the new bundle. To enable it:

1. Create a Resources/config/oro/bundles.yml file with the following content:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/bundles.yml*
```yaml
bundles:
    - { name: Acme\Bundle\DemoBundle\AcmeDemoBundle, priority: 255 }
```

This file provides a list of bundles to register. All such files are automatically parsed to load the required bundles.

1. Regenerate the application cache using console command `cache:clear`:
   ```none
   user@host:/var/www/vhosts/platform-application$ php bin/console cache:clear
   Clearing the cache for the dev environment with debug true
   ```

   #### NOTE
   If you are working in production environment, use parameter `--env=prod` with the command.
2. Check if your bundle is registered and active with following command:
   ```none
   php bin/console debug:container --parameter=kernel.bundles --format=json | grep AcmeDemoBundle
   ```

   #### NOTE
   Replace grep argument with your bundle’s proper name
3. When your bundle is registered and active, the command displays output similar to the following:
   ```none
   "AcmeDemoBundle": "Acme\\Bundle\\DemoBundle\\AcmeDemoBundle",
   ```

## References

* <a href="https://symfony.com/doc/6.4/bundles/best_practices.html" target="_blank">Symfony Best Practices for Structuring Bundles</a>
* <a href="https://symfony.com/doc/6.4/reference/events.html" target="_blank">Symfony Framework Events</a>
* [Bundle-less Structure](../architecture/bundle-less-structure.md#dev-backend-architecture-bundle-less-structure)

<!-- Frontend -->
