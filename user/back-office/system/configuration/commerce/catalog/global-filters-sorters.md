<a id="configuration-guide-commerce-configuration-catalog-filters-sorters"></a>

# Configure Global Filters and Sorters Settings

To make sure that only the attributes of the required product family are displayed in the storefront, you can limit filters and sorting options in OroCommerce. You can also control whether to hide or disable filters and sorting options in the storefront for the products that do not belong to the selected product family or collapse and expand the display of applied filters in the filter panel.

<!-- For instance, the Lawnmowers and Pressure Washers product collections usually have different product attributes: for lawnmowers these can be *Blade Type* or *Cutting Heights*, while for pressure washers the *Flow Rate* or *Temperature*. Ideally, you would not want the *Flow Rate* to be displayed as a filtering option for lawnmowers in the storefront. -->

#### HINT
Configuration for this option is available on three levels, globally, [per organization](../../../user-management/organizations/org-configuration/commerce/catalog/organization-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters-organization), and [per website](../../../websites/web-configuration/commerce/catalog/website-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters-website).

#### NOTE
By default, the options are enabled for OroCommerce versions 3.0 and higher.

<a id="configuration-guide-commerce-configuration-catalog-filters-sorters-globally"></a>

To configure filters and sorting options globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Catalog > Filters and Sorters** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

The following page opens:

![Filters and Sorters global configuration settings](user/img/system/config_commerce/catalog/filters_and_sorters.png)
1. In the **Limit Filters and Sorters** section, the following configuration options are available:
   * **Hide Unrelated Product Filters and Sorting Options** — removes unrelated filters and sorting options from the product collection page to display only those attributes that belong to the current product family. When a user adjusts the initial product data search to target the product with the desired attribute, but the attribute is no longer applicable, it gets removed from the filter.

   > ![The storefront product page illustrating the Hide Unrelated Product Filters and Sorting Options configuration](user/img/system/config_commerce/catalog/hide_unrelated_product_filters.png)
   * **Don’t Change Initial Filter State** — disables unrelated attributes within a filter instead of removing it. When applying a filter to the initial product data set in the storefront, all unrelated attributes remain visible but become disabled in the filter dropdown (available only in the OroCommerce Enterprise edition). This option affects filters in the storefront only when **Hide Unrelated Product Filters and Sorting Options** is enabled. Please ensure to enable both options for this configuration.

   > ![The storefront product page illustrating the Don't Change Initial Filter State configuration](user/img/system/config_commerce/catalog/dont_change_initial_filter_state.png)

   #### NOTE
   If a multi-attribute product has only one attribute, the filter is not displayed for it in the storefront.

   For example, if a product (e.g., a shirt) has several options for the attribute of color (red, green, yellow) but only red items are available, then no filter by color will be displayed in the storefront. This way, customers will not see the filter for the attribute where multiple options are unavailable at that moment.
2. In the **Display Settings** section, select the required option for the following settings:
   * **Default Filter Panel State** — controls the visibility of the filters applied to the product grids in the storefront. The filter panel can be either expanded to show all filter bars or collapsed to reduce the screen space. In this case, the collapsed filters are substituted with the text representation of all applied filters.

   > ![The storefront product page illustrating the Default Filter Panel State configuration](user/img/system/config_commerce/catalog/filters_and_sorters_storefront.png)
   > * **Filter Panel Position** — enables to select the required position of the filter bar in the storefront (applicable since OroCommerce v4.2.0. To check which application version you are running, see the [system information](../../../system-information/index.md#system-information)). There are two options available:

   > > When *Top* (default) is selected, the filter bar is displayed on the top of the product listing page.
   > > ![The storefront product page illustrating the filter on the top of the product listing page](user/img/system/config_commerce/catalog/filters_panel_position_top.png)

   > > When *Sidebar* is selected, the filter is displayed in the left sidebar.
   > > ![The storefront product page illustrating the filter in the left sidebar](user/img/system/config_commerce/catalog/filters_panel_position_sidebar.png)
3. To customize any of these options:
   > 1. Clear the **Use Default** box next to the option.
   > 2. Select the necessary checkbox or a value.
4. Click **Save Settings**.
