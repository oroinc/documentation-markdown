<a id="back-office-theme-configuration"></a>

# Theme Configuration

Theme configuration enables you to manage your website’s storefront look and feel, customize menus in the header, select the way the main navigation menu is displayed, choose the layout for the product page details, etc.

#### NOTE
To customize the storefront theme for 5.1 and earlier versions of OroCommerce, please refer to the [theme system configuration](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme) settings.

To configure your current storefront theme:

1. Navigate to **System > Theme Configurations** in the main menu.
2. There is a list of storefront themes configured by a developer for your website. By default, there is a new 6.1 Refreshing Teal theme, but there can also be your backup themes from the previous versions of OroCommerce.
3. You can create a new configuration of the existing theme by clicking **Create Theme Configuration** on the top right or edit any existing theme configuration by clicking <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to the right of the theme.

> ![The list of existing theme configurations](user/img/system/theme-configuration/theme-configuration-list.png)
1. In the **General** section, configure the following options:
   ![General section of the theme configuration](user/img/system/theme-configuration/theme-configuration-general.png)
   * **Owner** — Select the owner responsible for the theme configuration.
   * **Theme** — Select the storefront theme from the list. The default theme starting from version 6.1 LTS is *Refreshing Teal*. However, if you select one of your backup themes from the previous OroCommerce LTS versions, the settings under the Configuration menu below will become disabled. You can still configure them under the [theme system configuration](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme) settings.

   > ![Theme configuration details when the default 5.0 theme is selected](user/img/system/theme-configuration/theme-configuration-5.0.png)
   * **Name** — Specify the name for the theme to distinguish it from other themes.
   * **Description** — Type a short but meaningful description that can help you and other users understand the specifics of the theme.
   * **Type** — Select the theme type. Currently, only storefront themes are available for configuration.
2. In the **Configuration** section, customize the following options. You can preview several menu configuration setting to visualize what the option does and where the selected storefront menu will be positioned.
   ![Configuration section of the theme configuration](user/img/system/theme-configuration/theme-configuration-config-details.png)

* **Show Quick Access Menu** — Enable a storefront quick access menu ([oro_customer_dashboard_quick_access_menu](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide-storefront-quick-access)) on the customer user’s [Dashboard](../../../storefront/account/dashboard/index.md#storefront-dashboard) page. You can edit this menu under *System > Storefront Menus* to include shortcuts to key sections.
  > ![Illustrating the enabled storefront quick access menu on the customer user’s Dashboard page](user/img/system/theme-configuration/oro-customer-dashboard-quick-access-menu.png)
* **Show Purchase Volume Chart** — Enable a bar chart to show the customer user’s total purchase volume over the past 12 months on the customer user’s [Dashboard](../../../storefront/account/dashboard/index.md#storefront-dashboard) page. The total purchase volume is the sum of all orders placed by or for this customer user (excluding sub-orders and canceled orders).
  > ![Illustrating the enabled Purchase Volume Chart on the customer user`s Dashboard page](user/img/system/theme-configuration/volume-chart.png)
* **Customer Dashboard Content Widget (1-6)** — Select a [datagrid content widget](../../marketing/content-widgets/index.md#content-widgets-dashboard-datagrid-widget) from the list of predefined widgets to display on the customer user’s [Dashboard](../../../storefront/account/dashboard/index.md#storefront-dashboard) page. You can select up to six content widgets. Only the widgets of the **Customer Dashboard DataGrid** type are displayed in the dropdown list. Each widget presents up to five of the latest records in a grid format, with an option to view all other records on a dedicated page.
  > ![Illustrating the selected 5 content widgets on the customer user’s Dashboard page](user/img/system/theme-configuration/customer-dashboard-content-widgets.png)
* **Recommended Products (1-2)** — Select a [product segment content widget](../../marketing/content-widgets/index.md#content-widgets-user-guide) from the list of predefined widgets to display on the customer user’s [Dashboard](../../../storefront/account/dashboard/index.md#storefront-dashboard) page. You can select up to two content widgets. Only the widgets of the **Product Segment** type are displayed in the dropdown list. This widget highlights specific product segments for the customer user.
  > ![Illustrating the selected 5 content widgets on the customer user’s Dashboard page](user/img/system/theme-configuration/recommended-products-widgets.png)
* **Promotional Content Block (1-2)** — Select a [content block](../../marketing/content-blocks/index.md#user-guide-landing-pages-marketing-content-blocks) from the dropdown list to display on the customer user’s [Dashboard](../../../storefront/account/dashboard/index.md#storefront-dashboard) page. You can select up to two content blocks. This section can include important information such as news, blog posts, or other relevant content.
  > ![Illustrating the selected 5 content widgets on the customer user’s Dashboard page](user/img/system/theme-configuration/dashboard-promotional-block.png)
* **Customer Dashboard Scorecard (1-4)** — Select a [scorecard content widget](../../marketing/content-widgets/index.md#content-widgets-dashboard-scorecard-widget) from the list of predefined widgets to display on the customer user’s [Dashboard](../../../storefront/account/dashboard/index.md#storefront-dashboard) page. You can select up to four content widgets. Only the widgets of the **Scorecard** type are displayed in the dropdown list. The scorecards represent the information about the total number of customer users under the current customer, the number of shopping lists, open Requests for Quote (excluding cancelled ones), and the total value of all non-cancelled orders.
  > ![Illustration of the Scorecard widget in the storefront](user/img/marketing/content_widgets/scorecard.png)
* **Promotional Content** — Select a [content block](../../marketing/content-blocks/index.md#user-guide-landing-pages-marketing-content-blocks) from the dropdown list to display it at the top of the storefront header.
  > ![Promotional content configuration and representation in the storefront header](user/img/system/theme-configuration/promotional-content.png)
* **Top Navigation Menu** — Select a storefront menu that will be rendered above the header. Please see the [concept guide on storefront menu items](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide) to learn more about each menu.
  > ![Top navigation menu representation in the storefront header](user/img/system/theme-configuration/top-navigation-menu.png)
* **Quick Links Menu** — The top level items from the selected storefront menu will be added to the header to provide quick access to the most frequently used pages. Please see the [concept guide on storefront menu items](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide) to learn more about each menu.
  > ![Quick Links Menu representation in the storefront header](user/img/system/theme-configuration/quick-links-menu.png)
* **Quick Access Button** — The quick access button can either open an additional storefront menu, be a direct shortcut to the product catalog, or another important section of the website. Select the type of the quick access button and specify the name to display it in the storefront header.
  > ![Quick access button representation in the storefront header](user/img/system/theme-configuration/quick-access-button.png)
* **Language And Currency Switchers** — Select where you want to place the language and currency switcher. When *Above the header* option is selected, the language and currency switchers are rendered above the header on the devices with the sufficient screen width. On smaller screens the language/currency switchers will be placed inside the “hamburger” menu (product catalog).
  > ![Two representations of language and currency switchers in the storefront](user/img/system/theme-configuration/language-currency-switchers.png)
* **Standalone Main Menu** — Enable the setting to let the main menu be rendered separately and to provide easy access to its top level items on the devices with sufficient screen width. On smaller screens the main menu will be placed inside the “hamburger” menu.
* **Search on Smaller Screens** — Select the way the search is going to be represented on devices with small screens. The search input can either be rendered in its own row to provide easy access to global search (*standalone*), or in line with the shopping list item (*integrated*).
  > ![Two representations of search on small screens in the storefront](user/img/system/theme-configuration/search-on-small-screens.png)
* **Use Pagination Input if Number of Pages Exceeds** — Set the threshold for a number of pages, at which a pagination input field will appear. If the total number of pages exceeds this specified number, the system will display a pagination input, allowing users to directly enter a page number and quickly navigate to it, rather than clicking through each page individually.
* **CSS Variables Configuration** — This option includes all the CSS variables that frontend developers use to define the theme in the storefront. These variables are made available here for easier access, allowing administrators to fine-tune the website’s storefront appearance directly. Currently, all variables are rendered as text inputs, and basic validation is in place. However, future updates will enhance validation to ensure that values entered match the allowed CSS properties. The list of supported CSS variables includes: css_background, css_border_radius, css_box_shadow, css_color, css_font_size, css_gap, css_length, css_line_height, css_min_height, css_outline, css_padding, and more.
  > ![CSS variables configuration represented as as text inputs to be filled by back-office users](user/img/system/theme-configuration/CSS-variables-configuration.png)
* **Product View Page Template** — Select the product page template from the list. A page template is used to render the product page in the storefront by default, unless the template is overridden in the product details. Available options are *Default*, *Tabs*, and *Wide*.
  > **Default Template**:
  > ![image](user/img/system/theme-configuration/default-page-template.png)

  > **Tabs (Additional Attribute Groups Are Displayed In Tabs)**:
  > ![image](user/img/system/theme-configuration/tabbed-page-template.png)

  > **Wide (Additional Attribute Groups Are Displayed In Collapse One Below Another For Full Page Width)**:
  > ![image](user/img/system/theme-configuration/wide-page-template.png)
* **Display Price Tiers As** — Select a multi or single unit table. A multi-unit table shows price tiers for all product units in the same table, which might not work well for products with many units or when quantity tiers are not aligned between units. Single-unit table shows price tiers only for the currently selected unit.
* **Product Image Zoom Type** — Select the zoom effect for product images on the product details page. Available options:
  > **Window**: Displays a zoomed portion of the image in a separate window near the product image.
  > ![image](user/img/system/theme-configuration/preview-zoom-window.png)

  > **Inner**: Zooms in directly inside the product image area.
  > ![image](user/img/system/theme-configuration/preview-zoom-inner.png)

  > **Lens**: Displays a square lens effect for zooming.
  > ![image](user/img/system/theme-configuration/preview-zoom-lens.png)

  > **Disabled**: Disables the zoom effect for product images on the product details page.
* **Product Image Zoom Overlay** — Enable or disable an overlay above the product image when zoom is activated. This option works only with the *Window* or *Lens* zoom types.
  > ![image](user/img/system/theme-configuration/preview-zoom-overlay.png)
* **Scale Zoom On Mouse Wheel** — Enable or disable the ability to adjust the zoom level using the mouse wheel while hovering over the product image. When enabled, users can zoom in or out for a closer look.
  > ![image](user/img/system/theme-configuration/preview-zoom-on-mousewheel.png)
* **Product View Images Display Mode** — Select how additional product images are displayed on the product details page. Available options are *Horizontal* (thumbnails are displayed in a horizontal row below the main product image) and *Vertical* (thumbnails are  displayed in a vertical column beside the main product image).
* **Filter Panel Position** — Specify where the filter panel should be represented in the storefront. Available options are *Top*, *Sidebar* and *Overlay*.
  > ![Three representations of filter panel positions in the storefront](user/img/system/theme-configuration/filter-panel-position.png)

  > #### HINT
  > To specify how to display the multi-select filter options, refer to the [theme-related settings](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme).

  > To control whether to hide or disable product attributes within filters, refer to the [filters and sorting settings](../configuration/commerce/catalog/global-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters) documentation.
* **Contact Us Form** — Select a [contact us content widget](../../marketing/content-widgets/index.md#content-widgets-user-guide) from the dropdown list of predefined widgets to display on the Contact Us page. Only the widgets of the **Contact Us Form** type are displayed in the dropdown list.
  > ![Illustrating the selected contact us widget on the Contact Us page](user/img/system/theme-configuration/contact-us-form-widget.png)
* **Quantity Inputs in Shopping List** — Choose how quantity inputs are displayed in the shopping list. Available options are *Plain* (displays a simple input field where users can type the desired quantity manually) and *With Stepper Buttons* (adds `+` and `-` buttons next to the input field, allowing users to adjust the quantity incrementally).

1. Click **Save Settings**.

Once saved, you can now enable your theme configuration under the theme system settings on the required level: [globally](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme), [per organization](../user-management/organizations/org-configuration/commerce/design/organization-theme.md#configuration-commerce-design-theme-theme-settings-organization) or [website](../websites/web-configuration/commerce/design/website-theme.md#configuration-commerce-design-theme-theme-settings-website).

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
