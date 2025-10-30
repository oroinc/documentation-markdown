<a id="configuration-commerce-orders-external-order-import-org"></a>

# Configure External Order Import Settings per Organization

#### NOTE
The feature is available as of OroCommerce version 6.1.2.

#### HINT
The External Order Import feature can be enabled [globally](../../../../../configuration/commerce/orders/global-external-order-import.md#system-configuration-orders-external-order-import) and per organization.

The External Order Import feature enables administrators to access a complete order history by importing legacy orders in JSON format. This feature is especially useful for businesses migrating from ERP systems or consolidating historical data.

#### IMPORTANT
Please consider the following when working with imported external orders:

* This feature supports **import only**. Export of legacy order data is not available.
* Imported orders are marked as **This order has been imported from the ERP**. Administrators cannot edit these orders after import.
* Tax calculations, promotional discounts, and payment transactions are not available for legacy orders.
* All order line items are imported as *free-form line items*. They will link to products only if the product SKU in the import file matches an existing product SKU.
* Line items without matching SKUs will still be imported but may not be accurately reflected in *Previously Purchased* widgets, *Best Sellers* reports, or similar analytics.

To enable this feature per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Orders > External Order Import** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

1. In the **External Order Import** section:
   1. Clear the **Use Default** checkbox to adjust the system settings.
   2. Select the checkbox next to **Enable JSON Order Import** to enable the feature.
   3. Once enabled, the **Import file** button appears on the Open Orders page in the back-office for administrators to [upload a JSON file containing the legacy order data](../../../../../../sales/orders/external-orders-import.md#user-guide-sales-orders-external-orders-import). A sample file is available for download to guide formatting and structure.
2. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
