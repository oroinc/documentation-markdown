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
4. In the **Product Sorting** section, configure the options that enable you to override the default product sorting behavior in the storefront, which is typically based on a product sort order (if specified) and by relevance score.
   > #### NOTE
   > The product sorting feature was introduced in OroCommerce Enterprise versions 6.1.3 and 6.1.4.

   > #### HINT
   > Before enabling the options, ensure to:
   > 1. Define the options for the [inventory_status](../../../../products/product-attributes/index.md#products-product-attributes) product attribute under the Products > Product Attributes back-office menu. Drag and drop statuses to arrange them by priority (e.g., *In Stock, Out Of Stock, Discontinued*). Products with higher-priority statuses will be displayed first. Please note that the inventory_status attribute is a system product attribute, so only a system administrator of the global organization can edit it.
   >    > ![The details page of the Inventory status product attribute](user/img/system/config_commerce/catalog/inventory-status-attribute.png)
   > 2. Check the [visibility of the inventory statuses](../inventory/allowed-statuses.md#configuration-guide-commerce-configuration-inventory-allowed-statuses) under System > Configuration > Commerce > Inventory > Allowed Statuses to ensure that products with the specified status can be visible in the storefront.
   >    > ![The config page of the Allowed Statuses commerce system menu](user/img/system/config_commerce/catalog/inventory-status-visibility-config.png)

* **Sort Category Products by Inventory Status** — When enabled, the items on product listing (master catalog category) pages in the storefront will be sorted by their inventory status, as configured under the Products > Product Attributes back-office menu. Products with higher-priority statuses (e.g., *In Stock*) will appear first, followed by others in the defined order. Within the same inventory status group, products are further sorted by the sort order number assigned to them in the category.

![The master catalog category details page with the products with different inventory statuses and sort order, and the storefront page that reflects the enabled sorting behavior](user/img/system/config_commerce/catalog/category-products-sorting.png)
* **Sort Search Results by Inventory Status** — When enabled, the items on the search results page in the storefront will be sorted by their inventory status, as configured under the Products > Product Attributes back-office menu. Products with higher-priority statuses (e.g., *In Stock*) will appear first, followed by others in the defined order.

![The storefront page that reflects the enabled sorting behavior, where the products with higher-priority status *In Stock* appear first](user/img/system/config_commerce/catalog/search-results-sorting.png)
* **Sort Product Collection by Inventory Status** — When enabled, the items in product collections in the storefront will be sorted by their inventory status, as configured under the Products > Product Attributes back-office menu. Products with higher-priority statuses (e.g., *In Stock*) will appear first, followed by others in the defined order. Within the same inventory status group, products are further sorted by the sort order number assigned to them in the product collection.

![The web catalog content node details page with the assigned product collection and the storefront page that reflects the enabled sorting behavior](user/img/system/config_commerce/catalog/product-collection-sorting.png)
1. Click **Save Settings**.
