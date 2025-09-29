<a id="configuration-guide-commerce-configuration-product-images"></a>

# Configure Global Settings for Product Images

On the Product Images configuration page, you can control the following settings:

* [Image Watermark]()
* [Image Preview on Product Listing Page]()
* [Image Gallery]()

To configure the product image settings globally:

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Product Images** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global product image watermark configuration settings](user/img/system/config_commerce/product/ProductImages.png)
3. Customize any of the options by proceeding through the following steps:
   > 1. Clear the **Use Default** check box next to the option.
   > 2. Enable the required check box or enter the necessary file size and type information.

#### NOTE
As of application version 4.2.11, the **Enable Original File Names** option is hidden. To configure the original image file names, navigate to [General Setup > Upload Settings](../../system/general-setup/upload.md#admin-configuration-upload-settings) in the system configuration.

<a id="sys-commerce-product-product-images"></a>

## Image Watermark

In the **Product Image Watermark** section, you can control the watermark that will appear on top of every image uploaded as part of product details on two levels, globally and [per website](../../../websites/web-configuration/commerce/product/website-image-preview.md#sys-websites-commerce-product-product-images).

> * **File** — The image file with the watermark on a transparent background.
> * **Size** — The size of the watermark in percentage compared to the whole image.
> * **Position** — The watermark position on the image (e.g., top left, top, top right, left, right, center, bottom left, bottom, and bottom right).

<a id="sys-commerce-product-product-images-image-preview-global"></a>

## Image Preview on Product Listing Page

In the **Image Gallery Options** section, enable or disable product previews on product listing pages by simplifying product selection for customer. This can be done on three levels, globally, [per organization](../../../user-management/organizations/org-configuration/commerce/product/organization-image-preview.md#sys-commerce-product-product-images-image-preview-organization), and [per website](../../../websites/web-configuration/commerce/product/website-image-preview.md#sys-commerce-product-product-images-image-preview-website).

> ![Global image gallery options configuration settings](user/img/system/config_commerce/product/ImagePreviewGlobal.png)

When **Enable Image Preview on Product Listing** is enabled, clicking on the product image on the product listing page in the storefront will open a pop up image gallery, rather than the product page.

> ![Illustration of the Enable Image Preview on Product Listing option in the storefront](user/img/system/config_commerce/product/ImagePreviewEnabled.png)

When **Enable Image Preview on Product Listing** is disabled, clicking on the product image on the product listing page in the storefront will open the product page.

> ![Illustration of the Enable Image Preview on Product Listing option disabled](user/img/system/config_commerce/product/ImagePreviewDisabled.png)

> #### NOTE
> By default, **Enable Image Preview on Product Listing** is enabled.

<a id="sys-commerce-product-product-images-gallery-slider-global"></a>

## Image Gallery

n the **Image Gallery Options** section, choose whether to use popup or inline view for the image gallery in the storefront.

#### HINT
This can be configured on three levels, globally, [per organization](../../../user-management/organizations/org-configuration/commerce/product/organization-image-preview.md#sys-users-organization-commerce-products-gallery-slider) and [per website](../../../websites/web-configuration/commerce/product/website-image-preview.md#sys-websites-commerce-product-gallery-slider).

![image](user/img/system/config_commerce/product/ImageGallery.png)

When **Popup Gallery on Product View** is enabled, image gallery in the storefront will take the following form:

> ![Illustration of the Popup Gallery on Product View option in the storefront](user/img/system/config_commerce/product/ImageGalleryEnabled.png)

> By clicking on the image, the pop up gallery will be displayed in the middle of the screen:

> ![Displaying the popup gallery functionality](user/img/system/config_commerce/product/ImageGalleryEnabled2.png)

When **Popup Gallery on Product View** is disabled, the image gallery will take the form of an inline view:

> ![Displaying the popup gallery functionality if the feature is disabled](user/img/system/config_commerce/product/ImageGalleryDisabled.png)

> Flick through the pictures in the gallery by pressing < or > arrows without leaving the product page.

> #### NOTE
> By default, **Popup Gallery on Product View** is enabled.
1. Click **Save Settings**.
