<a id="concept-guide-inventory"></a>

# Inventory and Warehouse Management Concept Guide

With e-commerce marketing increasing dramatically and products selling online more frequently than ever before, it is vital for businesses to keep track of their inventory, know where their products are, whether they are overstocked, in stock, or out of stock, and organize proper workflows to ensure that all processes run effectively.

OroCommerce provides an essential kit of features to help manage and monitor your inventory and storage, providing a number of benefits to online sellers:

**1. Stock quantities are always up-to-date**

When a buyer submits an order, OroCommerce synchronizes stock levels immediately in real-time both in the storefront and the back-office, which prevents overselling products in the warehouse. This way, you know exactly how much inventory you have, accurately forecast demand, and prevent overselling, which ultimately increases your cash flow.

**2. Inventory synchronization across multiple warehouses and websites**

OroCommerce Enterprise edition supports [multiple warehouses](../../../back-office/inventory/index.md#user-guide-inventory) and [multiple websites](../../business-models/websites/index.md#website-management-concept-guide) features. It means that you can create an unlimited number of websites required for your business and assign each of them a dedicated warehouse. You can also bind several warehouses to a single website. The perks of the OroCommerce application is that the inventory numbers are synced across all the channels you sell products on which enables you to track orders, inventory, and relationships across websites and warehouses, partners and wholesalers within one convenient system.

![A list of all inventory levels](user/img/concept-guides/inventory/inventory_registry.png)

**3. Various options for managing inventory**

OroCommerce comes with a number of essential features that enhance inventory management and help control quantities of stock in the catalog to avoid running out. By customizing the settings, you can decide whether to allow buyers to purchase the products that are not yet available in stock or set the threshold values, which, if reached, will notify buyers of the insufficient product quantity in the storefront. You can also set the minimum and maximum amounts that can be purchased in a single order. You can find more information on inventory options [further below](#concept-guide-inventory-options).

**4. Forecasting trends and customer demands**

The number of product items you ship and keep in stock tells you about purchasing and seasonal trends, as well as dynamic customer demands. With OroCommerce out-of-the-box inventory management system, you can get the necessary data insights to build custom [reports](../../../back-office/reports-segments/reports/index.md#user-guide-reports) to have a closer look at your existing stock, the most frequently ordered items, category performance, or how customer needs are changing. Vendors can use the reports to forecast procurements more precisely.

**5. Supporting third-party inventory solutions**

OroCommerce provides a robust data structure to handle inventory management that would suit many companies well. However, it is not a dedicated inventory and storage tracking solution. For some companies, it can be enough. But if your business requires more advanced functionality, on top of what you get out-of-the-box, you may need to install a full-featured inventory and warehouse management software. OroCommerce is compatible with many fully-featured WMS and inventory solutions that you can have seamlessly integrated via our powerful API (for example, <a href="https://www.marello.com/" target="_blank">Marello ERP</a>).

Once you decide which system to use, reflect your choice in the product inventory options configuration by enabling or disabling the full OroCommerce inventory management functionality.

![Global managed inventory functionality](user/img/concept-guides/inventory/manage_inventory_functionality.png)

## Inventory Status VS Inventory Level

Inventory statuses and inventory levels in OroCommerce are interconnected.

**Inventory status** defines whether a product is in stock, out of stock, or discontinued. You can select what product status to display to buyers in the storefront and restrict adding the products with a particular status to RFQs, orders, quotes, or shopping lists. These settings can be configured on the [system](../../../back-office/system/configuration/commerce/inventory/allowed-statuses.md#configuration-guide-commerce-configuration-inventory-allowed-statuses) and [website](../../../back-office/system/websites/web-configuration/commerce/inventory/website-allowed-statuses.md#allowed-statuses-website) levels.

![Global allowed statuses option configuration](user/img/concept-guides/inventory/global_allowed_statuses_config.png)

Defining the statuses that can be applied to products enables you to switch between them manually on the [inventory levels page](../../../back-office/inventory/manage-levels.md#user-guide-inventory-manage-levels) or [per product](../../../back-office/products/products/create-simple.md#create-simple-product-inventory).

![Adjusting inventory status per product](user/img/concept-guides/inventory/product_inventory_status.png)

**Inventory levels** are the quantities of products with a particular inventory status in every operating warehouse. The inventory levels page compiles and stores all inventory statistics in one centralized location. The information is pulled from all available sources and channels on a real-time basis allowing you to make informed decisions on sales and marketing strategies.

![Adjusting inventory levels from the inventory registry page](user/img/concept-guides/inventory/edit_inventory_levels.png)

You can adjust product quantity both from the [inventory levels page](../../../back-office/inventory/manage-levels.md#user-guide-inventory-manage-levels) and [per product](../../../back-office/inventory/manage-levels.md#doc-products-actions-manage-inventory-per-product), wherever it is convenient.

![Adjusting the quantity from a specific product's page](user/img/concept-guides/inventory/manage_inventory_levels_per_product.png)

<a id="concept-guide-inventory-options"></a>

## Inventory Options

Configuring inventory options allows the inventory to run automatically in the expected customized behavior. It means that once the options are set up, you no longer have to worry about adjusting product quantities after every placed order, notifying customers of any insufficient or out-of-stock products or the pushed back delivery dates. OroCommerce enables you to configure the inventory options on different levels, [global](../../../back-office/system/configuration/commerce/inventory/product-options.md#sys-conf-commerce-inventory-product-options-global), [per organization](../../../back-office/system/user-management/organizations/org-configuration/commerce/inventory/organization-product-options.md#sys-conf-commerce-inventory-product-options-organization), [per website](../../../back-office/system/websites/web-configuration/commerce/inventory/website-product-options.md#sys-conf-commerce-inventory-product-options-website), [per product](../../../back-office/products/products/create-simple.md#create-simple-product-inventory), and [per master catalog category](../../../back-office/products/master-catalog/index.md#master-catalog-inventory),  covering various business requirements.

![Global product inventory options configuration](user/img/concept-guides/inventory/product_inventory_options.png)

Let’s elaborate on some of the options to clarify their distinctive features.

**Inventory Threshold**

Inventory threshold is the minimum quantity of product that you need to have on hand to take care of orders. You can define an inventory level that becomes the threshold to determine when an item needs to be marked as out-of-stock and/or reordered.

Let’s say you have 10 items of Product A in stock. You set the Inventory Threshold option to `1` (in case you prefer avoiding an entirely dead stock). It means that when there is one item left in stock, the system will automatically change the product inventory status to Out of Stock. With such configuration, your customer is allowed to purchase up to 9 items only.

![Display inventory statuses in the storefront](user/img/concept-guides/inventory/productA_inventory_status.png)

**Low Inventory**

You may want to warn your customers of low stock so they could adjust the quantity they want to purchase before proceeding to checkout. To configure this behavior, enable the **Highlight Low Inventory** option and define the quantity for **Low Inventory Threshold**. When the threshold is reached, the customers will be notified about low quantities of stock.

For instance, if you have 10 items left of product A, you may want to set the low inventory threshold to `3`. This means that when three items of this product are left in stock, a customer will see a warning of low inventory and can decide whether to proceed with the order or change the quantity.

![Display the low inventory label in the storefront](user/img/concept-guides/inventory/highlight_low_inventory.png)

**Upcoming Products**

If you want to inform your customers about an upcoming delivery of the items that are currently out of stock (or the stock is running low), you can add a corresponding note to [individual products](../../../back-office/products/products/create-simple.md#create-simple-product-inventory) or the [whole category](../../../back-office/products/master-catalog/index.md#master-catalog-inventory) by enabling the **Upcoming** option. To announce the exact date of product arrival, choose the date in the additional **Availability Date** field.

![Display the upcoming products label in the storefront](user/img/concept-guides/inventory/upcoming_products_note.png)

Disable the **Upcoming** option to remove the label for the upcoming products when you no longer need it. Alternatively, toggle the **Hide Labels Past Availability Date** option in the system configuration to define the general behavior of the note representation.

![Global upcoming products configuration settings](user/img/concept-guides/inventory/upcoming_products_global.png)

**Backorders**

The option determines whether OroCommerce Enterprise accepts backorders. Backorders do not affect order status processing. Payment is still authorized or captured once the order is submitted, regardless of whether the product is in stock. Products are shipped once they become available. The inventory level may get negative if **Backorders** and **Decrement Inventory** are enabled.

![Negative inventory level values](user/img/concept-guides/inventory/backorders.png)

**Decrement Inventory**

It is vital for businesses to know the final count of their inventory, and that the numbers adjust dynamically as orders are being placed through all the channels. For that, enable the option to decrement inventory on order submission to be always aware of the current data.

**Quantity Limitations**

To control the number of a product that a buyer can claim in the RFQ, quote, or purchase in a single order, you can set the related quantity limitations on different levels, [global](../../../back-office/system/configuration/commerce/inventory/limitations.md#configuration-guide-commerce-configuration-inventory-limitations), [per organization](../../../back-office/system/user-management/organizations/org-configuration/commerce/inventory/organization-limitations.md#inventory-limitations-org), [per website](../../../back-office/system/websites/web-configuration/commerce/inventory/website-limitations.md#inventory-limitations-website), [per product](../../../back-office/products/products/create-simple.md#create-simple-product-inventory), and [per master catalog category](../../../back-office/products/master-catalog/index.md#master-catalog-inventory)

![Global inventory limitations configuration settings](user/img/system/config_commerce/inventory/limitations.png)![Display the quantity limitations label in the storefront](user/img/concept-guides/inventory/quantity_limitations.png)

## Inventory Options Fallback

Inventory options can be configured on different levels. To help you understand the inventory option fallback hierarchy, have a look at the illustration of the logic below:

![Graphic illustration of the inventory options fallback logic](user/img/concept-guides/inventory/product_options_fallback.png)

In the default configuration, the options set on the product level always go first. It means that if a product has its unique inventory options configuration, these settings override the settings on all other levels.

However, product inventory settings can fall back to the master catalog category settings, inheriting its inventory configuration.

Category settings, in turn, can fall back to the parent category (if there is any), or to the website settings. Website settings fall back to the organization settings, and organization settings fall back to the system ones.

![Screenshots to illustrate the inventory options fallback logic](user/img/concept-guides/inventory/product_options_fallback_screens.png)

In other words, if you set the inventory options for the whole system, but your organization has a different configuration, the latter prevails. In case a website has its custom configuration, it overrides both the organization and global settings. Master catalog configuration overrides the website, organization, and global settings. An individual configuration set per product overrides the configuration set on all the aforementioned levels.

#### HINT
When adding a new organization, remember to update the [organization’s configuration settings](../../../back-office/system/user-management/organizations/index.md#user-management-organizations) (including its owner and a [warehouse](../../../back-office/system/user-management/organizations/org-configuration/commerce/inventory/organization-warehouses.md#warehouses-organization)).

**Related Topics**

* [Manage Inventory in the Back-Office](../../../back-office/inventory/index.md#user-guide-inventory)
* [Manage Warehouse in the Back-Office](../../../back-office/inventory/create.md#user-guide-inventory-warehouse-create)
* [Global Inventory Configuration](../../../back-office/system/configuration/commerce/inventory/index.md#configuration-guide-commerce-configuration-inventory)
* [Organization-specific Inventory Configuration](../../../back-office/system/user-management/organizations/org-configuration/commerce/inventory/index.md#configuration-commerce-inventory-organization)
* [Website-specific Inventory Configuration](../../../back-office/system/websites/web-configuration/commerce/inventory/index.md#configuration-commerce-inventory-website)
