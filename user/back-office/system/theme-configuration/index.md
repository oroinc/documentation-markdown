<a id="back-office-theme-configuration"></a>

# Theme Configuration

#### HINT
Theme Configuration is available starting from OroCommerce v6.0.1. To check which application version you are running, see the [system information](../system-information/index.md#system-information).

Theme configuration enables you to manage your website’s storefront look and feel, customize menus in the header, select the way the main navigation menu is displayed, choose the layout for the product page details, etc.

#### NOTE
To customize the storefront theme for 5.1 and earlier versions of OroCommerce, please refer to the [theme system configuration](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme) settings.

To configure your current storefront theme:

1. Navigate to **System > Theme Configurations** in the main menu.
2. There is a list of storefront themes configured by a developer for your website. By default, there is a new 6.1 Refreshing Teal theme, but there can also be your backup themes from the previous versions of OroCommerce.
3. You can create a new configuration of the existing theme by clicking **Create Theme Configuration** on the top right or edit any existing theme configuration by clicking <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to the right of the theme.

> ![The list of existing theme configurations](user/img/system/theme-configuration/theme-configuration-list.png)
1. In the **General** section, configure the following options:
   ![Theme configuration details](user/img/system/theme-configuration/theme-configuration.png)
   * **Owner** — Select the owner responsible for the theme configuration.
   * **Theme** — Select the storefront theme from the list. The default theme starting from version 6.1 LTS is *Refreshing Teal*. However, if you select one of your backup themes from the previous OroCommerce LTS versions, the settings under the Configuration menu below will become disabled. You can still configure them under the [theme system configuration](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme) settings.

   > ![Theme configuration details when the default 5.0 theme is selected](user/img/system/theme-configuration/theme-configuration-5.0.png)
   * **Name** — Specify the name for the theme to distinguish it from other themes.
   * **Description** — Type a short but meaningful description that can help you and other users understand the specifics of the theme.
   * **Type** — Select the theme type. Currently, only storefront themes are available for configuration.
2. In the **Configuration** section, customize the following options. You can preview each menu configuration setting to visualize what the option does and where the selected storefront menu will be positioned.
   * **Promotional Content** — Select a [content block](../../marketing/content-blocks/index.md#user-guide-landing-pages-marketing-content-blocks) from the dropdown list to display it at the top of the storefront header.

   ![Promotional content configuration and representation in the storefront header](user/img/system/theme-configuration/promotional-content-block.png)
   * **Top Navigation Menu** — Select a storefront menu that will be rendered above the header. Please see the [concept guide on storefront menu items](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide) to learn more about each menu.

   ![Top navigation menu representation in the storefront header](user/img/system/theme-configuration/top-navigation-menu.png)
   * **Quick Links Menu** — The top level items from the selected storefront menu will be added to the header to provide quick access to the most frequently used pages. Please see the [concept guide on storefront menu items](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide) to learn more about each menu.

   ![Quick Links Menu representation in the storefront header](user/img/system/theme-configuration/quick-links-menu.png)
   * **Quick Access Button** — The quick access button can either open an additional storefront menu, be a direct shortcut to the product catalog, or another important section of the website. Select the type of the quick access button and specify the name to display it in the storefront header.

   ![Quick access button representation in the storefront header](user/img/system/theme-configuration/quick-access-button.png)
   * **Language And Currency Switchers** — Select where you want to place the language and currency switcher. When *Above the header* option is selected, the language and currency switchers are rendered above the header on the devices with the sufficient screen width. On smaller screens the language/currency switchers will be placed inside the “hamburger” menu (product catalog).

   ![Two representations of language and currency switchers in the storefront](user/img/system/theme-configuration/language-currency-switchers.png)
   * **Standalone Main Menu** — Enable the setting to let the main menu be rendered separately and to provide easy access to its top level items on the devices with sufficient screen width. On smaller screens the main menu will be placed inside the “hamburger” menu.
   * **Search on Smaller Screens** — Select the way the search is going to be represented on devices with small screens. The search input can either be rendered in its own row to provide easy access to global search (*standalone*), or in line with the shopping list item (*integrated*).

   ![Two representations of search on small screens in the storefront](user/img/system/theme-configuration/search-on-small-screens.png)
   * **Product View Page Template** — Select the product page template from the list. A page template is used to render the product page in the storefront by default, unless the template is overridden in the product details. Available options are *Default*, *Tabs*, and *Wide*.

     **Default Template**:
     ![image](user/img/system/theme-configuration/default-page-template.png)

     **Tabs (Additional Attribute Groups Are Displayed In Tabs)**:
     ![image](user/img/system/theme-configuration/tabbed-page-template.png)

     **Wide (Additional Attribute Groups Are Displayed In Collapse One Below Another For Full Page Width)**:
     ![image](user/img/system/theme-configuration/wide-page-template.png)

> * **Display Price Tiers As** — Select a multi or single unit table. A multi-unit table shows price tiers for all product units in the same table, which might not work well for products with many units or when quantity tiers are not aligned between units. Single-unit table shows price tiers only for the currently selected unit.

> > * **Filter Panel Position** — Specify where the filter panel should be represented in the storefront. Available options are *Top*, and *Sidebar*.

> > ![Three representations of filter panel positions in the storefront](user/img/system/theme-configuration/filter-panel-position.png)

> > #### HINT
> > To specify how to display the multi-select filter options, refer to the [theme-related settings](../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme).

> > To control whether to hide or disable product attributes within filters, refer to the [filters and sorting settings](../configuration/commerce/catalog/global-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters) documentation.
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
