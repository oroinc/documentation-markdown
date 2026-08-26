<a id="sys-users-organization-commerce-products-customer-settings"></a>

# Configure Customer Settings per Organization

The **Customer Settings** configuration page brings together several settings that apply to storefront customers and how they can obtain product information. This section covers two groups of settings available here at the organization level:

* **Product Data Export** — Controls whether registered users can export products, their prices, and price tiers into a .csv file from the storefront product collection and search results pages.
* **Customer Part Number** — Controls whether [customer part numbers](../../../../../../products/customer-part-numbers/index.md#back-office-customer-part-numbers) are displayed to customers of this organization in the storefront.

You can configure these settings [globally](../../../../../configuration/commerce/product/global-customer-settings.md#sys-commerce-product-customer-settings), per organization, [website](../../../../../websites/web-configuration/commerce/product/website-customer-settings.md#sys-websites-commerce-products-customer-settings), [customer group](../../../../../../customers/customer-groups/customer-group-configuration/commerce/product/customer-group-product-customer-settings.md#user-guide-customer-groups-customer-settings), and [customer](../../../../../../customers/customers/customer-configuration/commerce/product/customer-product-settings.md#user-guide-customers-customer-settings).

#### HINT
In addition to configuring product grid export on the above mentioned configuration levels, you can mark “simple” fields of a product as [Exportable](../../../../../entities/entity-fields/entity-fields-advanced-properties.md#admin-guide-create-entity-fields-advanced). You can also [mark a price attribute as Enabled in Product Export](../../../../../../products/price-attributes/index.md#user-guide-products-price-attributes-manage). Exportable setting is available for all “simple” fields (scalar values and select/multi-select enums) of the product entity. Export is not allowed for relations, other complex fields (“WYSIWYG”, attachments, etc.) and entityfallback-type fields. Please note that product name is always included in the export.

To configure these settings per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.
3. Select **Commerce > Product > Customer Settings** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![Product data export configuration options on organization level](user/img/system/user_management/org_configuration/products/org-product-data-export.png)
4. Under **Product Data Export**, enable the following options by clearing the **Use System** checkbox next to the required option:
   * **Enable Product Grid Export** — Enable this option to allow customers in the storefront to export selected product data. Once you enable this option and click **Save Settings** at the top right, options **Include Product Prices** and **Include Price Tiers** will be displayed.
   * **Include Product Prices** — Enable this option to add product prices to the exported product data file. Data will be displayed only for the primary unit, minimum quantity and the currency currently selected in the storefront.
   * **Include Price Tiers** — Enable this option to include price tiers to the exported product data file, if available. If product units have no price, they will be omitted in the exported file.
5. Under **Customer Part Number**, enable the following option by clearing the **Use System** checkbox:
   * **Display Customer Part Numbers In The Storefront** — Enable this option to let customers view their own part numbers in the storefront (e.g., on the product listing, search results, and product details pages), as well as create, delete, and filter by them. This option has no effect on its own unless option **Enable Customer Part Numbers** is [enabled on the global level](../../../../../configuration/commerce/product/global-customer-settings.md#sys-commerce-product-customer-settings).
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
