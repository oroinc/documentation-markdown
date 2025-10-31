<a id="configuration-guide-commerce-configuration-catalog-filters-sorters"></a>

<a id="configuration-guide-commerce-configuration-catalog-filters-sorters-globally"></a>

# Configure Global Filters and Sorters Settings

To make sure that only the attributes of the required product family are displayed in the storefront, you can limit filters and sorting options in OroCommerce. You can also control whether to hide or disable filters and sorting options in the storefront for the products that do not belong to the selected product family or collapse and expand the display of applied filters in the filter panel.

#### HINT
Configuration for this option is available on three levels, globally, [per organization](../../../user-management/organizations/org-configuration/commerce/catalog/organization-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters-organization), and [per website](../../../websites/web-configuration/commerce/catalog/website-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters-website).

To configure filters and sorting options globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Catalog > Filters and Sorters** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Filters and Sorters global configuration settings](user/img/system/config_commerce/catalog/filters_and_sorters.png)
1. To customize the option configuration, clear the **Use Default** checkbox next to the option and select the required value.
2. In the **Limit Filters and Sorters** section, the following configuration options are available:
   * **Hide Unrelated Product Filters and Sorting Options** — removes unrelated filters and sorting options from the product collection page to display only those attributes that belong to the current product family. When a user adjusts the initial product data search to target the product with the desired attribute, but the attribute is no longer applicable, it gets removed from the filter.

   > ![The storefront product page illustrating the Hide Unrelated Product Filters and Sorting Options configuration](user/img/system/config_commerce/catalog/hide_unrelated_product_filters.png)
   * **Don’t Change Initial Filter State** — disables unrelated attributes within a filter instead of removing it. When applying a filter to the initial product data set in the storefront, all unrelated attributes remain visible but become disabled in the filter dropdown (available only in the OroCommerce Enterprise edition). This option affects filters in the storefront only when **Hide Unrelated Product Filters and Sorting Options** is enabled. Please ensure to enable both options for this configuration.

   > ![The storefront product page illustrating the Don't Change Initial Filter State configuration](user/img/system/config_commerce/catalog/dont_change_initial_filter_state.png)

   > #### NOTE
   > If a multi-attribute product has only one attribute, the filter is not displayed for it in the storefront.

   > For example, if a product (e.g., a shirt) has several options for the attribute of color (red, green, yellow) but only red items are available, then no filter by color will be displayed in the storefront. This way, customers will not see the filter for the attribute where multiple options are unavailable at that moment.
3. In the **Display Settings** section, select the required option for the following settings:
   * **Default Filter Panel State** — controls the visibility of the filters applied to the product grids in the storefront. The filter panel can be either expanded to show all filter bars or collapsed to reduce the screen space. In this case, the collapsed filters are substituted with the text representation of all applied filters.
   * **Filter Panel Position** — specifies where the filter panel should be represented in the storefront, at the top or in the sidebar.

   #### IMPORTANT
   The Filter Panel Position configuration applies to OroCommerce version 5.1 and below and is retained in the current version only for legacy backward compatibility. For v6.0 and above, please configure this option under [System > Theme Configuration](../../../theme-configuration/index.md#back-office-theme-configuration).

   #### HINT
   To specify how to display the multi-select filter options, refer to the [theme-related settings](../design/theme-global.md#configuration-commerce-design-theme).
4. Click **Save Settings**.
