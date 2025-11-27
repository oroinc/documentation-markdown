<a id="bundle-docs-commerce-product-bundle-product-lists"></a>

# Customize Product Lists

Product lists are used to show lists of products grouped by some criteria, for example, new arrival products, featured products, top selling products, up-sell products, etc.

The data for these lists are loaded from the [website search index](../../WebsiteSearchBundle/index.md#bundle-docs-commerce-website-search-bundle).
This was done to avoid unnecessary hydration of product entities, which is quite expensive and requires
a lot of database requests.

The main entry point to the product lists is <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Provider/ProductListBuilder.php" target="_blank">ProductListBuilder</a>. This builder creates a base query to load products
from website search index, executes this query and converts the result to a list of <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Model/ProductView.php" target="_blank">ProductView</a> objects.
To be able to customize which data should be loaded, this builder dispatches the following events:

* class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Event/BuildQueryProductListEvent.php" target="_blank">BuildQueryProductListEvent</a>, event name: `oro_product.product_list.build_query`.
* class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Event/BuildQueryProductListEvent.php" target="_blank">BuildQueryProductListEvent</a>, event name: `oro_product.product_list.build_query.PRODUCT_LIST_TYPE`.
* class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Event/BuildResultProductListEvent.php" target="_blank">BuildResultProductListEvent</a>, event name: `oro_product.product_list.build_result`.
* class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Event/BuildResultProductListEvent.php" target="_blank">BuildResultProductListEvent</a>, event name: `oro_product.product_list.build_result.PRODUCT_LIST_TYPE`.

`PRODUCT_LIST_TYPE` here is a unique string that identifies each type of product list.
The following product list types are available out-of-the-box:

* `new_arrivals` for the list of [new arrivals products](../../../../user/back-office/system/configuration/commerce/product/global-promotions.md#sys-commerce-product-new-arrivals).
* `featured_products` for the list of [featured products](../../../../user/back-office/system/configuration/commerce/product/global-featured-products.md#sys-commerce-product-featured-products).
* `top_selling_items` for the list of top selling products.
* `related_products` for the list of [related products](../../../../user/back-office/system/configuration/commerce/catalog/global-related-products.md#sys-commerce-catalog-relate-products).
* `upsell_products` for the list of [up-sell products](../../../../user/back-office/system/configuration/commerce/catalog/global-related-products.md#sys-commerce-catalog-upsell-products).
* `similar_products` for the list of [similar products](../../../../user/back-office/system/configuration/commerce/catalog/global-related-products.md#sys-commerce-catalog-similar-products).
* `product_mini_block` for a product displayed in [“Product Mini Block” content widget](../../../../user/concept-guides/content-management/content-widgets.md#concept-guide-content-widgets).
* `segment_products` for the list of products displayed in [“Product Segment” content widget](../../../../user/concept-guides/content-management/content-widgets.md#concept-guide-content-widgets).

These events provide a possibility to customize all product lists and a particular product list.

<!-- Frontend -->
