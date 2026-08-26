<a id="user-guide-customers-customer-settings"></a>

# Configure Customer Settings per Customer

The **Customer Settings** configuration page brings together several settings that apply to storefront customers and how they can obtain product information. This section covers two groups of settings available here at the customer level:

* **Product Data Export** — Controls whether this customer’s registered users can export products, their prices, and price tiers into a .csv file from the storefront product collection and search results pages.
* **Customer Part Number** — Controls whether [customer part numbers](../../../../../products/customer-part-numbers/index.md#back-office-customer-part-numbers) are displayed to this customer’s users in the storefront.

You can configure these settings [globally](../../../../../system/configuration/commerce/product/global-customer-settings.md#sys-commerce-product-customer-settings), per [organization](../../../../../system/user-management/organizations/org-configuration/commerce/product/organization-customer-settings.md#sys-users-organization-commerce-products-customer-settings), [website](../../../../../system/websites/web-configuration/commerce/product/website-customer-settings.md#sys-websites-commerce-products-customer-settings), [customer group](../../../../customer-groups/customer-group-configuration/commerce/product/customer-group-product-customer-settings.md#user-guide-customer-groups-customer-settings), and customer.

#### HINT
In addition to configuring product grid export on the configuration levels mentioned above, you can mark “simple” fields of a product as [Exportable](../../../../../system/entities/entity-fields/entity-fields-advanced-properties.md#admin-guide-create-entity-fields-advanced). You can also [mark a price attribute as Enabled in Product Export](../../../../../products/price-attributes/index.md#user-guide-products-price-attributes-manage). Exportable setting is available for all “simple” fields (scalar values and select/multi-select enums) of the product entity. Export is not allowed for relations, other complex fields (“WYSIWYG”, attachments, etc.), and entityfallback-type fields. Please note that the product name is always included in the export.

To configure customer settings per customer:

1. Navigate to **Customers > Customers** in the main menu.
2. For the necessary customer, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.
3. Select **Commerce > Product > Customer Settings** in the menu to the left.

![Product data export configuration options on customer level](user/img/customers/customers/customer-settings-config.png)
1. Under **Product Data Export**, enable the following options by clearing the **Use Customer Group** checkbox next to the required option:
   * **Enable Product Grid Export** — Enable this option to allow customers in the storefront to export selected product data. Once you enable this option and click **Save Settings** at the top right, options **Include Product Prices** and **Include Price Tiers** will be displayed.
   * **Include Product Prices** — Enable this option to add product prices to the exported product data file. Data will be displayed only for the primary unit, minimum quantity, and the currency currently selected in the storefront.
   * **Include Price Tiers** — Enable this option to include price tiers in the exported product data file, if available. Product units will be omitted in the exported file if they have no price.
2. Under **Customer Part Number**, enable the following option by clearing the **Use Customer Group** checkbox:
   * **Display Customer Part Numbers In The Storefront** — Enable this option to let customers view their own part numbers in the storefront (e.g., on the product listing, search results, and product details pages), as well as create, delete, and filter by them. This option has no effect on its own unless option **Enable Customer Part Numbers** is [enabled on the global level](../../../../../system/configuration/commerce/product/global-customer-settings.md#sys-commerce-product-customer-settings).
3. Click **Save Settings**.

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
