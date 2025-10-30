<a id="configuration-guide-commerce-configuration-inventory-warehouses"></a>

# Configure Global Warehouses Settings

#### HINT
This section is part of the [Inventory and Warehouse Management](../../../../../concept-guides/catalog-promotions/inventory/index.md#concept-guide-inventory) topic that provides a general understanding of the inventory and warehouse concepts.

After you [created several warehouses](../../../../inventory/create.md#user-guide-inventory-warehouse-create) in the **Inventory > Warehouses** section, you should enable and prioritize them to ensure that OroCommerce uses the most efficient and recommended strategy for inventory updates that happen during the Store operations.

#### NOTE
The ability to configure warehouses is only available in the Enterprise edition.

To enable and prioritize warehouses:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Inventory > Warehouses** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global warehouses configuration settings](user/img/system/config_commerce/inventory/Warehouses.png)
3. Enable as many warehouses as you need:
   > 1. If necessary, click **+Add Warehouse**.
   > 2. Select the warehouse name in the *Choose a Warehouse* list.
   > 3. Assign a numeric priority to the enabled warehouse (1 is higher, 100 is lower).
   >    Products will be ordered and shipped from the higher priority warehouses first.

#### NOTE
You can manage the list of enabled warehouses using the following actions:

* To disable a warehouse, click **x** to the right of the priority.
* To clear the selected warehouse, click **x** to the right of the warehouse name.
* To select different warehouse from the list, click **v** to the right of the warehouse name, and select a new warehouse to enable.
* To see the complete list of the warehouses in a table view, click **bars** sign to the right of the warehouse name. The list of warehouses opens in a popup window.

1. Once all warehouses are enabled and prioritized, click **Save Settings**.
