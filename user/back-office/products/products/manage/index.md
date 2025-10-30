<a id="doc-products-characteristics"></a>

<a id="doc-products-actions-view-list"></a>

# Product Grid

In this section, you will learn how to control and manage product information displayed in the product grid.

In the main menu, navigate to **Products > Products**. The product list opens.

The following information about products is available in the product list.

| Field                                 | Description                                                                                                                                                                                   |
|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SKU                                   | The [stock keeping unit](../../../../glossary.md#term-Stock-keeping-unit-SKU) that helps identify the product and track it for inventory.                                                     |
| NAME                                  | The name of the product and how it appears on the user interface.                                                                                                                             |
| INVENTORY STATUS                      | Whether the product is in stock, out of stock, or discontinued.                                                                                                                               |
| STATUS                                | Whether the product is enabled or disabled.                                                                                                                                                   |
| CREATED AT                            | The date and time when the product was created.                                                                                                                                               |
| UPDATED AT                            | The date and time when the product was last updated.                                                                                                                                          |
| PRICE (<Currency>) *Multiple columns* | The product pricing information per unit of quantity. There is an individual column for each currency in which you have defined the price.                                                    |
| Price Attributes *Multiple columns*   | The additional price information that may be useful for determining the product pricing strategy (e.g., MSRP, MAP). There is an individual column for each price attribute and each currency. |
| TAX CODE                              | The code that helps identify what taxes to apply to the product.                                                                                                                              |
* To control the product information displayed in the list, click <i class="fa fa-cog fa-lg" aria-hidden="true"></i> **Settings** on the top right of the list, and in the dialog that appears, select which column to display.
* To filter product information by value, click <i class="fa fa-filter fa-lg" aria-hidden="true"></i> **Filter** on the top right of the list, and in the filter section that appears, select the required values.
* To display pricing information related only to a particular price list, select the price list from the **Price List** list in the left panel, or click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> next to it to select the price list using the dialog.
* To display/hide pricing information related to the particular currency, select/clear the checkbox next to the name of the corresponding currency in the left panel.
* To display/hide tier prices, in the left panel, select/clear the **Show Tier Prices** checkbox.
  > ![Select the checkboxes next to the required currency](user/img/products/products/ProductsFilterPrices.png)
* To display products that belong to a particular category, navigate to the required category in the left panel and click it. Use search to locate the category quickly.
* To display/hide the product from the sub-categories, select/clear the **Include Sub-Categories** checkbox in the left panel.
  > ![Select a product category and the Include Su-Categories checkbox](user/img/products/products/ProductsCategories.png)

## Core Product Management

You can perform the following actions for a specific product from the grid:

* [Create a product](../index.md#doc-products-actions-create) by clicking the corresponding button on the top right.
* [Export](../export-products.md#export-products) and [import](../import-products.md#import-products) the necessary product information.

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the required product’s row, and select whether to

* [View a product](view.md#doc-products-actions-view)
* [Edit a product](edit.md#doc-products-actions-edit-fromgrid)
* Duplicate <i class="far fa-copy" aria-hidden="true"></i> a product. The duplicated product opens. It has the **Disabled** status, and its SKU is automatically generated by adding a hyphen and a duplicate version number to the original SKU. You can edit the duplicated product to customize its settings as required.
* Delete <i class="fas fa-trash-alt" aria-hidden="true"></i> a product. To delete multiple products, select the checkboxes in front of the products you need to delete, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu, and then click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete**. To select the bulk of items quickly, use *All* (to select all products) or *All Visible* (to select only products visible on the page now) from the list above the checkboxes.

![The actions a user can perform from the product's grid](user/img/products/products/ProductGridActions.png)

## Advanced Product Management

* [Manage Product Visibility](../managing-product-visibility.md#products-product-visibility)
* [Manage Product Quantities in the Inventory](manage-inventory.md#doc-products-actions-manage-inventory)
* [Manage Product Pricing](view-product-prices.md#view-and-filter-product-prices)
* [Manage Product Page Design with Page Templates](../page-templates.md#user-guide-page-templates)
* [Highlight and Illustrate Products in the Storefront](../../../../concept-guides/catalog-promotions/product-management/index.md#highlight-products-on-the-storefront) by managing the following items:
  * Product Images (watermark, image gallery, and preview)
  * Featured Products
  * New Arrivals
  * Brands
  * Related Products
  * Up-Sell Products

#### NOTE
You can also view the complete reference of [product-related settings in system configuration](../../../system/configuration/commerce/product/index.md#configuration-products).

* [View Product Details](view.md)
* [Edit a Product](edit.md)
* [Manage Product Pricing](view-product-prices.md)
* [Manage Inventory](manage-inventory.md)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
