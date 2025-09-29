<a id="backend-frontend-menus"></a>

<a id="frontend-menus-overview"></a>

# Configure Storefront Menus in the Back-Office

#### HINT
This section is part of the [Storefront and Back-Office Menu Management Concept Guide](../../../concept-guides/menus/index.md#menu-management-concept-guide) topic that provides a general understanding of the available storefront and back-office menu types and their management in Oro applications.

In this section, you will learn how to edit and configure the storefront menu components in OroCommerce.

All the OroCommerce storefront menus are located in the main menu under **System > Frontend Menus**.

![A list of all storefront menu items](user/img/system/frontend_menu/frontend_menu_1.png)

Each menu type has a different purpose that is described in detail in the [Storefront and Back-Office Menu Management Concept Guide](../../../concept-guides/menus/index.md#menu-management-concept-guide).

## Permissions Required to Customize Storefront Menus

The ability to configure menus globally, per organization, and for personal use is controlled by the two capabilities: **Manage Menus** and **Access system configuration**.

By default, only users with Admin role have these capabilities enabled and may customize menus on all configuration levels.

To enable a user to personalise menus for themselves and configure menus for each organization individually, include the **Manage Menus** capability into the user role.

To enable a user to configure menus globally, for all organizations, websites, and users whose configuration fall back to the global settings, both **Manage Menus** and **Access system configuration** capabilities should be enabled for the user role.

![Capabilities that must be enabled for the role to be allowed to manage storefront menus](user/img/concept-guides/menus/menus_capabilities.png)

<a id="doc-system-menu-config-levels-frontend-menus"></a>

<a id="frontend-menu-globally"></a>

## Storefront Menus Configuration

In the Oro applications, you can customize the storefront menus look, and the elements they contain globally (see below), per organization, per website, per customer, and per customer group.

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/customize-front-end-menus" target="_blank">how to customize storefront menus in OroCommerce</a> or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/nNPLsSOUc1c" frameborder="0" allowfullscreen></iframe>

To configure a default storefront menu globally:

1. Navigate to **System > Frontend Menus** in the main menu.
2. Click on the menu you would like to edit.
3. Update the menu contents following the guidelines provided in the [Edit a Storefront Menu](edit-frontend-menu.md#user-guide-system-menu-menu-frontend) section.
   The changes apply automatically.

* [Customize Storefront Menus per Organization](../user-management/organizations/organization-frontend-menus.md#frontend-menu-organization)
* [Customize Storefront Menus per Website](../websites/website-frontend-menus.md#frontend-menus-website)
* [Customize Storefront Menus per Customer](../../customers/customers/customer-frontend-menus.md#frontend-menus-customer)
* [Customize Storefront Menus per Customer Group](../../customers/customer-groups/customer-group-frontend-menus.md#frontend-menus-customer-group)

## Storefront Menu Management

### Edit a Storefront Menu

A storefront menu may be multi-level, and the child menu items are nested under parent menu items (e.g., **About**, **Customer Service**, **Privacy Policy**, and others are nested under **Information**).

![Configuration settings of the About menu under the commerce_footer_links storefront menu](user/img/system/frontend_menu/frontend_menu_2.png)

Menu items on the same level of hierarchy may be visually separated by a divider that looks like a horizontal line and helps you logically organize menu items. However, some menus do not support displaying dividers (on a particular level in the tree, or in general).

![User menu without divider](user/img/system/menus/user_menu.png)

To update the storefront menu contents, navigate to **System > Frontend Menus** in the main menu and click the menu name or the <i class="fa fa-eye fa-lg" aria-hidden="true"></i> View icon in the corresponding row of the storefront menu list.

![A lust of available storefront menu items](user/img/system/frontend_menu/frontend_menu_1.png)

On the page that opens, the menu item tree is displayed in the left panel. The center is reserved for the menu item configuration.

#### Toggle the Storefront Menu Tree View

1. To minimize or maximize the left menu panel, click a double arrow on the top right of the panel.
2. To expand / collapse all menu items, click the ellipses drop-down menu on the top right of the left panel and click **Expand All** or **Collapse All**.
3. To expand / collapse a parent menu item, click an arrow in front of it.

![Numbers that define the actions you can do to storefront menu items described above](user/img/system/frontend_menu/frontend_menu_edit.png)

<a id="doc-config-menus-actions-draganddrop-frontend"></a>
1. To change the position of an item / divider in a menu, drag and drop it in the left panel. You can change the order of menu items at the same level as well as move an item / divider to the higher or lower level. When you drag-and-drop items, pay attention to the arrow that shows where the item will be placed:

- If an arrow points to the place between items, that is where the moved item will be placed.
  ![Dragging the Catalog menu under Shopping Rules](user/img/system/frontend_menu/d&dsame.png)
- If and arrow appears in front of a menu item, then the moved item will become a child of the item to which the arrow points.

#### Add a Menu Item

1. In the left panel, click a menu item that is going to be a parent for the menu item that you create.
2. Click **Create Menu Item** on the top right and then **Create Menu Item** from the dropdown list.

   The created menu item is displayed as the last one on the list of children of the same parent item. You can move it to the position that you need, as described in the [Toggle the Menu Tree View](../menus/index.md#doc-config-menus-actions-draganddrop) action description.
3. In the right part of the page, specify the following information:

* **Title** — A name for the menu item. This is how this menu item is going to be represented in the menu. Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. Click the <i class="fas fa-language" aria-hidden="true"></i> **Default Language** icon to return to the single-language view.
* **Target Type** — Select the target of the storefront menu item: a URI link, a content node, or a system page. The fields below vary depending on the target type you choose.

  | **URI**          | URI is a web address of the page or resource that this menu item opens. You can specify an absolute URI or one relative to the application URI (as specified in Application Settings in the System Configuration).                                                                     |
  |------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | **System Page**  | Select one of the standard pre-designed pages of the OroCommerce storefront.                                                                                                                                                                                                           |
  | **Content Node** | Select the [web catalog](../../marketing/web-catalogs/index.md#user-guide-web-catalog) from which you want to choose content node, and the [content node](../../marketing/web-catalogs/edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant) itself. |
  ![Select the target type for a storefront menu item](user/img/system/frontend_menu/target_type.png)

  #### HINT
  If this menu item serves as a non-clickable parent that does not link itself to any resource (like **Customers** in the default main menu), type  *#*.
* **Icon** — From the list, select the icon that denotes the menu item. Sometimes menus (or menu levels) may not be supposed to display icons. For example, icons added to the first level of the main menu are displayed only when this menu is set to appear on the left.
* **Description** — Type a short but meaningful description of the menu item. Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. Click the <i class="fas fa-language" aria-hidden="true"></i> **Default Language** icon to return to the single-language view.
* **User Agent** — A unique agent to every customer. It reveals a catalog of technical data about the device and software that the customer is using. You can control whether to show or hide some menu items from the customer by proceeding with the following steps:
  1. Click **+Add** next to the **User Agent** field.
  2. Fill in the text field with a user agent substring or a string, if required.

     #### NOTE
     A user agent string is a combination of user agent application versions, operating systems, crawlers, and other scripts that are specific for each user (e.g., Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.113 Safari/537.36).

     A user agent substring is part of the string mentioned above (e.g., Mozilla, Windows, Safari, etc).
     ![The settings under User Agent](user/img/system/frontend_menu/user_agent.png)
  3. Select the corresponding operation from the list.
     * The *contains* operation determines whether the specified substring is included in the user agent string (e.g., if you mention Mozilla, all the versions of Mozilla in the user agent string will meet the requirements of this function).
     * The *does not contain* operation determines whether the specified substring is not included in the user agent string.
     * The *matches* operation checks whether the specified value fully matches the user agent string (e.g., you need to provide a version of Mozilla to meet the requirements of this function).
     * The *does not match* operation checks when the specified value does not match the user agent string.

  > ![A list of available operations under User Agent](user/img/system/frontend_menu/frontend_menu_5.png)
  1. To create a more advanced condition, you can combine constraints into the expression using logical AND and OR operators:
     * Click **+ And** below the operation field within the same block to add another constraint block into the expression via AND.

       *AND* operation means that only those user agents that comply with all the specified conditions in a group will be selected.

     ![The steps you need to take to add another condition with AND operator to User Agent](user/img/system/frontend_menu/frontend_menu_6.png)
     * Click **+ Add** at the bottom of the expression block to add another constraint block into the expression via OR.

       *OR* operation activates the expression once any of the constraint blocks in a group evaluates to true.

     ![The steps you need to take to add another condition with OR operator to User Agent](user/img/system/frontend_menu/frontend_menu_7.png)
* **Exclude On Screens** — Enables you to hide the menu items on the specified screens sizes by clicking any screen size and selecting the one for which the menu will be hidden from the customer. Hold **Ctrl** and click the value to select/deselect multiple screens.
  > As an illustration, let us hide the **About** menu item from the desktops with a 13-inch screen by enabling **Exclude On Screens** and selecting the corresponding screen size.
  > ![Footer menu in the storefront illustrating the Exclude On Screens option both enabled and disabled](user/img/system/frontend_menu/frontend_menu_9.png)
* **Condition** — Enables you to restrict the visibility of a menu item using the following functions:
  * The *is_logged_in()* function stands for the *registered users*. If entered, only the users who have logged into the Oro storefront are enabled to view the corresponding menu item.
  * The  *!is_logged_in()* function stands for the *non-registered users*. If entered, only the unregistered users are enabled to view the corresponding menu item.
  * The *config_value(‘some_identifier’)* function limits visibility of the corresponding menu item upon specifying certain value instead of  *‘some_identifier’*. Keep in mind that to get the value for  *‘some_identifier’*, you need to ask the developer for assistance.

As an example, let us make the **About** section in the storefront visible to customers with configured taxes. For this, we need to:

> 1. Customize the *config_value(‘some_identifier’)* function with the required value instead of *some_identifier*. In our case, it is the *oro_tax.tax_enable* value.
> 2. Click **Save** on the top right of the About menu page to save the changes.
> 3. Enable **Tax Calculation** in the system configuration. More information on tax configuration can be found in the relevant [Configure Tax Calculation](../configuration/commerce/taxation/tax-calculation.md#user-guide-taxes-tax-configuration) topic.
> 4. Click **Save** on the top right of the Tax Calculation configuration page.

The steps are illustrated below:

![The steps you need to take to enable the About section to customers with configured taxes in the storefront](user/img/system/frontend_menu/frontend_menu_11.png)![The steps you need to take to disable the About section to customers with configured taxes in the storefront](user/img/system/frontend_menu/frontend_menu_12.png)
* **Target Window** — determines the way to open the linked document or URI. Select *Same Window* option to open it in the current browser window. Select *New Window* to open it in a new browser tab.
* **Image** — an image used to illustrate a new storefront menu. Click **Choose File** to select the image from your directory and upload it.

1. Click **Save** to save your changes. If you wish to start creating another menu item right away, click **Save and New** on the top right.

#### IMPORTANT
You need to reload the page to see the changes.

#### Add a Divider

1. In the left panel, click a menu item which will be the parent for the menu divider that you create.
2. Click **Create** drop-down on the top right, and select **Create Divider**.

![Highlight the Create Divider button under Create Menu Item](user/img/system/frontend_menu/menus_createdivider.png)

The created divider will appear as the last one on the list of children of the same parent item. You can move it to the position that you need, as described in the [Toggle the Menu Tree View](#doc-config-menus-actions-draganddrop-frontend) action description. Reload the page to see changes.

#### NOTE
Some menus (or some menu levels) cannot display dividers. For example, if you add a divider to the first level of the main menu (**application_menu**), this divider will not be displayed.

#### Toggle Item Visibility

1. **Hide a Menu Item** — To hide the default menu items from the interface, click the necessary menu item in the left panel. Click **Hide** on the top right. Reload the page to see changes.

   #### IMPORTANT
   - If a menu that you hide has child items, they will be hidden too.
   - You cannot hide non-default menu items.
2. **Show a Menu Item** — To show a previously hidden menu item, click the necessary menu item in the left panel. Click **Show** on the top right. Reload the page to see changes.

   #### NOTE
   If a menu item that you want to show has a parent, it will become visible too.
3. **Find a Menu Item** —  To quickly find a menu item, enter its name into the search field and click the <i class="fa fa-search fa-lg" aria-hidden="true"></i> **Search** icon or press **Enter**.
   ![Using the search tab to locate all references about sales](user/img/system/menus/menus_application_search.png)
4. **Delete a Menu Item / Divider** — To delete a menu item or a divider, click the necessary item in the left panel. Click **Delete** on the top right. In the **Delete Confirmation** dialog box, click **Yes, Delete**. Reload the page to see changes.

   #### IMPORTANT
   - You cannot delete default menu items.
   - When you delete a menu item that has child items, they will not be deleted but moved to the parent of the menu item that you delete.
5. **Reset a Menu** — To reset any customization changes and roll back to the menu that is provided out-of-the-box in the Oro application, click a menu name in the left panel. Click **Reset** on the top right. In the **Reset Confirmation** dialog box, click **Yes, Reset**. Reload the page to see changes.

## Add All Products Page to Storefront Menus Globally

Once the All Products page has been enabled in the system configuration [globally](../configuration/commerce/catalog/global-all-products.md#sys-conf-commerce-catalog-special-pages-global) or [per website](../websites/web-configuration/commerce/catalog/website-all-products.md#sys-conf-commerce-catalog-special-pages-website), you can add it to a storefront menu on the system level (globally):

1. Navigate to **System > Frontend Menus** in the main menu.
2. Click once on the menu to which you will add the All Products page.
3. Click **Create Menu Item** on the top right of the page.
4. In the **Title** field, type in the label for the menu item.
5. In the **URI** field, specify  */catalog/allproducts*.
6. Complete the other fields as required.
   ![Adding the All Products page to storefront menus globally](user/img/products/all_products_page/AllProductsMainMenu.png)
7. Click **Save** on the top right of the page.

The All Products page should now become available as part of the selected menu.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
