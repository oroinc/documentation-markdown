<a id="user-guide-system-websites-manage-websites"></a>

# Manage a Website in the Back-Office

#### HINT
This section is part of the [Multi-Website Configuration](../../../concept-guides/websites/index.md#website-management-concept-guide) concept guide topic that provides the general understanding of multiple website configuration concept in Oro applications.

#### IMPORTANT
Multi-website management is only available in the Enterprise edition.

With OroCommerce, you can determine the way a particular website is operated by customizing it according to your business requirements.

Once a website is created and properly configured, you can now:

* set the website as default
* configure the website settings for the B2C market sector
* customize the website storefront navigation and menus
* add variable web catalog pages for different websites
* limit price lists and content blocks to particular websites
* customize product inventory, create and manage multiple warehouses on different websites
* manage product visibility on the website
* enable certain shipping and payment methods on the website
* limit a promotion campaign to a website
* set up and use website tracking with your OroCommerce website

## Set a Website as Default

OroCommerce redirects anonymous users to the default website. Logged in customers users may also be redirected in case their current website is not identified.

To set a website as default:

1. Navigate to **System > Websites** using the main menu.
2. Click on the website you would like to use as default (e.g., Australia).
   ![View the details of Australia website](user/img/system/websites/view_website_australia.png)
3. On the website details page, click <i class="fa fa-flag fa-lg" aria-hidden="true"></i> **Set Default**.

Now the website is marked as default and will be used for the anonymous access.

![Mark Australia website as the default one](user/img/system/websites/default_australia_website.png)

<a id="user-guide-system-websites-b2c"></a>

## Configure a Website for B2C

OroCommerce enables you to customize the application for the B2C business type, modifying the default configuration to match the typical B2C setup. You can then change these settings manually in the system configuration, if necessary.

A B2C website can be configured in two ways, either [during creation](create.md#system-websites-create) or from the website’s view page.

1. Navigate to **System > Websites** using the main menu.
2. Click the website you would like to configure for B2C (e.g., Australia).
   ![View the details of Australia website](user/img/system/websites/view_website_australia_B2C.png)
3. On the website details page, click <i class="fas fa-shopping-bag" aria-hidden="true"></i> **Configure for B2C**.
4. The popup confirmation dialog displays the list of options that will be modified by this configuration.
   ![The list of options that are modified for the B2C website](user/img/system/websites/B2C_settings2.png)
5. Click **Yes** to confirm.
6. The changes apply automatically. You can view them in the system configuration and update if required.

## Edit a Storefront Menu

OroCommerce storefront has a number of menus that may be rearranged and customized. You can enable or disable menu items for a particular customer, website, or a mobile device by setting related conditions.

To customize a storefront menu for the website:

1. Navigate to **System > Websites** using the main menu.
2. Click the website you would like to edit a menu for (e.g., Australia).
   ![View the details of Australia website](user/img/system/websites/view_website_australia1.png)
3. On the website details page, click <i class="fas fa-cog" aria-hidden="true"></i> **Edit Frontend Menu**.

   Now you are redirected to the list of OroCommerce storefront menus:
   ![The list of OroCommerce storefront menus](user/img/system/websites/front_menu.png)
4. Click on the menu to start customizing it:
   ![Click on the menu to start customizing it](user/img/system/websites/edit_menu.png)
   * Drag-and-drop menu items to rearrange them.
   * Create new items and dividers if necessary by clicking **Create Menu Item** or **Create Divider** (in the button group on the top right of the page).
   * Click on the menu item to edit its details.

Find more information on how to edit and customize the storefront menu in the [Menu Management](../menus/index.md#doc-config-menus-menuspage) section.

1. Once you are happy with the menu contents, click **Save**.

## Customize Web Catalogs per Website

OroCommerce enables you to create a web catalog with different product collections and customize it for a certain website in a way you prefer to make shopping easy and efficient. You can also organize a specific content tree by building additional content nodes and customizing menu items per each website individually.

To create a new web catalog, personalize the catalog content for a specific website, set up particular visibility restrictions to a website, localization, or a customer, and enable the web catalog for the selected website, refer to the following sections:

* [Create a Web Catalog](../../marketing/web-catalogs/create.md#user-guide-web-catalog-create)
* [Configure Content Variants for the Content Node](../../marketing/web-catalogs/edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant)
* [Configure Content Visibility](../../marketing/web-catalogs/edit-content-tree/visibility.md#user-guide-marketing-web-catalog-node-visibility)
* [Enable a Web Catalog for a Website](web-configuration/general-sys-config/websites/website-routing.md#user-guide-marketing-web-catalog-enable-per-website)

## Customize Content Blocks per Website

When you prepare [web catalogs](../../marketing/web-catalogs/index.md#user-guide-web-catalog) for you storefront, you can [create](../../marketing/web-catalogs/create.md#user-guide-web-catalog-create) and [enable a custom web catalog for the website](web-configuration/general-sys-config/websites/website-routing.md#user-guide-marketing-web-catalog-enable-per-website) or [set up a custom node content for the website](../../marketing/web-catalogs/edit-content-tree/visibility.md#user-guide-marketing-web-catalog-customize) in the default web catalog.

<a id="user-guide-system-websites-price-lists"></a>

## Customize Price Lists per Website

With OroCommerce you can create and set up flexible product prices for different websites, link the price lists to a particular website, a customer, or a customer group, and schedule price changes.

For more details on how to create a price list and enable it for a particular website, refer to the following sections:

* [Currency Configuration per Website](web-configuration/commerce/catalog/website-pricing.md#sys-websites-sysconfig-currency)
* [Price Lists Management](../../sales/price-lists/index.md#user-guide-pricing-pricelist-management)
* [Price List Configuration per Website](configure-price-lists.md#sys-website-edit-price-lists)
* [Price List Configuration per Customer](../../customers/customers/customer-price-lists.md#customers-customers-edit-price-lists)
* [Price List Configuration per Customer Group](../../customers/customer-groups/customer-group-price-lists.md#customers-customer-groups-edit-price-lists)

## Customize Product Inventory per Website

You can also create and manage multiple warehouses (EE feature), track your inventory status and the availability of your products, as well as their quantities, in each warehouse assigned to a particular website.

The [Warehouses and Inventory](../../inventory/index.md#user-guide-inventory) section covers the details on how to configure inventory-related settings globally and per a website.

## Customize Product Visibility per Website

Additionally to configuration set for product categories and price lists, you can determine which customers, customer groups, or websites are to view specific products by customizing a related product visibility per each product individually.

Follow the [Manage Product Visibility](../../products/products/managing-product-visibility.md#products-product-visibility) section for the details on how to set certain visibility restrictions for selected products.

## Customize Promotion Visibility per Website

Similarly to a visibility restriction procedure set to a product, promotion visibility can also be limited to a particular website, a customer. or a customer group.

Follow the [Promotions](../../marketing/promotions/promotions/index.md#user-guide-marketing-promotions) section for the details on how to create and manage promotions.

## Customize a Payment Method per Website

OroCommerce provides sellers with effective payment solutions that help enhance customers’ buying experience. Integration with the most popular payment services as [PayPal](../integrations/payment-integration/paypal-services/index.md#user-guide-payment-payment-providers-overview-paypal), [Authorize.Net](../integrations/payment-integration/authorizenet/index.md#user-guide-payment-payment-providers-overview-authorizenet), [InfinitePay](../integrations/payment-integration/infinitepay/index.md#user-guide-payment-payment-providers-overview-infinitepay), and [Apruve](../integrations/payment-integration/apruve/index.md#user-guide-payment-payment-providers-overview-apruve) into OroCommerce enables various payment transactions to be made in a particular localization and on a certain website.

Learn more about how to assign a payment method to the required website in the [Payment Rules Configuration](../payment-rules/index.md#sys-payment-rules) section.

Also refer to the [payment configuration](../../../concept-guides/payment-configuration/index.md#user-guide-payment-configuration) for the detailed instruction on how to set a merchant location and configure integration with third-party payment providers.

## Customize a Shipping Method per Website

Similarly to configuring payment methods in OroCommerce, you can create an integration with a shipping provider, such as [UPS](../integrations/shipping-integration/ups.md#doc-integrations-ups), [FedEx](../integrations/shipping-integration/fedex.md#doc-integrations-fedex), and [Flat Rate](../integrations/shipping-integration/flat-rate.md#doc-integrations-flat-rate) and customize its settings per a particular website by adding a [shipping rule](../integrations/shipping-integration/index.md#sys-integrations-manage-integrations-ups-flat-rate).

Also, refer to the [shipping configuration on the system level](../configuration/commerce/shipping/index.md#user-guide-shipping-configuration) to set the default shipping address, enable or disable shipping units of length and weight, and specify the tax code to be applied to the shipping cost.

**Related Topics**

* [Website Management](index.md#user-guide-system-websites)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
