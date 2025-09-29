<a id="sys-conf-commerce-catalog-special-pages-website"></a>

# Configure All Products Page per Website

#### HINT
This section is part of the [Product Management](../../../../../../concept-guides/product-management/index.md#concept-guides-product-management) topic that provides a general understanding of the product concept in OroCommerce.

In your Oro back-office, you can enable and configure the All Products page for the OroCommerce storefront. When configured, such page should display all available products from the master catalog grouped by categories.

## Flow

To configure the All Products page:

1. Enable **All Products Page** in system configuration on the required level — [globally](../../../../configuration/commerce/catalog/global-all-products.md#sys-conf-commerce-catalog-special-pages-global) or per website (see below).
2. Add it to the storefront as part of either your [web catalog](../../../../../marketing/web-catalogs/edit-content-tree/content-variants.md#user-guide-marketing-web-catalog) (**Marketing > Web Catalog**) or frontend menu (**System > Frontend Menus**) on the required level:
   * [Globally](../../../../frontend-menus/global-all-products-menus.md#sys-conf-frontend-menus-all-products-global) (**System > Frontend Menus**)
   * [Per organization](../../../../user-management/organizations/organization-all-products-menus.md#sys-users-organization-menus-all-products-organization) (**System > User Management > Organizations**)
   * [Per website](../../../website-all-products-menu.md#sys-users-organization-menus-all-products-website) (**System > Websites**)
   * [Per customer group](../../../../../customers/customer-groups/customer-group-all-products-menus.md#user-guide-customers-customer-groups-all-products) (**Customers > Customer Group**)
   * [Per customer](../../../../../customers/customers/customer-all-products-menus.md#user-guide-customers-customers-all-products) (**Customers > Customers**)
3. Check the [example of adding the All Products page](#user-guide-all-products-sample) for your reference.

#### NOTE
Please note that it is recommended to enable the All Products page exclusively for *small catalogs* with no more than a few hundred products, otherwise browser performance might be affected.

## Enable All Products Page per Website

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Catalog > Special Pages** in the panel to the left.
   ![image](user/img/system/websites/web_configuration/AllProductsWebsite.png)
4. Clear the **Use Organization** checkbox to change the organization-wide setting.
5. In the **All Products** section, select the **Enable All Products Page** checkbox.
6. Click **Save Settings** on the top right of the page.

<a id="user-guide-all-products-sample"></a>

## An Example of Adding All Products Page

As an illustration, let us add a sample All Products page to the storefront of the Europe website as a standalone page in the Quick Access menu.

![image](user/img/products/all_products_page/SampleAllProducts1.png)

For this, first enable the All Products page in the system:

1. Navigate to **System > Websites**.
2. For *Europe*, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> more actions menu, and click <i class="fas fa-cog" aria-hidden="true"></i>.
3. Select **Commerce > Catalog > Special Pages** in the panel to the left.
4. In the **All Products** section, select the **Enable All Products Page** checkbox.
   ![image](user/img/products/all_products_page/SampleAllProducts3.png)
5. Click **Save Settings**.

Next, add the page to the quick access menu:

1. Navigate to **System > Websites**.
2. Click once on the *Europe* website to open its page.
3. On the website page, click <i class="fas fa-cog" aria-hidden="true"></i> **Edit Frontend Menu** to start editing the configuration.
4. Click once on the commerce_quick_access menu.
   ![image](user/img/products/all_products_page/SampleAllProducts5.png)
5. Click **Create Menu Item** on the top right.
   ![image](user/img/products/all_products_page/SampleAllProducts6.png)
6. Fill in the required fields:
   * **Title**: All Products
   * **URL**: /catalog/allproducts
   * Select an icon from the list

   ![image](user/img/products/all_products_page/SampleAllProducts8.png)
7. Click **Save** on the top right to save the changes.

The All Products page should now be available as part of the Quick Access menu in the storefront of the Europe website.

#### NOTE
Please note, that the products unassigned to a category will be listed first, followed by those which belong to a category.

![image](user/img/products/all_products_page/SampleAllProducts7.png)

Similarly, you can add the All Products page to the menus of your choice.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
