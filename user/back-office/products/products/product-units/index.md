<a id="user-guide-products-product-units-in-use"></a>

# Manage Product Units in the Back-Office

#### HINT
This section is part of the [Product Management](../../../../concept-guides/product-management/index.md#concept-guides-product-management) topic that provides a general understanding of the product concept in OroCommerce.

A [Product Unit](../../../../glossary.md#term-Product-Unit) represents a measurement system of products or their combinations. All products in OroCommerce must have a product unit assigned to them for the customer users to be able to add items to the shopping list and determine their quantity in the OroCommerce storefront. Product units are also used throughout the system for inventory and pricing control. Each product in OroCommerce can be assigned multiple units with custom pricing added to each particular product unit.

Out-of-the-box, OroCommerce offers the following product units:

* each
* hour
* item
* kilogram
* piece
* set

By default, *each* is set as the primary product unit, but you can mark any available unit as primary in the [system configuration](../../../system/configuration/commerce/product/product-units.md#sys-commerce-product-product-units).

#### NOTE
You cannot add new product units or modify the existing ones from the OroCommerce back-office UI, but this can be achieved [with the help of the API](../../../../../api/index.md#web-services-api).

## Single and Multiple Product Units

#### HINT
See the article on [creating a new product](../index.md#doc-products-actions-create) with step-by-step explanations and illustrations of the process, including adding product units.

You can add one or multiple units to a single product when creating new products or through import.

Although the primary unit must always be added to a product, multiple units can be used to sell products in different weight or size options. For instance, sugar can be sold loose in *kilograms* or in packs of 5kg in *items*.

To add additional units when creating a new product or editing an existing one, click **+Add** next to the **Additional Units** field and select the desired unit from the list.

![Additional product unit](user/img/products/products/add_additional_product_unit.png)

You will be prompted to provide unit details, such as unit precision and conversion rate, and mark them for sale in the storefront or keep them invisible for internal usage. You need to provide these details for every additional unit you add to a product, including prices to be displayed to customer users in the storefront.

#### NOTE
Keep in mind that to be able to add multiple product units to products, the **Single Product Unit Mode** must be disabled in the system configuration.

### Determine Unit Precision

You can determine any desired precision for each product unit selected for the product. Precision represents the number of digits after the decimal point for the number of products a customer can order or add to the shopping list. Although *items* and *sets* are usually whole numbers (5, 6, 15), units like *kilograms* may require specific precision. For instance, you may set precision to 2, which would allow buying a custom volume of kilograms and grams, such as 0.5 kg or 10.95 meters.

When no product unit precision is selected (i.e. it is left at 0), this means that the unit is represented by a whole number.

### Set Unit Conversion Rate

When you select additional units of quantity, you can set a conversion rate compared to the primary unit of quantity selected for the product.

Have a look at how the Unit of Quantity and Additional Units fields are filled in the following example:

![Primary and additional product unit added to a new product](user/img/products/products/product_unit_primary_additional.png)
* The **Unit of Quantity** field is set to a *kilogram* with a **Precision** of 2.
* The **Additional Units** field is set to an *item* with a **Precision** remaining a zero and the **Conversion Rate** set to 5 kg. This means that one item contains 5 kgs of sugar if we convert one unit into another.

Another example is for a product with 3 units: *item, set and kilogram*, where *an item* is the primary unit that equals 0.5 kg., *a set* contains 10 items, and *a kilogram* is 2 items.

![Two additional units added to the product](user/img/products/products/three_units_per_product.png)

#### NOTE
Please keep in mind that unit conversion in the OroCommerce storefront does not happen automatically, e.g., if a set is 10 items and the customer adds 10 items to the shopping list, items are not converted into sets. Units are selected manually in the storefront.

### Control Unit Visibility: Sell

You can control the visibility of product units in the storefront by enabling or disabling the *Sell* checkbox next to the required product unit when creating or editing a product.

When *Sell* is enabled for a product unit, this makes the unit visible to the customer users in the storefront when they are viewing this product. When *Sell* is disabled, the product unit is only visible in the back-office and is hidden from the customer users in the OroCommerce storefront.

![Enables sell checkbox for a product unit](user/img/products/products/sell_checkbox_for_product_unit.png)

Keeping product units visible only for internal operations in the back-office might come in handy in many situations. For instance, if you buy your products in bulk in kilograms but sell them in items and sets, it makes sense to hide *kilograms* as a product unit option from the storefront and only use it for internal wholesale purchases.

Alternatively, while preparing sets of certain items for a holiday season sale, you might want to keep them hidden from the storefront until the actual sale day; you can, however, still track these sets through warehouses and add prices to them.

### Manage Product Units in Pricing

You can add custom and tier pricing to every product unit of a specific product.

For example, if you sell paint brushes in items and sets, you can specify the dollar amount for the specific quantity that you want to sell. In the following example, 1 set contains 5 items (i.e., the conversion rate for *set* is 5).

![Paintbrushes are sold in items and sets](user/img/products/products/example_brushes_items_sets.png)

The product units available for pricing in the **Product Prices** section depend on the units selected for the product in the **General** section.

#### NOTE
Prices can be added manually when creating or editing a product or through import. See the section on [price lists in OroCommerce](../../../sales/price-lists/index.md#user-guide-pricing-pricelist-management) for more information and examples.

![Tier pricing for a product in items and sets](user/img/products/products/tier_pricing_units.png)

As the screenshot illustrates, pricing for each quantity and product unit variation is added separately, depending on your pricing strategy.

In the storefront, the tiered pricing is reflected in the following way:

![The tier pricing for the Paint Brush product displayed in the storefront](user/img/products/products/tier_pricing_storefront.png)
* If you buy 1 item, it would cost you $9.50 for 1 piece.
* If you buy 10 items, the price per item is lowered to $9.10
* If you buy 50 items, the price per item is lowered further to $8.99

However, if you buy the same product in sets, the price is even lower:

* If you buy 1 set, 1 item within it goes for $8.80
* If you buy 10 sets, 1 item within the set goes for $8.6.

Depending on the quantity selected for the product unit, **Your Price** in the storefront will be different.

**Listed Price** is the pricing assigned to the available product units and their variations of quantity. **Your Price** is the *Listed* price under your current tier pricing configuration.

For instance:

* For 1 brush, your price is $9.50 per item, the same as the listed price.
  ![Your price and listed price are the same in the storefront](user/img/products/products/your_listed_pricing_equal.png)
* However, if you choose 50 items, your price is recalculated to $8.99 because this is the tier pricing set for the quantity of 50 brushes.
  ![Your price and listed price are different because the pricing tier is applied](user/img/products/products/your_price_recalculated_after_tier_application.png)
* The same goes for sets:

![Your price is recalculated for sets](user/img/products/products/your_price_recalculated_sets.png)

#### HINT
See another example of the difference between [Your Price and Listed price in the storefront](../../../../storefront/getting-started/common-controls.md#frontstore-guide-navigation-product-price).

### Use Units in Promotions

Two types of promotions, *Order Line Items* and *Buy X Get Y (Same Product)* require a unit of quantity added to the promotion setup. To ensure that the promotion is going to be successfully triggered, the units of products added to the promotion must correspond to the units of quantity selected for the products. The promotion that offers you to buy 10 *pairs* of contact lenses and get 1 *pair* for free will not be triggered if the products (contact lenses) added to the promotion are sold as *each* or *set*.

#### NOTE
A *pair* here is used for illustration purposes, this unit does not come out-of-the-box.

Suppose the product added to the promotion has more than one product unit. In that case, the promotion will be triggered if, in the storefront, the customer user selects the product unit defined in the promotion’s conditions. For instance, if contact lenses are sold both in *each* and *pair* but the promotion is configured to be triggered for *pairs*, then no discount will be provided for customers who add the same product to the shopping list in *each*.

#### NOTE
If you want the promotion to be applied to all available units of one product, you need to create separate promotions with each of these additional units.

For more information, check out the [Promotions](../../../marketing/promotions/promotions/index.md#user-guide-marketing-promotions) topic.

## Product Units in Inventory

Each product unit assigned to a product is listed on the inventory list, where product quantity can be managed and adjusted for the required warehouse. If one product is sold in several units, all these units are displayed in the inventory table.

![Product units displayed in the inventory table](user/img/products/products/units_inventory.png)

More inventory information is available in the [Warehouse and Inventory](../../../inventory/index.md#user-guide-inventory) section.

#### BUSINESS TIP
## Business Tip

Looking for a digital commerce solution for B2B? Research and compare <a href="https://oroinc.com/b2b-ecommerce/b2b-ecommerce-comparison" target="_blank">B2B eCommerce platforms</a> in our comparison chart.

**Related Topics**

* [Configure Product Units](../../../system/configuration/commerce/product/product-units.md#sys-commerce-product-product-units)
* [Understand Products’ Life Cycle](../index.md#doc-products-before-you-begin)
