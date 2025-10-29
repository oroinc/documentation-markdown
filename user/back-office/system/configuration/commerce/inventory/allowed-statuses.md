<a id="configuration-guide-commerce-configuration-inventory-allowed-statuses"></a>

# Configure Allowed Statuses Settings (Inventory Status Constrains)

#### HINT
This section is part of the [Inventory and Warehouse Management](../../../../../concept-guides/catalog-promotions/inventory/index.md#concept-guide-inventory) topic that provides a general understanding of the inventory and warehouse concepts.

You can control the way product inventory is displayed for your buyers (in the storefront) and sales people (in the back-office). Moreover, you can restrict adding products with particular inventory status to an RFQ, customer order, quote, or a shopping list.

To change the default inventory statuses:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Inventory > Allowed Statuses** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Inventory allowed statuses system configuration](user/img/system/config_commerce/inventory/AllowedStatuses.png)
3. Customize any of the options by clearing the **Use Default** box next to the option. Click on the inventory status to select/deselect it. Press Shift and click to select/deselect a range of items. Press Ctrl and click to select/deselect multiple items in no particular order.
4. In the **Storefront** section, the following options are available:
   * **Visible Inventory Statuses** - A buyer can see products with the selected inventory statuses in the OroCommerce storefront.
   * **Can Be Added To RFQs** - A buyer can add Products with the selected inventory statuses when creating an RFQ in the OroCommerce storefront.
   * **Can Be Added To Orders** - A buyer can add Products with the selected inventory statuses when creating an Order in the OroCommerce storefront.

   #### HINT
   This configuration is also available [on the website level](../../../websites/web-configuration/commerce/inventory/website-allowed-statuses.md#allowed-statuses-website).
5. In the **Inventory Filter**, you can allow storefront users to filter products by the Inventory statuses, while allowing administrators to prevent revealing unwanted inventory details:
   * **Enable For Guests** - enable or disable the ability to show the inventory filter to unauthenticated visitors.
   * **Inventory Filter Type** - select the type of inventory filter to display. The *Multi-Select* filter type enables users to filter by any combination of individual inventory statuses. The *Simple* type will allow to filter only by predefined inventory statuses when the filter is applied. For this type, select the statuses that will be considered as *In Stock* in the storefront in the *In Stock Statuses For Simple Filter* field below.

   #### HINT
   This configuration is also available on the [organization](../../../user-management/organizations/org-configuration/commerce/inventory/organization-allowed-statuses.md#inventory-allowed-statuses-org) and [website](../../../websites/web-configuration/commerce/inventory/website-allowed-statuses.md#allowed-statuses-website) levels.
6. In the **Management Console** section, the following options are available:
   * **Can Be Added To Quotes** - A sales person can add products with the selected inventory statuses to the Quotes using OroCommerce back-office.
   * **Can Be Added To RFQs** - A sales person can add products with the selected inventory statuses to the RFQs using OroCommerce back-office.
   * **Can Be Added To Orders** - A sales person can add products with the selected inventory statuses to the Orders using OroCommerce back-office.
   * **Can Be Added To Shopping Lists** - A sales person can add products with the selected inventory statuses to the Shopping Lists using OroCommerce back-office.

1. Click **Save Settings**.

Once the default statuses are defined, you can then change the status manually directly from the [all inventory levels page](../../../../inventory/manage-levels.md#user-guide-inventory-manage-levels) or [per each product](../../../../products/products/create-simple.md#create-simple-product-inventory) individually.
