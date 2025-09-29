<a id="configuration-commerce-design-theme-theme-settings-globally"></a>

<a id="configuration-commerce-design-theme-page-templates"></a>

<a id="configuration-commerce-design-theme-filter-settings"></a>

<a id="configuration-commerce-design-theme-menu-templates"></a>

<a id="configuration-commerce-design-theme"></a>

# Configure Global Theme Settings

In your Oro application, you can control and customize the storefront look and feel.

#### HINT
This can be done on three levels – globally, [per organization](../../../user-management/organizations/org-configuration/commerce/design/organization-theme.md#configuration-commerce-design-theme-theme-settings-organization) and [website](../../../websites/web-configuration/commerce/design/website-theme.md#configuration-commerce-design-theme-theme-settings-website).

You can set the following theme-related options that apply globally by default:

* Pre-designed theme for the storefront
* The layout for the product page details (default tabbed view, short, two column, or list)
* Style of the selector in filters
* Display mode for the user menu in the storefront

To configure the storefront theme options globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Design > Theme** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global theme configuration settings](user/img/system/config_commerce/design/design_theme_global.png)
3. In the **Theme Settings** section, configure the following options:
   * **Theme** — select the theme from the list. The theme controls general design of the storefront that defines its look and feel. *Default*, *blank*, and *custom* themes are available out of the box for the storefront.

   For example, this is how the address book looks in the storefront for the default and custom themes:

   **Default theme**
   ![A sample of the Address Book menu in the storefront if the default theme is enabled](user/img/system/config_commerce/design/MyProfileAddressBooks.png)

   **Custom theme**
   ![A sample of the Address Book menu in the storefront if the custom theme is enabled](user/img/system/config_commerce/design/address_book_compact.png)

   **Product Image Placeholder** — select the image file that will appear on the product listing and product view pages for the products that have no associated images to avoid a blank image page.
   ![A sample of the product image placeholder on the product listing page](user/img/system/config_commerce/design/product_image_placeholder.png)

   **Category Image Placeholder** — select the image file to be applied to the category that has no associated image. The image is usually used in various category widgets (e.g., *Featured Categories*).
   ![A sample of the product image placeholder for the on the product listing age](user/img/system/config_commerce/design/category_image_placeholder.png)
4. In the **Page Templates** section, select the product page template from the list.

   This page template is used to render the product page in the storefront by default, unless the template is overridden in the product details.

   *Default template* (tabbed), *Short page*, *Two-column page*, and *List page* templates are available out of the box. For preview and more information on these options, see the [Manage Product Page Design with Page Templates](../../../../products/products/page-templates.md#user-guide-page-templates) topic.

   Select the **Use Parent Scope Value** check box to use the default value.
5. In the **Filter Settings** section, specify how the multi-select filters should look in the storefront. Available options are *Drop-down* and *All at once*.

   For example, this is how the user menu looks for different values:

   **Drop-down**
   ![Illustration of the multi-select filter dispayed in the drop-down in the storefront](user/img/system/config_commerce/design/filter_settings_dropdown.png)

   **All at once**
   ![Illustration of the multi-select filter displayed all at once in the storefront](user/img/system/config_commerce/design/filter_settings_allatonce.png)
6. In the **Menu Templates** section, select the user menu display mode that defines the look and feel of the user menu in the storefront.

   For example, this is how the user menu looks for different values:

   **Show all items at once**
   ![The storefront user menu look when the Show all items at once option is enabled](user/img/system/config_commerce/design/ShowAllItemsAtOnce.png)

   **Show subitems in a popup**
   ![The storefront user menu look when the Show subitems in a popup option is enabled](user/img/system/config_commerce/design/ShowSubitemsInPopup.png)
7. In the **Grid Settings** section, configure the following options:

   **Responsive Grids** — This option makes storefront grids responsible, realigning row cells to fit various screen sizes.

   **Swipe Actions Grids** — This option enables swipe actions for the storefront grids on mobile devices.
8. Click **Save Settings**.
