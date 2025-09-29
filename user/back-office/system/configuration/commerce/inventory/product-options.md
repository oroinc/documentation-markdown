<a id="configuration-guide-commerce-configuration-inventory-product-options"></a>

<a id="sys-conf-commerce-inventory-product-options"></a>

<a id="sys-conf-commerce-inventory-product-options-global"></a>

# Configure Global Product Options Settings

#### HINT
This section is part of the [Inventory and Warehouse Management](../../../../../concept-guides/inventory/index.md#concept-guide-inventory) topic that provides the general understanding of the inventory and warehouse concepts.

You can control the way product inventory is managed for every product in the OroCommerce product catalog on multiple levels – globally, [per organization](../../../user-management/organizations/org-configuration/commerce/inventory/organization-product-options.md#sys-conf-commerce-inventory-product-options-organization), [per website](../../../websites/web-configuration/commerce/inventory/website-product-options.md#sys-conf-commerce-inventory-product-options-website), [per product](../../../../products/products/create-simple.md#create-simple-product-inventory), and [per master catalog category](../../../../products/master-catalog/index.md#master-catalog-inventory).

To customize the default product options globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Inventory > Product Options** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global product options configuration](user/img/system/config_commerce/inventory/product_options_global.png)

Here, you can manage both inventory and upcoming products options.

**Product Inventory Options**

> | Name                        | Description                                                                                                                                                                                                                                                                                                                            |
> |-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | **Managed Inventory**       | This options indicates whether the product inventory is handled by OroCommerce vs external application.                                                                                                                                                                                                                                |
> | **Inventory Threshold**     | A minimum quantity of the product that is treated as *In stock*. When a product quantity reaches this threshold value, the product inventory status falls back to *Out Of Stock*.                                                                                                                                                      |
> | **Backorders**              | A flag that indicates whether OroCommerce accepts backorders (available for the Enterprise edition only). When set to yes, buyers and sales people can order products in the quantities that are not currently available in the warehouses. The remaining portion of the order will be sustained until the product gets back in stock. |
> | **Decrement Inventory**     | A flag that indicates whether OroCommerce decrements inventory upon order. When both **Decrement Inventory** and **Backorders** are enabled, product quantity may get negative.                                                                                                                                                        |
> | **Highlight Low Inventory** | This option indicates whether wholesale buyers are able to see that there might not be enough product left in stock for their purchase.                                                                                                                                                                                                |
> | **Low Inventory Threshold** | The minimum stock level defined for the product. Reaching the defined level will trigger a warning message to the buyer in the storefront.                                                                                                                                                                                             |

<a id="upcoming-products-config"></a>

**Upcoming Products**

**Hide Labels Past Availability Date** - When enabled, the label for the upcoming products will be removed automatically once the availability date has passed. If the option is disabled, the label will remain displayed as long as the product is marked as upcoming regardless of its availability date.

1. To customize any of these options:
   > 1. Clear the **Use Default** check box next to the option.
   > 2. Select **Yes/No** for the flag-like options, and type in the updated value for the threshold-like options.
2. Click **Save Settings**.
