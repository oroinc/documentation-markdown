<a id="concept-guide-master-catalog"></a>

# Master Catalog Management Concept Guide

Setting up a [master catalog](../../../back-office/products/master-catalog/index.md#user-guide-master-catalog) may be one of the first steps of your OroCommerce journey. One OroCommerce [organization](../../../back-office/system/user-management/organizations/index.md#user-management-organizations) always has only **one master catalog** that structures all existing products in your store by categories to help you organize what you are selling. By configuring a particular set of product options, visibility, and SEO settings for each master catalog category, you enforce a unified selling strategy.

It is a good idea to create product [categories](../../../back-office/products/master-catalog/index.md#user-guide-master-catalog-category-creation) before populating the master catalog with products. You can then either add the products manually or import them in bulk by uploading a .csv list of all products. You can adjust your .csv file to the OroCommerce’s template and import it to the master catalog. Once you import the products, they are displayed on the product list page (grid) in the back-office and inside their respective master catalog categories. It is important to remember that one product can reside only in one category of the master catalog.

![The default product options details page](user/img/products/master_catalog/catalog_product_options.png)

#### HINT
In OroMarketplace, organizations are represented by sellers. While they can see the master catalog’s structure and place their products into its categories, they cannot affect it, as the master catalog is predefined by the administrator of the marketplace owner organization. For more information, see the [Marketplace Concept Guide](../../business-models/marketplace/index.md#concept-guide-oro-marketplace).

## Master Catalog in a Multi-Org Application

#### NOTE
The multi-org functionality is only available in the Enterprise edition.

Each [organization](../../../back-office/system/user-management/organizations/index.md#user-management-organizations) is an independent organism with a separate inventory, products, and the organization configuration options that may or may not fall back to the [system configuration](../../../back-office/system/configuration/index.md#mc-system-configuration). That is why the master catalog is never replicated in other organizations. Whenever you create a new organization in the same OroCommerce application, a blank category **All Products** is automatically added to the master catalog as a placeholder for your product structure, so you could create and configure a new master catalog specific to this organization.

Consider each available organization in your OroCommerce application as an umbrella that covers one master catalog, multiple web catalogs, and enables you to share products across all websites that belong to this organization.

![Illustration of a multi-org application](user/img/products/master_catalog/mc_multi-org.png)

## Master VS Web Catalog

Although they may sound similar, a master and a [web catalog](../../../back-office/marketing/web-catalogs/index.md#user-guide-web-catalog) are not quite the same. While the master catalog is responsible for the organization of a product collection inside the company, a web catalog is used to display products to customers on the website. Unlike the master catalog, one organization can have multiple web catalogs.

The master and the web catalog share some terminology, namely a product, a category, and a product collection.

- A product and a product collection. The master and web catalogs share the same product collection but unlike the former, a web catalog can have the same product in multiple categories.
- A category. You can add any master catalog product category to a [content node of a web catalog](../../../back-office/marketing/web-catalogs/edit-content-tree/index.md#user-guide-web-catalog-edit-content-tree), adding various localization, website or customer restrictions to it.

The master catalog organizes, categorizes, and stores the details of all your products (even those that you may not want to sell immediately), and a web catalog helps present these products in a personalized way that fits your target audience, website, or sales strategy. Think of a master catalog as a storage room, and a [web catalog](../../../back-office/marketing/web-catalogs/index.md#user-guide-web-catalog) as your shop window (of which you can have more than one). You keep all your products in the storage room but display only some of them in a specific way and order in the shop windows.

Please be aware that the master catalog product structure impacts the way products are displayed in the OroCommerce storefront only if there is no [web catalog](../../../back-office/marketing/web-catalogs/index.md#user-guide-web-catalog) or if no web catalog is connected to your website. This behavior is the same, regardless of the organization.

#### IMPORTANT
For more information on how to create master catalog categories and import product collection, refer to the [Master Catalog Back-Office Guide](../../../back-office/products/master-catalog/index.md#user-guide-master-catalog). For information on building web catalogs, refer to the [Web Catalogs Back-Office Guide](../../../back-office/marketing/web-catalogs/index.md#user-guide-web-catalog)

**Related Topics**

* [Master Catalog](../../../back-office/products/master-catalog/index.md#user-guide-master-catalog)
* [Manage Product Visibility](../../../back-office/products/products/managing-product-visibility.md#products-product-visibility)
* [Web Catalogs](../../../back-office/marketing/web-catalogs/index.md#user-guide-web-catalog)
* [Build a Custom Web Catalog From Scratch](../../../back-office/marketing/web-catalogs/build-from-scratch.md#user-guide-marketing-web-catalog-sample)
* [Use Web Catalog Nodes as Root Nodes](../../../back-office/marketing/web-catalogs/web-catalog-nav-tool-usecase.md#user-guide-web-catalog-navigation-tool)

**Further Practice**

* <a href="https://academy.oroinc.com/course/fundamental-orocommerce/" target="_blank">Fundamental OroCommerce Online Course</a>
