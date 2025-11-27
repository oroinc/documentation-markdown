<a id="sys-commerce-product-product-images-image-preview-organization"></a>

<a id="sys-users-organization-commerce-products-gallery-slider"></a>

# Configure Settings for Product Images per Organization

In the Product Images section of Commerce configuration settings, you can control the way images are previewed on product listing pages and configure whether to use popup or inline view for the image gallery per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> more actions menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Products > Product Images** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![image](user/img/system/user_management/org_configuration/products/ImagePreviewOrganization.png)
4. Clear the **Use System** checkbox to change the system-wide setting.
5. In the **General** section, configure the following options:

   **Enable Original File Names** — When enabled, the original image file name will be appended to the system-generated hash value. All non-alphanumeric characters (e.g., “:”, “)”, “,”, “~”) will be replaced with “-” (dash).

   For example, the name of the file is **coffee_maker/bosch_#RND123.jpg**, the system-generated hash value is “media/cache/attachment/product_gallery_main/5bae287538.jpg”. If the option is enabled, the file name will be displayed in the storefront as follows “media/cache/attachment/product_gallery_main/5bae287538-coffee-maker-bosch-RND123.jpg”
6. In the **Image Gallery Options** section, enable or disable the required options.

**Enable Image Preview on Product Listing**:

> * When **Enable Image Preview on Product Listing** is enabled, clicking on the product image on the product listing page in the storefront will open a pop up image gallery, rather than the product page.
>   ![image](user/img/system/user_management/org_configuration/products/ImagePreviewOrgEnabled.png)
> * When **Enable Image Preview on Product Listing** is disabled, clicking on the product image on the product listing page in the storefront will open the product page.

> > ![image](user/img/system/user_management/org_configuration/products/ImagePreviewOrgDisabled.png)

> > #### NOTE
> > When **Use System** checkbox is enabled, system settings are applied.

**Popup Gallery on Product View**

> * When **Popup Gallery on Product View** is enabled, image gallery in the storefront will take the following form:
>   <!-- image::/img/system/user_management/org_configuration/products/ImageGalleryOrganizationEnabled.png
>   :class: with-border -->

>   By clicking on the image, the pop up gallery will be displayed in the middle of the screen:
>   ![image](user/img/system/user_management/org_configuration/products/ImageGalleryOrganizationEnabled2.png)
> * When **Popup Gallery on Product View** is disabled, the image gallery will take the form of an inline view:
>   ![image](user/img/system/user_management/org_configuration/products/ImageGalleryOrganizationDisabled.png)

>   Flick through the pictures in the gallery by pressing < or > arrows without leaving the product page.
1. Click **Save**.

<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
