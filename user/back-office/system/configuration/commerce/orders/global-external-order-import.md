<a id="system-configuration-orders-external-order-import"></a>

# Configure Global External Order Import Settings

#### HINT
The External Order Import feature can be enabled globally and [per organization](../../../user-management/organizations/org-configuration/commerce/orders/organization-external-order-import.md#configuration-commerce-orders-external-order-import-org).

The External Order Import feature enables administrators to access a complete order history by importing legacy orders in JSON format. This feature is especially useful for businesses migrating from ERP systems or consolidating historical data.

#### IMPORTANT
Please consider the following when working with imported external orders:

* This feature supports **import only**. Export of legacy order data is not available.
* Imported orders are marked as **This order has been imported from the ERP**. Administrators cannot edit these orders after import.
* Tax calculations, promotional discounts, and payment transactions are not available for legacy orders.
* All order line items are imported as *free-form line items*. They will link to products only if the product SKU in the import file matches an existing product SKU.
* Line items without matching SKUs will still be imported but may not be accurately reflected in *Previously Purchased* widgets, *Best Sellers* reports, or similar analytics.

![External Order Import configuration settings and the appeared Import File button on the Orders page](user/img/system/config_commerce/order/external-order-import.png)

To enable this feature globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Orders > External Order Import** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

1. In the **External Order Import** section:
   1. Clear the **Use Default** checkbox to adjust the system settings.
   2. Select the checkbox next to **Enable JSON Order Import** to enable the feature.
   3. Once enabled, the **Import file** button appears on the Open Orders page in the back-office for administrators to [upload a JSON file containing the legacy order data](../../../../sales/orders/external-orders-import.md#user-guide-sales-orders-external-orders-import). A sample file is available for download to guide formatting and structure.
2. Click **Save Settings**.
