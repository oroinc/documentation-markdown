<a id="bundle-docs-platform-image-placeholder-config"></a>

# Image Placeholder Configuration

## Intro

To define your own entity image placeholder or redefine the existing one, use one of the following three options.

All examples are illustrated for the Product entity, but you can do the same for any other entity.

There are three services that enable you to set a placeholder for the image that is already defined in the system for the Product entity.

## Default Image Placeholder Provider

Take a look at the <a href="https://github.com/oroinc/orocommerce/blob/5.1/src/Oro/Bundle/ProductBundle/Resources/config/image_placeholder.yml" target="_blank">image_placeholder.yml</a> file on Github.

Perform the following steps to override DefaultImagePlaceholderProvider that is located at the very bottom of this chain:

1. Create an appropriate service definition.
   > ```yaml
   > # Resources/config/services.yml
   > services:

   >     acme_demo.provider.demo_image_placeholder.default:
   >         parent: oro_layout.provider.image_placeholder.default.abstract
   >         public: false
   >         arguments:
   >             - '/bundles/acmedemo/images/demo_placeholder_default.png'
   > ```
2. Add your newly created service to the `oro_product.provider.product_image_placeholder` chain service.  You can do it via DI CompilerPass.
   > ```php
   > // DependencyInjection/Compiler/ImagePlaceholderProviderPass.php
   > namespace Acme\Bundle\DemoBundle\DependencyInjection\Compiler;

   > use Symfony\Component\DependencyInjection\Compiler\CompilerPassInterface;
   > use Symfony\Component\DependencyInjection\ContainerBuilder;
   > use Symfony\Component\DependencyInjection\Reference;

   > /**
   >  * The ImagePlaceholderProviderPass compiler pass class.
   >  */
   > class ImagePlaceholderProviderPass implements CompilerPassInterface
   > {
   >     public function process(ContainerBuilder $container)
   >     {
   >         if (!$container->hasDefinition('oro_product.provider.product_image_placeholder')) {
   >         }

   >         $definition->setMethodCalls(array_merge(
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.config')]]],
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.theme')]]],
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.default')]]],
   >             $definition->getMethodCalls()
   > ```

Pay attention to the way the chain works. It gets the first suitable value from providers, so we have put our own provider to the very top of the chain via `ContainerBuilder::setMethodCalls` and `array_merge`. You can locate your own provider where required.

Make sure to insert CompilerPass to the bundle root file.

> ```php
> <?php

> // AcmeDemoBundle.php
> namespace Acme\Bundle\DemoBundle;

> use Oro\Bundle\DataAuditBundle\Model\AuditFieldTypeRegistry;
> use Symfony\Component\HttpKernel\Bundle\Bundle;
> use Acme\Bundle\DemoBundle\DependencyInjection\Compiler\ImagePlaceholderProviderPass;
> use Symfony\Component\DependencyInjection\ContainerBuilder;
> use Acme\Bundle\DemoBundle\DependencyInjection\Compiler\AcmeExtendValidationPass;

> class AcmeDemoBundle extends Bundle
> {
>     /**
>      * {@inheritdoc}
>      */
>     public function build(ContainerBuilder $container): void
>     {
>         parent::build($container);

>         $container->addCompilerPass(new ImagePlaceholderProviderPass());
>         $container->addCompilerPass(new AcmeExtendValidationPass());
>         /**
>          * You can also use AuditFieldTypeRegistry::overrideType to replace existing type
>          * But make sure you move old data into new columns
>          */
>         AuditFieldTypeRegistry::addType($doctrineType = 'datetimenew', $auditType = 'datetimenew');
>     }
> }
> ```

## Theme Image Placeholder Provider

The second way to define an image placeholder is to set it on the theme layer.

To do this, perform the following:

1. Define one more service and name it as `acme_demo.provider.demo_image_placeholder.theme`. The argument which this service receives is the placeholder name of our placeholder image. You can name this argument the same as the entity name, `product` in our case, to avoid any confusion.
   > ```yaml
   > # Resources/config/services.yml
   > services:

   >     acme_demo.provider.demo_image_placeholder.theme:
   >        parent: oro_layout.provider.image_placeholder.theme.abstract
   >        public: false
   >        arguments:
   >            - 'product'
   > ```
2. Add the `acme_demo.provider.demo_image_placeholder.theme` service definition to CompilerPass.
   > ```php
   > // DependencyInjection/Compiler/ImagePlaceholderProviderPass.php
   >         if (!$container->hasDefinition('oro_product.provider.product_image_placeholder')) {
   >             return;

   >         $definition = $container->getDefinition('oro_product.provider.product_image_placeholder');
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.config')]]],
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.theme')]]],
   > ```
3. Create `theme.yml`
   > ```yaml
   > # Resources/views/layouts/default/theme.yml
   > image_placeholders:
   >     product: '/bundles/acmedemo/images/demo_placeholder_theme.png'
   > ```

#### NOTE
Pay attention that the `product` key in the YAML file is the value that we have passed to `acme_demo.provider.demo_image_placeholder.theme` as the first argument.

## Config Image Placeholder Provider

The third way to define an image placeholder is through the system configuration parameters.

To do this, perform the following:

1. Define one more service with the `acme_demo.provider.demo_image_placeholder.config` name. The argument which this service receives is the system configuration key.
2. Define this configuration key in the system. More details on how to do it are described in the <a href="https://doc.oroinc.com/backend/system-configuration/#creating-configuration-forms" target="_blank">System Configuration</a> article.
   > ```yaml
   > # Resources/config/services.yml
   > services:

   >     acme_demo.provider.demo_image_placeholder.config:
   >        parent: oro_layout.provider.image_placeholder.config.abstract
   >        public: false
   >        arguments:
   >            - 'acme_demo.provider.demo_image_placeholder.config.param'
   > ```
3. Add the `acme_demo.provider.demo_image_placeholder.config` service definition to CompilerPass.
   > ```php
   > // DependencyInjection/Compiler/ImagePlaceholderProviderPass.php
   >         if (!$container->hasDefinition('oro_product.provider.product_image_placeholder')) {
   >             return;

   >         // ...
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.config')]]],
   >             [['addProvider', [new Reference('acme_demo.provider.demo_image_placeholder.theme')]]],
   > ```

## TwigExtension and template examples

To use the providers we have created previously, we need to create TwigExtension that fetches the Product image in the appropriate dimension or, if the main image is unavailable, provides the placeholder instead.

> ```php
> // Twig/ProductImageExtension.php
> namespace Acme\Bundle\DemoBundle\Twig;

> use Oro\Bundle\AttachmentBundle\Entity\File;
> use Oro\Bundle\AttachmentBundle\Manager\AttachmentManager;
> use Oro\Bundle\LayoutBundle\Provider\Image\ImagePlaceholderProviderInterface;
> use Psr\Container\ContainerInterface;
> use Symfony\Contracts\Service\ServiceSubscriberInterface;
> use Twig\Extension\AbstractExtension;
> use Twig\TwigFunction;

> /**
>  * Provides Twig functions to get image placeholder and type images for a product entity:
>  *   - product_filtered_image
>  *   - product_image_placeholder
>  */
> class ProductImageExtension extends AbstractExtension implements ServiceSubscriberInterface
> {
>     private ContainerInterface $container;

>     public function __construct(ContainerInterface $container)
>     {
>         $this->container = $container;
>     }

>     /**
>      * {@inheritdoc}
>      */
>     public function getFunctions()
>     {
>         return [
>             new TwigFunction('product_filtered_image', [$this, 'getProductFilteredImage']),
>             new TwigFunction('product_image_placeholder', [$this, 'getProductImagePlaceholder'])
>         ];
>     }

>     public function getProductFilteredImage(?File $file, string $filter): string
>     {
>         if ($file) {
>             return $this->getAttachmentManager()->getFilteredImageUrl($file, $filter);
>         }

>         return $this->getProductImagePlaceholder($filter);
>     }

>     public function getProductImagePlaceholder(string $filter): string
>     {
>         return $this->getImagePlaceholderProvider()->getPath($filter);
>     }

>     /**
>      * {@inheritdoc}
>      */
>     public static function getSubscribedServices()
>     {
>         return [
>             AttachmentManager::class,
>             'oro_product.provider.product_image_placeholder' => ImagePlaceholderProviderInterface::class,
>         ];
>     }

>     private function getAttachmentManager(): AttachmentManager
>     {
>         return $this->container->get(AttachmentManager::class);
>     }

>     private function getImagePlaceholderProvider(): ImagePlaceholderProviderInterface
>     {
>         return $this->container->get('oro_product.provider.product_image_placeholder');
>     }
> }
> ```

> ```yaml
> # Resources/config/services.yml
> services:
>     acme_demo.twig.product_image_extension:
>         class: Acme\Bundle\DemoBundle\Twig\ProductImageExtension
>         arguments:
>             - '@oro_platform.twig.service_locator'
>         tags:
>             - { name: twig.extension }
> ```

You can use Twig functions declared in the extension for your templates.

> > ```html+twig
> > {# Resources/views/layouts/default/imports/oro_product_list_item/oro_product_list_item.html.twig #}

> > {# ... #}
> > {% set productImage = product.imagesByType('listing').first.image|default(null) %}

> > {% include '@OroAttachment/Twig/picture.html.twig' with {
> >     sources: product_filtered_picture_sources(productImage, product_image_size),
> >     img_attrs: {
> >         alt: 'Product Image',
> >         itemprop: 'image'
> >     }
> > } %}
> > ```
> <!-- Frontend -->
