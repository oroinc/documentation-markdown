<a id="user-guide-customer-groups-customer-settings"></a>

# Configure Product Data Export per Customer Group

You can control whether to allow registered customer users to export products, their prices, and price tiers into a .csv file from the storefront product collection and search results pages. You can configure these settings [globally](../../../../../system/configuration/commerce/product/global-customer-settings.md#sys-commerce-product-customer-settings), per [organization](../../../../../system/user-management/organizations/org-configuration/commerce/product/organization-customer-settings.md#sys-users-organization-commerce-products-customer-settings), [website](../../../../../system/websites/web-configuration/commerce/product/website-customer-settings.md#sys-websites-commerce-products-customer-settings), customer group, and [customer](../../../../customers/customer-configuration/commerce/product/customer-product-settings.md#user-guide-customers-customer-settings).

#### HINT
In addition to configuring product grid export on the configuration levels mentioned above, you can mark “simple” fields of a product as [Exportable](../../../../../system/entities/entity-fields/entity-fields-advanced-properties.md#admin-guide-create-entity-fields-advanced). You can also [mark a price attribute as Enabled in Product Export](../../../../../products/price-attributes/index.md#user-guide-products-price-attributes-manage). The *exportable* setting is available for all “simple” fields (scalar values and select/multi-select enums) of the product entity. Export is not allowed for relations, other complex fields (“WYSIWYG”, attachments, etc.), and entityfallback-type fields. Please note that the product name is always included in the export.

![Export product data from the storefront product collection page](user/img/storefront/navigation/export.png)

To configure product data export settings per customer group:

1. Navigate to **Customers > Customer Groups** in the main menu.
2. For the necessary customer group, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary group and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.

![Configuration settings for a customer group](user/img/customers/customer_groups/customer-group-config.png)
1. Select **Commerce > Products > Customer Settings** in the menu to the left.

![Product data export configuration options on customer group level](user/img/customers/customer_groups/customer-settings-config.png)
1. Enable the following options by clearing the **Use Website** checkbox next to the required option:
   * **Enable Product Grid Export** — Enable this option to allow customers in the storefront to export selected product data. Once you enable this option and click **Save Settings** on the top right, options **Include Product Prices** and **Include Price Tiers** will be displayed.
   * **Include Product Prices** — Enable this option to add product prices to the exported product data file. Data will be displayed only for the primary unit, minimum quantity, and the currency currently selected in the storefront.
   * **Include Price Tiers** — Enable this option to include price tiers in the exported product data file, if available. Product units will be omitted in the exported file if they have no price.
2. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
