<a id="sys-commerce-product-customer-settings"></a>

# Configure Global Customer Settings for Product Data Export

You can control whether to allow registered customer users to export products, their prices, and price tiers into a .csv file from the storefront product collection and search results pages. You can configure these settings globally, per [organization](../../../user-management/organizations/org-configuration/commerce/product/organization-customer-settings.md#sys-users-organization-commerce-products-customer-settings), [website](../../../websites/web-configuration/commerce/product/website-customer-settings.md#sys-websites-commerce-products-customer-settings), [customer group](../../../../customers/customer-groups/customer-group-configuration/commerce/product/customer-group-product-customer-settings.md#user-guide-customer-groups-customer-settings), and [customer](../../../../customers/customers/customer-configuration/commerce/product/customer-product-settings.md#user-guide-customers-customer-settings).

#### HINT
In addition to configuring product grid export on the above mentioned configuration levels, you can mark “simple” fields of a product as [Exportable](../../../entities/entity-fields/entity-fields-advanced-properties.md#admin-guide-create-entity-fields-advanced). You can also [mark a price attribute as Enabled in Product Export](../../../../products/price-attributes/index.md#user-guide-products-price-attributes-manage). Exportable setting is available for all “simple” fields (scalar values and select/multi-select enums) of the product entity. Export is not allowed for relations, other complex fields (“WYSIWYG”, attachments, etc.) and entityfallback-type fields. Please note that product name is always included in the export.

![Export product data from the storefront product collection page](user/img/storefront/navigation/export.png)

To configure these settings globally:

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Customer Settings** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Product data export configuration options on global level](user/img/system/config_commerce/product/global-product-export.png)
1. Enable the following options by clearing the **Use Default** checkbox next to the required option:
   * **Enable Product Grid Export** — Enable this option to allow customers in the storefront to export selected product data. Once you enable this option and click **Save Settings** on the top right, options **Include Product Prices** and **Include Price Tiers** will be displayed.
   * **Include Product Prices** — Enable this option to add product prices to the exported product data file. Data will be displayed only for the primary unit, minimum quantity and the currency currently selected in the storefront.
   * **Include Price Tiers** — Enable this option to include price tiers to the exported product data file, if available. If product units have no price, they will be omitted in the exported file.
2. If you have a <a href="https://extensions.oroinc.com/orocommerce/extension/customer-part-number/" target="_blank">Customer Part Number</a> extension installed, enable it here under **Customer Part Number** to allow customers to manage CPN per product.
3. Click **Save Settings**.
