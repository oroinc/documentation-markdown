<a id="configuration-guide-commerce-configuration-product-images"></a>

# Configure Global Settings for Product Images

On the Product Images configuration page, you can control the way images are previewed on product listing pages and configure whether to use popup or inline view for the image gallery.

To configure the product image settings globally:

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Product Images** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global product image watermark configuration settings](user/img/system/config_commerce/product/ProductImages.png)
3. To customize the option configuration, clear the **Use Default** checkbox next to the option and select the required value.

#### NOTE
As of application version 5.0.2, the **Enable Original File Names** option is hidden. To configure the original image file names, navigate to [General Setup > Upload Settings](../../system/general-setup/upload.md#admin-configuration-upload-settings) in the system configuration.

<a id="sys-commerce-product-product-images"></a>
1. In the **Product Image Watermark** section, you can control the watermark that will appear on top of every image uploaded as part of product details.
   * **File** — The image file with the watermark on a transparent background.
   * **Size** — The size of the watermark in percentage compared to the whole image.
   * **Position** — The watermark position on the image (e.g., top left, top, top right, left, right, center, bottom left, bottom, and bottom right).

<a id="sys-commerce-product-product-images-image-preview-global"></a>
1. In the **Image Gallery Options** section, enable or disable product previews on product listing pages by simplifying product selection for customer.
   ![Global image gallery options configuration settings](user/img/system/config_commerce/product/ImagePreviewGlobal.png)

   When **Enable Image Preview on Product Listing** is enabled, clicking on the product image on the product listing page in the storefront will open a pop up image gallery, rather than the product page.
   ![Illustration of the Enable Image Preview on Product Listing option in the storefront](user/img/system/config_commerce/product/ImagePreviewEnabled.png)

   When **Enable Image Preview on Product Listing** is disabled, clicking on the product image on the product listing page in the storefront will open the product page.
   ![Illustration of the Enable Image Preview on Product Listing option disabled](user/img/system/config_commerce/product/ImagePreviewDisabled.png)

<a id="sys-commerce-product-product-images-gallery-slider-global"></a>
1. In the **Image Gallery Options** section, choose whether to use popup or inline view for the image gallery in the storefront.
   ![image](user/img/system/config_commerce/product/ImageGallery.png)

   When **Popup Gallery on Product View** is enabled, image gallery in the storefront will take the following form:
   ![Illustration of the Popup Gallery on Product View option in the storefront](user/img/system/config_commerce/product/ImageGalleryEnabled.png)

   By clicking on the image, the pop up gallery will be displayed in the middle of the screen:
   ![Displaying the popup gallery functionality](user/img/system/config_commerce/product/ImageGalleryEnabled2.png)

   When **Popup Gallery on Product View** is disabled, the image gallery will take the form of an inline view:
   ![Displaying the popup gallery functionality if the feature is disabled](user/img/system/config_commerce/product/ImageGalleryDisabled.png)

   Flick through the pictures in the gallery by pressing < or > arrows without leaving the product page.
2. Click **Save Settings**.
