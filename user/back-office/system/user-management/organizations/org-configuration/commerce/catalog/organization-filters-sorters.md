<a id="configuration-guide-commerce-configuration-catalog-filters-sorters-organization"></a>

# Configure Filters and Sorters Settings per Organization

To configure filters and sorting options per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Catalog > Filters and Sorters** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![image](user/img/system/user_management/org_configuration/catalog/filters_and_sorters_org.png)
4. The following configuration options are available:
   * **Hide Unrelated Product Filters and Sorting Options** - removes unrelated filters and sorting options from the product collection page to display only those attributes that belong to the current product family. When a user adjusts the search to target the product with the desired attribute, but the attribute is no longer applicable, it gets removed from the filter.
   * **Don’t Change Initial Filter State** - disables unrelated attributes within a filter. When applying a filter to the initial product data set in the storefront, all unrelated attributes remain visible but become disabled in the filter dropdown.

     #### NOTE
     This option affects filters in the storefront only when **Hide Unrelated Product Filters and Sorting Options** is enabled. Please ensure to enable both options for this configuration.
   * **Default Filter Panel State** - controls the visibility of the filters applied to the product grids in the storefront. The filter panel can be either expanded to show all filter bars or collapsed to reduce the screen space. In this case, the collapsed filters are substituted with the text representation of all applied filters.
   * **Filter Panel Position** — enables to select the required position of the filter bar in the storefront. There are two options available:

     When *Top* (default) is selected, the filter bar is displayed on the top of the product listing page.
     ![The storefront product page illustrating the filter on the top of the product listing page](user/img/system/config_commerce/catalog/filters_panel_position_top.png)

     When *Sidebar* is selected, the filter is displayed in the left sidebar.
     ![The storefront product page illustrating the filter in the left sidebar](user/img/system/config_commerce/catalog/filters_panel_position_sidebar.png)
5. To change any of the default options set on the global level:
   > 1. Clear the **Use System** checkbox next to the option.
   > 2. Select the necessary checkbox or a value.
6. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
