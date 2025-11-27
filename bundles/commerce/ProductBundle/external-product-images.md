<a id="bundle-docs-commerce-product-bundle-external-product-images"></a>

# Externally Stored Product Images

Out-of-the-box, product images are stored in-house and with the support of [Digital Asset Manager](../../../user/back-office/marketing/digital-assets/index.md#digital-assets). If you need to switch the product images field to the [externally stored files](../../platform/AttachmentBundle/attachment-bundle-config.md#attachment-bundle-externally-stored-files) flow, you have to do it manually via code, as the **Stored Externally** entity field config cannot be changed from the UI for the already existing fields.

#### NOTE
The rule of thumb is to decide how product images field should work before you create products and upload images. Otherwise, you may have to create a data migration for the already existing product images.

#### NOTE
Switching to the externally stored product images flow disables [Digital Asset Manager](../../../user/back-office/marketing/digital-assets/index.md#digital-assets) for that field.

Below you can find an example of how to switch to the externally stored product images flow manually.

1. Create the migration that switches attachment.is_stored_externally entity field config to true:
   *src/Acme/Bundle/DemoBundle/Migrations/Schema/v1_0/EnableIsStoredExternallyForProductImage.php*
   ```php
   namespace Acme\Bundle\DemoBundle\Migrations\Schema\v1_0;

   use Doctrine\DBAL\Schema\Schema;
   use Oro\Bundle\EntityConfigBundle\Migration\UpdateEntityConfigFieldValueQuery;
   use Oro\Bundle\MigrationBundle\Migration\Migration;
   use Oro\Bundle\MigrationBundle\Migration\QueryBag;
   use Oro\Bundle\ProductBundle\Entity\ProductImage;

   class EnableIsStoredExternallyForProductImage implements Migration
   {
       /**
        * @inheritDoc
        */
       public function up(Schema $schema, QueryBag $queries)
       {
           $queries->addPostQuery(
               new UpdateEntityConfigFieldValueQuery(ProductImage::class, 'image', 'attachment', 'is_stored_externally', true)
           );
       }
   }
   ```

#### NOTE
This code works with the upgrade only. If you need it to work with installation, update these metadata with the data migration.

1. Create the <a href="https://symfony.com/doc/5.4/form/create_form_type_extension.html" target="_blank">form type extension</a> for the `Oro\Bundle\ProductBundle\Form\Type\ProductImageType` form type to toggle the isExternalFile form option:
   *src/Acme/Bundle/DemoBundle/Form/Extension/ProductImageExtension.php*
   ```php
   namespace Acme\Bundle\DemoBundle\Form\Extension;

   use Oro\Bundle\AttachmentBundle\Form\Type\ImageType;
   use Oro\Bundle\ProductBundle\Form\Type\ProductImageType;
   use Symfony\Component\Form\AbstractTypeExtension;
   use Symfony\Component\Form\FormBuilderInterface;

   class ProductImageExtension extends AbstractTypeExtension
   {
       /**
        * @inheritDoc
        */
       public static function getExtendedTypes(): iterable
       {
           return [ProductImageType::class];
       }

       /**
        * @inheritDoc
        */
       public function buildForm(FormBuilderInterface $builder, array $options): void
       {
           $builder->add('image', ImageType::class, ['allowDelete' => false, 'isExternalFile' => true]);
       }
   }
   ```

   *src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
   ```yaml
   services:
       acme.form.extension.product_image:
           class: Acme\Bundle\DemoBundle\Form\Extension\ProductImageExtension
           tags:
               - { name: form.type_extension }
   ```

#### NOTE
The product image field is system-owned, therefore you need to create a form extension as the product image field’s options should be controlled explicitly by a developer. For the [custom extend fields](../../../backend/entities/extend-entities/index.md#book-entities-extended-entities-add-fields) added to a form automatically, form options are generated automatically, so you do not have to create a form extension that toggles an option.

Afterward, the product images field on the product form will switch from the file upload input to the external URL input. The application will not process, resize, or modify product images, but return an external URL as is. Product images import will also switch to the externally stored files, so it will not try to upload files, but only pick their URLs.

#### NOTE
If you need more control over how the externally stored files’ URLs are used for displaying images, refer to the [custom URL provider](../../platform/AttachmentBundle/generating-image-file-urls.md#attachment-bundle-custom-url-provider) documentation.

## Getting External Data From a URL

There are two methods in `Oro/Bundle/AttachmentBundle/Tools/ExternalFileFactory.php` for representing external file data - createFromFile and createFromUrl.
By default, the createFromUrl method uses the HEAD HTTP method to retrieve file metadata. If HEAD is disabled on the requested server, you can configure the external URL with a regex and specify alternative HTTP methods for metadata retrieval.

> *config/config.yml*
> ```yaml
> oro_attachment:
>     external_file_details_http_methods:
>         - regex: '/^https:\/\/example\.com\/products\/*/'
>           methods: [ GET ]
>         - regex: '/^https:\/\/example\.com\/media\/*/'
>           methods: [ HEAD, GET ]
> ```

#### NOTE
The script will attempt the HTTP methods (e.g., GET, HEAD, etc.) in the listed order for each URL pattern. Once a request succeeds, the script stops and does not try any subsequent methods for that endpoint.

#### NOTE
The HEAD method will be used by default if the requested URL does not match any regex or if the external_file_details_http_methods configuration is missing.

<!-- Frontend -->
