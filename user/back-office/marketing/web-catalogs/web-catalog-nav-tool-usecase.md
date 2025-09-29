<a id="user-guide-web-catalog-navigation-tool"></a>

# Use Web Catalog Nodes as Root Nodes (Example)

You can select any content node as a root node for the OroCommerce storefront menu. This enables you to display only the necessary sub-menu nodes in the storefront menu.

As an illustration, we will create a category and add it as a separate block on the storefront homepage as part of the featured menu. The block will lead to a product listing page with many discounted items. The product listing page will not be part of the main menu and will only be available via a link from the new featured menu block on the homepage (e.g., Special Offers).

To configure such behavior, follow the steps outlined in the sections below.

#### NOTE
The following illustration involves configuration options that may only be modified by an administrator or a person with permission to access system configuration settings.

## Step 1: Configure the Navigation Root

Define the navigation root for the main menu so that the only relevant categories are displayed in the storefront instead of the whole web catalog tree:

1. Navigate to **System > Websites > Routing** in the main menu.
2. In the [Navigation Root](../../system/configuration/system/websites/global-routing.md#sys-config-sysconfig-websites-routing) field, select a content node as the root for building the navigation tree in the storefront.
   ![Navigation root system configuration](user/img/marketing/web_catalogs/navigation_root/navigation_root_config.png)
3. Click **Save Settings** .

Once the navigation root scope is defined, the main menu in the storefront should display the sub-menus only from the selected navigation root range.

#### NOTE
Keep in mind that the *Navigation Root* option appears in the routing configuration settings when you clear the **Use Default** checkbox next to the *Web Catalog* field, select the necessary web catalog from the list (if you have more than one), and click **Save Settings**.

## Step 2: Add a Content Node

Create a new content node and add all the items eligible for your special offers:

1. Navigate to **Marketing > Web Catalogs** in the main menu.
2. Click **Create Content Node** outside of the *Navigation Root* range and provide it with a name (e.g., Special Offers). The URL slug is automatically generated, but you can modify it if necessary.
   ![Creating a content node outside of the navigation root](user/img/marketing/web_catalogs/navigation_root/content_node_outside_nav_root.png)
3. In the **Content Variants** section, add *Product Collection* as a [content variant](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant) for the node you are creating, and populate it with the items for sale. In the example below, we have applied an existing <a href="https://academy.oroinc.com/media-library/create-segments" target="_blank">segment</a> (New Arrivals/Lightning Products) to the product collection we are adding as a content variant.

   #### NOTE
   See the [Add a Product Collection (Web Catalog Content)](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-product-collection) topic for more details.

   ![Product collection content node](user/img/marketing/web_catalogs/navigation_root/product_collection_segment.png)
4. Click **Save**.

## Step 3: Add a Frontend Menu Item

Add a new menu item to the existing featured menu block in the storefront:

1. Navigate to **System > Frontend Menus** in the main menu.
2. Click once on the *featured_menu* item to open its page.
3. Click **Create Menu Item**.

   #### NOTE
   See the [Edit a Frontend Menu](../../system/frontend-menus/edit-frontend-menu.md#user-guide-system-menu-menu-frontend) topic for more information on frontend menu configuration.
4. Name the menu item, and paste the URL slug of the content node you created in step 2 (e.g.,/special-offers). Once you append the URL, clicking on this block on the homepage will lead to the collection of products on offer.
5. Add an icon or an image to the menu item (optional).
   ![A new frontend menu item added to the featured menu in the back-office](user/img/marketing/web_catalogs/navigation_root/new_frontend_menu_item_console.png)
6. Click **Save**.

   The block should now be displayed on the storefront homepage.
   ![A new frontend menu item added to the featured menu in the storefront](user/img/marketing/web_catalogs/navigation_root/featured_menu_block_storefront.png)

   Clicking on the *Special Offers* block will redirect you to a dedicated page excluded from the main menu with the collection of items selected for sale.
   ![Special offers page in the storefront](user/img/marketing/web_catalogs/navigation_root/storefront_product_collection.png)

**More on Web Catalogs**

* [Build a Custom Web Catalog From Scratch (Example)](build-from-scratch.md#user-guide-marketing-web-catalog-sample)
* <a href="https://academy.oroinc.com/course/fundamental-orocommerce/" target="_blank">Fundamental OroCommerce Online Course</a>
* <a href="https://academy.oroinc.com/course/content-management/" target="_blank">Content Management Online Course</a>
* <a href="https://www.youtube.com/watch?v=SlW73esqBpk" target="_blank">OroCommerce's Video Tutorial: How to Create a web Catalog</a>
* <a href="https://oroinc.com/b2b-ecommerce/blog/training-thursday-customizable-web-catalogs-orocommerce" target="_blank">OroCommerce Blog: Customizable Web Catalogs in OroCommerce</a>
