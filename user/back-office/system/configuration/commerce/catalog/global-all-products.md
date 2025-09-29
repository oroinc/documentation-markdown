<a id="sys-conf-commerce-catalog-special-pages"></a>

<a id="sys-conf-commerce-catalog-special-pages-global"></a>

# Configure Global Special Pages (All Products) Settings

#### HINT
This section is part of the [Product Management](../../../../../concept-guides/product-management/index.md#concept-guides-product-management) topic that provides a general understanding of the product concept in OroCommerce.

In your Oro back-office, you can enable and configure the All Products page for the OroCommerce storefront. When configured, such page should display all available products from the master catalog grouped by categories.

> ![The All Products page on the OroCommerce storefront](user/img/system/config_commerce/catalog/all_products_page.png)

## Flow

To configure the All Products page:

1. Enable **All Products Page** in system configuration on the required level — globally (see below) or [per website](../../../websites/web-configuration/commerce/catalog/website-all-products.md#sys-conf-commerce-catalog-special-pages-website).
2. Add it to the storefront as part of either your [web catalog](../../../../marketing/web-catalogs/edit-content-tree/content-variants.md#user-guide-marketing-web-catalog) (**Marketing > Web Catalog**) or frontend menu (**System > Frontend Menus**) on the required level:
   * [Globally](../../../frontend-menus/global-all-products-menus.md#sys-conf-frontend-menus-all-products-global) (**System > Frontend Menus**)
   * [Per organization](../../../user-management/organizations/organization-all-products-menus.md#sys-users-organization-menus-all-products-organization) (**System > User Management > Organizations**)
   * [Per website](../../../websites/website-all-products-menu.md#sys-users-organization-menus-all-products-website) (**System > Websites**)
   * [Per customer group](../../../../customers/customer-groups/customer-group-all-products-menus.md#user-guide-customers-customer-groups-all-products) (**Customers > Customer Group**)
   * [Per customer](../../../../customers/customers/customer-all-products-menus.md#user-guide-customers-customers-all-products) (**Customers > Customers**)
3. Check the [example of adding the All Products page](../../../websites/web-configuration/commerce/catalog/website-all-products.md#user-guide-all-products-sample) for your reference.

#### NOTE
Please note that it is recommended to enable the All Products page exclusively for *small catalogs* with no more than a few hundred products, otherwise browser performance might be affected.

## Enable All Products Page Globally

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Catalog > Special Pages** in the panel to the left.
   ![All Products global configuration settings](user/img/system/config_commerce/catalog/AllProductsSystem.png)
3. In the **All Products** section, select the **Enable All Products Page** checkbox.
4. Click **Save Settings** on the top right of the page.
