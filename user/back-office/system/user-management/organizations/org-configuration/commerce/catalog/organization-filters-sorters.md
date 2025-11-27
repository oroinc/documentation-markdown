<a id="configuration-guide-commerce-configuration-catalog-filters-sorters-organization"></a>

# Configure Filters and Sorters Settings per Organization

#### HINT
Configuration for this option is available on three levels, [globally](../../../../../configuration/commerce/catalog/global-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters), per organization, and [per website](../../../../../websites/web-configuration/commerce/catalog/website-filters-sorters.md#configuration-guide-commerce-configuration-catalog-filters-sorters-website).

To configure filters and sorting options per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Catalog > Filters and Sorters** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![image](user/img/system/user_management/org_configuration/catalog/filters_and_sorters_org.png)
4. To change any of the default options set on the global level:
   > 1. Clear the **Use System** checkbox next to the option.
   > 2. Select the necessary checkbox or a value.
5. The following configuration options are available:
   * **Hide Unrelated Product Filters and Sorting Options** - removes unrelated filters and sorting options from the product collection page to display only those attributes that belong to the current product family. When a user adjusts the search to target the product with the desired attribute, but the attribute is no longer applicable, it gets removed from the filter.

   ![The storefront product page illustrating the Hide Unrelated Product Filters and Sorting Options configuration](user/img/system/config_commerce/catalog/hide_unrelated_product_filters.png)
   * **Don’t Change Initial Filter State** - disables unrelated attributes within a filter. When applying a filter to the initial product data set in the storefront, all unrelated attributes remain visible but become disabled in the filter dropdown.

   #### NOTE
   This option affects filters in the storefront only when **Hide Unrelated Product Filters and Sorting Options** is enabled. Please ensure to enable both options for this configuration.

   ![The storefront product page illustrating the Don't Change Initial Filter State configuration](user/img/system/config_commerce/catalog/dont_change_initial_filter_state.png)
   * **Default Filter Panel State** - controls the visibility of the filters applied to the product grids in the storefront. The filter panel can be either expanded to show all filter bars or collapsed to reduce the screen space. In this case, the collapsed filters are substituted with the text representation of all applied filters.
   * **Filter Panel Position** — specifies where the filter panel should be represented in the storefront, at the top or in the sidebar.

   #### IMPORTANT
   The Filter Panel Position configuration applies to OroCommerce version 5.1 and below and is retained in the current version only for legacy backward compatibility. For v6.0 and above, please configure this option under [System > Theme Configuration](../../../../../theme-configuration/index.md#back-office-theme-configuration).

   #### HINT
   To specify how to display the multi-select filter options, refer to the [theme-related settings](../../../../../configuration/commerce/design/theme-global.md#configuration-commerce-design-theme).
6. Click **Save Settings**.

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
