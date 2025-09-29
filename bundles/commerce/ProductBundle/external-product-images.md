<a id="bundle-docs-commerce-product-bundle-external-product-images"></a>

# Externally Stored Product Images

#### HINT
The feature is available starting from v5.0.2. To check which application version you are running, see the [system information](../../../user/back-office/system/system-information/index.md#system-information).

Out-of-the-box, product images are stored in-house and with the support of [Digital Asset Manager](../../../user/back-office/marketing/digital-assets/index.md#digital-assets). If you need to switch the product images field to the [externally stored files](../../platform/AttachmentBundle/attachment-bundle-config.md#attachment-bundle-externally-stored-files) flow, you have to do it manually via code as the **Stored Externally** entity field config cannot be changed from the UI for the already existing fields.

#### NOTE
The rule of thumb is to decide how product images field should work before you create products and upload images. Otherwise, you may have to create a data migration for the already existing product images.

#### NOTE
Switching to the externally stored product images flow disables [Digital Asset Manager](../../../user/back-office/marketing/digital-assets/index.md#digital-assets) for that field.

Below you can find the example of how to manually switch to the externally stored product images flow.

> 1. Create the migration that switches attachment.is_stored_externally entity field config to true:
>    > *src/Acme/Bundle/AppBundle/Migrations/Schema/v1/EnableIsStoredExternallyForProductImage.php*
>    > ```php
>    >      namespace Acme\Bundle\AppBundle\Migrations\Schema\v1;

>    >      use Doctrine\DBAL\Schema\Schema;
>    >      use Oro\Bundle\EntityConfigBundle\Migration\UpdateEntityConfigFieldValueQuery;
>    >      use Oro\Bundle\MigrationBundle\Migration\Migration;
>    >      use Oro\Bundle\MigrationBundle\Migration\QueryBag;
>    >      use Oro\Bundle\ProductBundle\Entity\ProductImage;

>    >      class EnableIsStoredExternallyForProductImage implements Migration
>    >      {
>    >          public function up(Schema $schema, QueryBag $queries): void
>    >          {
>    >              $queries->addPostQuery(
>    >                  new UpdateEntityConfigFieldValueQuery(ProductImage::class, 'image', 'attachment', 'is_stored_externally', true)
>    >              );
>    >          }
>    >      }
>    > ```
> 2. Create the <a href="https://symfony.com/doc/5.4/form/create_form_type_extension.html" target="_blank">form type extension</a> for the `Oro\Bundle\ProductBundle\Form\Type\ProductImageType` form type to toggle the isExternalFile form option:
>    > *src/Acme/Bundle/AppBundle/Form/Extension/ProductImageExtension.php*
>    > ```php
>    >      use Oro\Bundle\AttachmentBundle\Form\Type\ImageType;
>    >      use Oro\Bundle\ProductBundle\Form\Type\ProductImageType;
>    >      use Symfony\Component\Form\AbstractTypeExtension;
>    >      use Symfony\Component\Form\FormBuilderInterface;

>    >      class ProductImageExtension extends AbstractTypeExtension
>    >      {
>    >          public static function getExtendedTypes(): iterable
>    >          {
>    >              return [ProductImageType::class];
>    >          }

>    >          public function buildForm(FormBuilderInterface $builder, array $options): void
>    >          {
>    >              $builder->add('image', ImageType::class, ['allowDelete' => false, 'isExternalFile' => true]);
>    >          }
>    >      }
>    > ```

>    > *src/Acme/Bundle/AppBundle/Resources/config/services.yml*
>    > ```yaml
>    >      services:
>    >          acme.form.extension.product_image:
>    >              class: 'Acme\Bundle\AppBundle\Form\Extension\ProductImageExtension'
>    >              tags:
>    >                  - { name: form.type_extension }
>    > ```

>    > #### NOTE
>    > The product image field is system-owned, therefore you need to create a form extension as the product image field’s options should be controlled explicitly by a developer. For the [custom extend fields](../../../backend/entities/extend-entities/index.md#book-entities-extended-entities-add-fields) added to a form automatically, form options are generated automatically so you do not have to create a form extension that toggles an option.

Afterward, the product images field on a the product form will switch from the file upload input to the external URL input. The application will not process, resize or modify product images, but return an external URL as is. Product images import will also switch to the externally stored files, so it will not try to upload files, but only pick their URLs.

#### NOTE
If you need to have more control on how the externally stored files URLs are used for displaying images, look towards [custom URL provider](../../platform/AttachmentBundle/generating-image-file-urls.md#attachment-bundle-custom-url-provider).

<!-- Frontend -->
