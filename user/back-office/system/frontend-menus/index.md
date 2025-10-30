<a id="backend-frontend-menus"></a>

<a id="frontend-menus-overview"></a>

<a id="doc-system-menu-config-levels-frontend-menus"></a>

<a id="frontend-menu-globally"></a>

# Configure Storefront Menus in the Back-Office

#### HINT
This section is part of the [Storefront and Back-Office Menu Management Concept Guide](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide) topic that provides a general understanding of the available storefront and back-office menu types and their management in Oro applications.

Storefront menu in OroCommerce allows users to navigate your website and easily access product collections, their account, shopping cart, and other essential information. There are several types of menus available for the storefront, described in the [Storefront Menu Components section](../../../concept-guides/administration/menus/index.md#menu-management-concept-guide).

![A list of all storefront menu items](user/img/system/frontend_menu/frontend_menu_1.png)

You can customize the way your storefront menus look globally (see below), per organization, per website, per customer, and per customer group.

To configure a default storefront menu globally:

1. Navigate to **System > Frontend Menus** in the main menu.
2. Click on the menu you would like to edit.
3. Update the menu contents following the guidelines provided in the [Edit a Storefront Menu](edit-frontend-menu.md#user-guide-system-menu-menu-frontend) section.
   The changes apply automatically.

To learn how to configure them on other levels, follow the links below:

* [Customize Storefront Menus per Organization](../user-management/organizations/organization-frontend-menus.md#frontend-menu-organization)
* [Customize Storefront Menus per Website](../websites/website-frontend-menus.md#frontend-menus-website)
* [Customize Storefront Menus per Customer](../../customers/customers/customer-frontend-menus.md#frontend-menus-customer)
* [Customize Storefront Menus per Customer Group](../../customers/customer-groups/customer-group-frontend-menus.md#frontend-menus-customer-group)

## Configure Permissions to Customize Storefront Menus

The ability to configure menus globally, per organization, and for personal use is controlled by the two capabilities: **Manage Menus** and **Access system configuration**.

By default, only users with the Admin role have these capabilities enabled and may customize menus on all configuration levels.

To enable a user to personalise menus for themselves and configure menus for each organization individually, include the **Manage Menus** capability into the user role.

To enable a user to configure menus globally, for all organizations, websites, and users whose configuration fall back to the global settings, both **Manage Menus** and **Access system configuration** capabilities should be enabled for the user role.

![Capabilities that must be enabled for the role to be allowed to manage storefront menus](user/img/concept-guides/menus/menus_capabilities.png)

## Change a Storefront Menu

To learn how to manage a storefront menu and create new menu items, see [Change a Storefront Menu](edit-frontend-menu.md#user-guide-system-menu-menu-frontend).

## Add All Products Page to Menus Globally

To learn how to add  All Products Page  to a storefront menu globally after enabling it in, see [Add All Products Page to Storefront Menus](global-all-products-menus.md#sys-conf-frontend-menus-all-products-global)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
