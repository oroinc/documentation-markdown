<a id="menu-management-concept-guide"></a>

# Storefront and Back-Office Menu Management Concept Guide

Companies are now making huge efforts to attract visitors on their site, investing large sums of money in advertising and marketing. Once a customer lands on a page of your website, you must let them find the product on the fly with an easy and user-friendly navigation. Navigation is what welcomes your visitor once they arrive, providing an overview of what you offer, how to contact you, how to access the shopping cart, and make an order.

A navigation menu of an e-commerce website has a lot in common with the shelving in a physical store. When a customer enters your website, regardless of whether they come with a specific purpose or just to browse, they scan the content to find the information they are looking for. Whether they stay or leave highly depends on a responsive menu that helps customers identify the required location on the spot.

![Illustrate navigation principles of any website](user/img/concept-guides/menus/oro2_1.jpg)

Catering to the needs of your business, OroCommerce offers a useful solution to build the menu of your choice. The application provides several pre-configured menu items out-of-the-box that you can customize to fit your criteria. With the storefront and back-office menu functionality, you can personalize and optimize your site navigation for the convenient usage by customers in the storefront and administrators in the back-office.

![The lists of the default storefront and back-office menu items](user/img/concept-guides/menus/menus_overview_new.png)

As a visual reference, we have used the default OroCommerce theme to illustrate how the menu items are represented

* **in the storefront**
  ![Illustrate all available storefront menu items in the storefront](user/img/concept-guides/websites/frontend_menu.png)

<br/>
* **in the back-office**

![Illustrate all available back-office menu items in the back-office](user/img/concept-guides/menus/backend_menu.png)

The way the menu looks and behaves on your website depends on the customization and settings that you apply to the default configuration.

Let’s check each of the available menu items individually.

## Storefront Menu Components

[Storefront menu](../../back-office/system/frontend-menus/index.md#backend-frontend-menus) in OroCommerce allows users to orient themselves within your website and easily access their account, shopping cart, and other essential information through the links distributed in different places: next to the main menu, in the footer, in the featured menu, etc.

The storefront menu functionality consists of several components that are supplied with the necessary settings to make up the navigation of your website storefront and to enable visitors to know where they are, where they can go, and where they have already been. You can [modify the default configuration](../../back-office/system/frontend-menus/edit-frontend-menu.md#user-guide-system-menu-menu-frontend) to add new menu items, exclude some items from the specific devices, set visibility conditions to certain customer groups, or according to particular config values.

![A list of all available storefront menu items in the storefront](user/img/concept-guides/menus/frontend_menu_list.png)

You can configure each of the following menu elements on five different levels: [global](../../back-office/system/frontend-menus/index.md#frontend-menu-globally), [organization](../../back-office/system/user-management/organizations/organization-frontend-menus.md#frontend-menu-organization), [website](../../back-office/system/websites/website-frontend-menus.md#frontend-menus-website), [customer group](../../back-office/customers/customer-groups/customer-group-frontend-menus.md#frontend-menus-customer-group), and a [customer](../../back-office/customers/customers/customer-frontend-menus.md#frontend-menus-customer). Always keep an eye on the fallback logic, which means that the values set on a lower level (e.g., customer level) would always prevail and override the configuration set on the higher level.

![Storefront menu fallback logic](user/img/concept-guides/menus/frontend_menu_fallback.png)

### Frontend_menu

**Frontend_menu** serves to build the breadcrumbs based on the pages nesting. Breadcrumbs help identify the location of the user within your website’s hierarchy.

![A sample of the frontend_menu breadcrumbs in the storefront](user/img/concept-guides/menus/frontend_menu_sample.png)

However, keep in mind that the breadcrumbs on the product listing page and the product details page are made up based on the structure of the enabled **master catalog** or **web catalog nodes**, but not through **frontend_menu**.

![A sample of the breadcrumbs composed based on the structure of a web catalog](user/img/concept-guides/menus/webcatalog_breadcrumbs.png)

### Commerce_top_nav

The **commerce_top_nav** menu indicates the links that appear at the top right of your website’s page header. If your customers need to reach your business, add the links to live chat. If they are looking for your store locations, add that. Whatever is important to you can be added to the header.

![A sample of the commerce_top_nav menu in the storefront](user/img/concept-guides/menus/commerce_top_nav_sample1.png)

### Commerce_quick_access

The **commerce_quick_access** menu provides links to the most frequently used pages or important actions for the customers to quickly locate them within your website.

![A sample of the commerce_quick_access menu in the storefront](user/img/concept-guides/menus/commerce_quick_access_sample1.png)

### Commerce_main_menu

**Commerce_main_menu** defines the static menu items that are appended to the main OroCommerce storefront menu. Generally, the leading part of the menu that a customer sees is build based on the master catalog categories or web catalog content nodes. The trailing part is composed of the **commerce_main_menu items**. If you need to add additional information that would not depend on the master or web catalog settings and restrictions, add them to the **commerce_main_menu**. It is useful for the sections with the general information, like the *About Company* page, or the *Contact Us* form, that can remain unchanged regardless if your site is accessed by a guest or registered user, via desktop, tablet or mobile.

![A sample of the commerce_main_menu in the storefront](user/img/concept-guides/menus/commerce_main_menu_sample.png)

### Commerce_footer_links

The **commerce_footer_links** menu defines the structure of the links located in the OroCommerce website page footer. Use the menu to provide a quick overview of your entire site or the most essential pages to your audience. You can also add the links to popular categories or products which otherwise are hard to find.

![A sample of the commerce_footer_links menu in the storefront](user/img/concept-guides/menus/commerce_footer_links_sample.png)

### Featured_menu

**Featured_menu** provides the possibility to include the necessary information as a separate block to the featured menu on the OroCommerce homepage. Usually, the menu is used to highlight the latest promotions, featured categories, or items to attract the customers’ attention to the critical information.

![A sample of the featured_menu in the storefront](user/img/concept-guides/menus/featured_menu_sample.png)

Keep in mind that the **featured_menu** is different from the [featured products segment](../../back-office/system/configuration/commerce/product/global-featured-products.md#products-featured-products). While the featured products segment is intended to store only the products and categories that are marked as featured, the featured menu is designed to offer any other information that you want to emphasize.

![Featured menu vs featured segment](user/img/concept-guides/menus/featured_menu_vs_segment.png)

### Customer_usermenu

**Customer_usermenu** is a storefront user menu that appears at the top right of the website’s page header and defines what a customer will see within this menu. The menu look can either be concise (displaying all menu items in one raw)  or expanded (displaying the full list of menu subitems in a popup). The way it is shown in the storefront can be customized under the **Theme Settings** configuration on the [global](../../back-office/system/configuration/commerce/design/theme-global.md#configuration-commerce-design-theme-theme-settings-globally), [organization](../../back-office/system/user-management/organizations/org-configuration/commerce/design/organization-theme.md#configuration-commerce-design-theme-theme-settings-organization), and [website levels](../../back-office/system/websites/web-configuration/commerce/design/website-theme.md#configuration-commerce-design-theme-theme-settings-website).

![A sample of the customer_usermenu in the storefront](user/img/concept-guides/menus/customer_usermenu_sample.png)

### Oro_customer_menu

**Oro_customer_menu** defines the menu items that would populate the **Account** section of the user menu.

![A sample of the oro_customer_menu in the storefront](user/img/concept-guides/menus/oro_customer_menu_sample.png)
<br/>

#### NOTE
The ability to configure and manage Storefront Menus depends on the **Manage Menus** and **Access system configuration** capabilities. Make sure to [enable them for the specific role](../../back-office/system/user-management/roles/index.md#user-guide-user-management-permissions-roles) to allow the user with this role to handle the menus functionality in the storefront.

![Illustrate Manage Menus and Access system configuration capabilities](user/img/concept-guides/menus/menus_capabilities.png)

## Back-Office Menu Components

[Back-office menu](../../back-office/system/menus/index.md#doc-config-menus) in OroCommerce allows you to navigate within menus of your website’s back-office, easily access your profile page, modify the existing menu items, adapt the default menus look and the elements they contain [globally](../../back-office/system/menus/index.md#doc-menu-config-levels), [per organization](../../back-office/system/user-management/organizations/organization-frontend-menus.md#backend-menu-organization), and [for your own use](../../back-office/system/menus/index.md#doc-menu-config-levels).

![A list of available back-office menu items in the back-office](user/img/concept-guides/menus/backend_menu_list.png)

### Application_menu

**Application_menu** (navigation bar) is the main menu of the back-office in the Oro application. It resides on the top of every application page, and you can use it to navigate through the Oro application. Subject to configuration, it may be displayed horizontally or vertically. The way it is displayed is customized in the system configuration in the **Navigation Bar** section of **Display Settings** and can be configured on four levels: [globally](../../back-office/system/configuration/system/general-setup/display.md#configuration-general-setup-display-settings), [per organization](../../back-office/system/user-management/organizations/org-configuration/general-setup-org/organization-display-settings.md#configuration-general-setup-display-settings-organization), [per website](../../back-office/system/websites/web-configuration/general-sys-config/general/website-display-settings.md#display-settings-website), and [per user](../../back-office/system/user-management/users/configuration/user-display-settings.md#doc-my-user-configuration-display).

![Illustrate the left and top positions of the application menu and where to configure them](user/img/concept-guides/menus/application_menu_sample.png)

In a top position, the application menu (navigation bar) looks like a top menu with a drop-down sub-menus that expand once you hover over the parent item.

In a left position, the application menu (navigation bar) may be collapsed into the icon bar, or expanded for visible labels and sub-menu items:

![Illustrate the application menu in the collapsed and expanded view](user/img/concept-guides/menus/left_application_menu.png)

### Shortcuts

The **shortcuts** menu is displayed in the top panel of the application, next to the organization name.

![A sample of the shortcuts menu in the back-office](user/img/concept-guides/menus/shortcuts_menu_sample1.png)

It helps you pin the frequently used actions and have them handy. You can launch an action by clicking it in the dynamically generated **Most Used Actions** list. This list is updated as you are using the system, and will initially contain the actions that you use the most.

To access other shortcuts, click **See the full list** to see a complete list of shortcut items or use search: start typing the name of a related entity or an action to choose from a list of matching items.

### Usermenu

**Usermenu** is the personal menu of the logged-in user in the back-office. A user can access their profile configuration, emails, tasks, and events via **usermenu** by clicking on their name on the top right of the application.

![A sample of the usermenu in the back-office](user/img/concept-guides/menus/usermenu_sample.png)

### Calendar_menu

**Calendar_menu** is a service menu that is located on the **My Calendar** page under the ellipsis menu to the right from the calendar name. The actions in the menu help change the displayed calendar color, hide or remove a calendar.

![A sample of the calendar_menu in the back-office](user/img/concept-guides/menus/calendar_menu.png)

### Calendar_menu_mobile

**Calendar_menu_mobile** is the mobile-adapted implementation of **calendar_menu** that allows you to manage your personal calendar from your mobile device anywhere and anytime without missing important events, calls, meetings, and schedules.

<br/>

#### NOTE
The ability to configure and manage Menus in the back-office depends on the **Manage Menus** and **Access system configuration** capabilities. Make sure to [enable them for the specific role](../../back-office/system/user-management/roles/index.md#user-guide-user-management-permissions-roles) to allow the user with this role to handle the menus functionality in the back-office.

## Menus Localization

With OroCommerce, you can also make your website menu content multilingual by translating it to the target languages of your audience. The related translation is displayed once a user is switching the localization in the storefront. The language of the back-office menu content can be configured either individually per user, per specific website, per organization, or system-wide.

In a nutshell, when editing the content of the selected menu item, click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon next to the required menu element to provide spelling for different languages.

![Commerce_quick_access menu translated to French in the storefront](user/img/concept-guides/menus/localize_menus.png)

#### HINT
More on localizations and translations of content and UI system elements, read in the [Localizations, Languages, and Translations](../../back-office/system/localization/index.md#sys-config-sysconfig-general-setup-localization) topic.

**Related Articles**

* [Configure Storefront Menu in the Back-Office](../../back-office/system/frontend-menus/index.md#backend-frontend-menus)
* [Configure Back-Office Menu in the Back-Office](../../back-office/system/menus/index.md#doc-config-menus)
* [Configure Localizations, Languages, and Translations in the Back-Office](../../back-office/system/localization/index.md#sys-config-sysconfig-general-setup-localization)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
