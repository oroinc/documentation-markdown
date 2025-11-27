<a id="products-products-create-product-kit"></a>

# Create a Product Kit

#### HINT
This section is part of the [Product Management](../../../concept-guides/catalog-promotions/product-management/index.md#concept-guides-product-management) topic that provides a general understanding of the product concept in OroCommerce.

A product kit is a grouping of products that you can sell together as a bundle.

To create a new product kit:

1. Navigate to **Products > Products** in the main menu.
2. Click **Create Product**.
3. Select the **Kit** product type from the dropdown.
   ![Selection of the kit product type](user/img/products/products/kits/product-type-kit.png)
4. Select the [product family](../product-families/index.md#products-product-families) to define the product options and details that will be filled in the following steps.
5. Place the product under the necessary category in the master catalog by clicking on the category. Use the search to limit the list of categories.
6. Click **Continue**.
7. Fill in the product details, as described in the topic on [creating a simple product](create-simple.md#products-products-create-simple-product).
8. In the **Kit Items** section, you can add as many kit items and products to the kits as necessary. For each kit item you add, you can provide the following details:
   ![Fields in the kit items section](user/img/products/products/kits/kit-items.png)
   * **Label** – Provide name for the kit item. It will be displayed in the back-office kit section, as well as [in the storefront when configuring the kit](../../../storefront/orders/kits.md#storefront-guide-orders-kits) and adding it to the shopping list.
   * **Sort Order** – Set the sort order to set the order in which kits are displayed in the storefront compared to other available kits. The lower is the number, the higher is the priority.
   * **Optional** – Indicates whether this kit item is required for purchase, or can be skipped by the customer.
   * **Minimum Quantity** – The minimum number of products a customer can purchase as part of the kit.
   * **Maximum Quantity** – The maximum number of products a customer can purchase as part of this kit.
   * **Unit of Quantity** – Select the [product unit](product-units/index.md#user-guide-products-product-units-in-use) for the product kit items. Available options: *each*, *item*, *kilogram*, *piece*, *set*.

   #### HINT
   You can expand or collapse each Kit Item section to display or hide the details of the product(s) that come as part of the kits.
   ![Collapsing and expanding the product kit section](user/img/products/products/kits/collapse-expand.gif)
   <br/>

   You can also drag and drop products in the kit section to a different position:
   <br/>
   ![Dragging and dropping products in the kit](user/img/products/products/kits/drag-drop.gif)
9. In the **Shipping Options** section, define how fixed shipping costs should be calculated for the selected product kit (available starting from OroCommerce v6.0.4). The field is only applied when calculating [Fixed Product Shipping](../../system/integrations/shipping-integration/fixed-shipping.md#doc-integration-fixed-shipping-cost) costs for product kits. The field has the following options:
   * **Kit product and kit items** (Default) — Shipping costs are calculated based on the combined shipping parameters of both the main product kit and its individual items.
   * **Only kit product itself** — Shipping costs are calculated exclusively on the shipping parameters of the main product kit, ignoring the individual items within the kit.
   * **Only kit items** — Shipping costs are calculated exclusively based on the shipping parameters of the individual items within the kit, ignoring the main kit product itself.

Provide unit, weight, and weight measuring unit, dimensions (width, height, depth), and dimensions measuring unit and freight class for the selected product kit.

![Shipping options details on the product kit edit page](user/img/products/products/kits/kit-shipping-options.png)
1. When you are ready to save the product, click **Save and Close**.

#### HINT
You can choose to sell an item exclusively as part of the kit, and not separately. To hide it from buyers in the storefront, change the product’s [visibility settings](managing-product-visibility.md#products-product-visibility) to **Hidden**. Customers will still be able to [purchase it](../../../storefront/orders/kits.md#storefront-guide-orders-kits) but only as part of the selected kit.

**Related Topics**

* [Product Kits Concept Guide](../../../concept-guides/catalog-promotions/product-management/kits-concept.md#concept-guides-product-management-kits)
* [Tax Calculation in Kits](../../../../bundles/commerce/TaxBundle/index.md#bundle-docs-commerce-tax-bundle-kits)
