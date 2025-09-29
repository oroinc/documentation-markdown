<a id="doc-products-before-you-begin"></a>

# Manage Products in the Back-Office

<!-- begin_product_configuration -->

#### HINT
This section is part of the [Product Management](../../../concept-guides/product-management/index.md#concept-guides-product-management) topic that provides a general understanding of the product concept in OroCommerce.

The flow for creating and managing products may vary depending on the needs of your business, whether you have small-scale operations or complicated product characteristics and visibility settings. With the help of OroCommerce flexible product management system, configuring products is simple to achieve. However, it may not be obvious where to start. This section is here to guide you through the process and refer you to suitable topics.

## Prepare for Product Creation

OroCommerce supports both product attributes and product families. Product attributes are configurable parameters for a product, such as product size, color, brand, name, inventory status, and the like. They can be arranged into a product family, a group of related attributes to be displayed as a titled section at the OroCommerce storefront. Both product components are used when creating simple and configurable products. A special price attribute helps you store the price-related information that may be easily reused when you plan the prices on the website.

With this information in mind, here are the references to the elements that need to be created and/or configured before you proceed to create an actual product in OroCommerce:

* [Create product units](product-units/index.md#user-guide-products-product-units-in-use) — to select the primary product unit and its precision.
* [Create product families](../product-families/index.md#products-product-families) and [product attributes](../product-attributes/index.md#products-product-attributes) — to design a structure for product information and give the product-specific characteristics, such as color or size.
* [Create price attributes](../price-attributes/index.md#user-guide-products-price-attributes) — to add custom parameters where you can store the price-related information (e.g., MSRP) that may be used in the rule-based price lists to calculate the price for the buyer.

<a id="doc-products-actions-create"></a>

## Create Your Products

Next, you can proceed to create products. You can create two types of products in OroCommerce, [simple](../../../glossary.md#term-Simple-Product) and [configurable](../../../glossary.md#term-Configurable-Product).

Simple products are physical items that exist in a primary, single variation. Their qualifiers, such as color or size, cannot be modified, meaning customers cannot select the same product with slightly different characteristics. Simple products have a unique SKU and serve as ‘building blocks’ for configurable products.

Unlike a simple product, a configurable product is an item available in multiple variations. Customers ‘configure’ the product in terms of its color, size, or any other applicable parameters according to buying needs. A configurable product with all its different attributes (e.g., size and color variations) is displayed in the storefront as a matrix ordering form.

* [Create a simple product](create-simple.md#products-products-create-simple-product)
* [Create a configurable product](create-complex.md#products-products-create-config-product)
* [Set up a matrix form and variations of a configurable product](../../system/configuration/commerce/product/global-configurable-products.md#config-guide-landing-commerce-products-configurable-products)

## Control Your Products

Once you have created products, you can:

* Discover what basic and advanced actions you can apply to products in the back-office in the [Products Grid](manage/index.md#doc-products-characteristics) section.
* Proceed to manage the way products are displayed in the storefront, as described in the [Highlight and Illustrate Products in the Storefront](../../../concept-guides/product-management/index.md#highlight-products-on-the-storefront) section.
* Learn how to manage your product quantities and product prices in the [Manage the product inventory quantity](manage/manage-inventory.md#doc-products-actions-manage-inventory) and [Manage product pricing](manage/view-product-prices.md#view-and-filter-product-prices) topics.

<!-- finish_product_configuration -->
