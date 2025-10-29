<a id="website-management-concept-guide"></a>

# Multiple Websites Concept Guide

#### IMPORTANT
Multi-website management is available for the Enterprise edition only.

Whether you are running a multinational B2B or B2C eCommerce business across countries or selling multiple brands to customers in the neighboring states, it is important to have the necessary tools and solutions in place and manage all your online stores from a single instance.

With OroCommerce Enterprise Edition, you can create multiple websites, both B2B and B2C, for all your industries, niches, and customers that would share the same configuration, same payment and shipment options, promotion campaigns, price lists, product and service assortment, and more.

You can also configure the websites to run in a fully independent way, with their own domain name, branding, product pages, localization, storefront menu, and customized content to target different audiences, countries, and segments of goods or services that your company offers.

The type of website you choose to maintain depends on your specific needs and circumstances.

Let’s dive deeper into the capabilities that the feature provides to find out which configuration options OroCommerce has prepared for B2B and B2C businesses who run multiple websites.

## Multi-Website Feature Capabilities

In many cases, segmenting information is useful for large organizations with varied offerings. OroCommerce has taken care of simplifying the setup procedure for all your [websites](../../../back-office/system/websites/index.md#system-websites), enabling you to create the necessary content once and leverage it across multiple websites, without labor-intensive copying of data , be it 2, 3, or 100 websites.

In a multi-org environment, each organization may have one or several websites. All the settings configured per organization can be adopted by all running websites within this particular organization, but cannot be applied to other organizations. To change the organization and see the related content and available websites, use the switcher on the top left.

> ![A list of websites created within one organization](user/img/concept-guides/websites/Oro_organization.png)

The settings that are shared across the websites are the following:

* [Customer management](../../../back-office/customers/customer-users/index.md#user-guide-customers-customer-users) — Out-of-the-box, a customer user with the registered account can log into all websites within one organization with the same credentials, regardless of the website where they have registered.
* [Integration configuration](../../../back-office/system/integrations/index.md#user-guide-integrations) — Once you configure Google, Dotdigital, Zendesk, or any other integration, it becomes available for all your websites automatically. Payment and shipping integrations, however, can be assigned to selected websites.
* [Taxation configuration](../../../back-office/system/configuration/commerce/taxation/index.md#configuration-guide-commerce-configuration-taxation) — The setting allows to enable taxation, select the tax provider, set Sales and VAT taxes, and calculate the tax on shipping once across all websites.
* [Workflow configuration](../../../back-office/system/workflows/index.md#doc-system-workflow-management) — Any workflows that you activate for your application (checkout, quote, rfq, or any other custom one) are automatically enabled for all the websites within one organization. However, the decision on whether to enable a guest checkout is made individually for each website.

While OroCommerce allows you to create a standard look and feel of your online web store and share it across all your business units, it also enables regional teams to tailor content and run marketing campaigns on the websites they are responsible for.

This may be useful in the following cases:

**1. The product or service you offer is limited to some websites.**

> Suppose you run your business both in the US and Germany selling a variety of industrial and medical products. While business in the US is well-established, your German chain is pending some license approval. Until you have it, you can sell only a limited number of medical products on the German website. To tackle this issue under the hood, you can set the appropriate restrictions to your web catalog so it displays a limited product assortment in Germany until the licenses are obtained, and then drop restrictions to enable the entire catalog.

> ![Different product catalog for the US and German websites](user/img/concept-guides/websites/us_website_vs_germany_website.png)

> #### HINT
> Check out the Web Catalog Visibility guide to learn more on [web catalog visibility restrictions](../../../back-office/marketing/web-catalogs/edit-content-tree/visibility.md#user-guide-marketing-web-catalog-node-visibility).

**2. You want to spotlight each of your brands, product groups or services separately.**

> If you deal with multiple brands or provide various services, you may want to separate your businesses to different websites with different domains or subdomains, if necessary. This way, you can configure the appropriate website-specific settings to target the required audience. You can change the domain name, add variable web catalog pages for different websites to showcase your products or services in the desired way, customize price lists, and configure the shipping and payment methods required for specific websites.

> #### HINT
> Check out the Websites Management guide to learn more on [website-specific settings](../../../back-office/system/websites/manage.md#user-guide-system-websites-manage-websites).

**3. You want to create a geo-specific website to target diverse localizations.**

> If your business sells products or services to multiple countries, you may want to create several websites to handle all locations and configure them individually for each site, adapting the content and settings for a specific country and region.

> ![An example of a geo-specific website](user/img/concept-guides/websites/select_your_country.png)

> While you can create multiple localizations to support content translation into different languages (e.g., Spanish, French, Russian, German), you can also create another localization for the same language with the same formatting to enable the additional translation of the UI system elements and content to the required language.

> For instance, if you run two different businesses in the US on the same platform, you can diversify the same UI and content elements so the two websites look and feel different. This way, you can change the wording of the same element turning a *shopping list* from website A into a *shopping cart* for website B, and a *Men’s Basic V-neck, 1-Pocket Light Blue Scrub Top* into a simple *Men’s Scrub Top* with a different product description.

> #### HINT
> Check out the Localization guide to learn more on [content localization and translation processes](../../../back-office/system/localization/index.md#sys-config-sysconfig-general-setup-localization).

With all of that in mind, let’s check the website-specific parameters you can adjust to hit your goals.

## Website-Specific System Configuration

Each website has system settings that can be customized individually per website. The same set of settings are also available on the [global](../../../back-office/system/configuration/index.md#mc-system-configuration) and [organization](../../../back-office/system/user-management/organizations/org-configuration/index.md#doc-organization-configuration) levels. Provided that all levels have different configuration, the settings configured for a particular website will always be prioritized first.

However, there are some settings that can be adjusted on the customer and customer group levels as well. This includes the configuration of [price lists](../../../back-office/customers/customers/customer-price-lists.md#customers-customers-edit-price-lists) and [storefront menus](../../../back-office/customers/customers/customer-frontend-menus.md#frontend-menus-customer).

> ![Website-specific system configuration settings](user/img/concept-guides/websites/website_system_config.png)

In the website configuration menu, you can:

* change the website’s domain name
* configure the appropriate cookie values
* enable the languages to be selected in the storefront
* enable guest website access and other guest functions
* define the required currency based on the website’s localization, and more.

## Website Matchers

In OroCommerce, you can identify the visitors of your website through various [tracking options](../../../back-office/system/configuration/system/websites/global-routing.md#sys-config-sysconfig-websites-routing). Out-of-the-box, you have three options:

> ![Three available website matcher options](user/img/system/config_system/routing_website_matchers.png)

**1. URL Based**.

> All websites in OroCommerce can either share the same domain name, use a specific one, or even reside in the sub-folders of the same domain.

> For the websites that share the same domain, you can simply adapt the content per region in the settings of each website.

> Websites exposed via different domain names can target different countries, audiences, or brands. So websites that operate both in the USA and Germany can be reached via either *https://us-store.com* & *https://de-store.com*, or *https://store.com/us* & *https://store.com/de*.

> For the websites with dedicated domains, you can use the default OroCommerce installation, where all websites are installed into the web folder of the OroCommerce instance. However, you can move or copy the website to the sub-directory to support the websites with the shared domain (e.g., *https://store.com/us* and *https://store.com/uk*).

> ![Routing configuration settings of the US website](user/img/concept-guides/websites/website_domain_names.png)

**2. Cookie Based**.

> You can also set the cookie values to identify visitors of a certain website and redirect them to the necessary site once they return. This allows websites to track users across several domains.

**3. ENV Variable Based**.

> Identifying visitors is also possible via the individual environment variable parameters specified for each website.

## B2C Websites

One of the substantial capabilities offered by OroCommerce is the ability to configure the website to match the [B2C](../../../back-office/system/websites/manage.md#user-guide-system-websites-b2c) business model. Even if the website was initially configured to follow the B2B market segment, you can easily transfer it to B2C at any time. Unlike B2B, the B2C model disables the ability to request a quote, view the quotes, and use a quick order form to place the orders. Guest shopping lists are activated, and all the users are no longer required to mention a company name when registering an account. All the settings are immediately adjusted to match the new strategy and can be changed in the system configuration later on.

> ![Configure a website as B2C](user/img/concept-guides/websites/configure_website_as_b2c.png)

## Website Navigation

The storefront navigation is highly customizable via the [Storefront Menus](../../../back-office/system/frontend-menus/index.md#doc-system-menu-config-levels-frontend-menus) that can be set globally, per organization, per website, per customer, and per customer group.

![A list of menu items in Storefront menu](user/img/concept-guides/websites/website_navigation.png)

All the visuals represented in the storefront are specific to each website. Go through the available menus to adapt content to particular audience and localization. You can enable or disable menu items for a particular customer, website, or mobile device by setting related conditions.

![Illustrate all available storefront menu items in the storefront](user/img/concept-guides/websites/frontend_menu_refreshing_teal.png)

## Web Catalogs per Website

You can compile content for the website, including individual products, product collections, categories, and landing pages, using three different strategies.

1. The website can share the default web catalog. It is useful when you offer the same product collection to your customers across different websites.
2. You can modify the default web catalog via the content variants and restrictions. This enables you to toggle the visibility of particular content, product pages, or the whole category specifically for each website.
   > ![Restricting a web catalog category to a certain website](user/img/concept-guides/websites/default_webcatalog_per_website.png)
3. You can have an entirely unique web catalog that defines content only for the specific website. You can create plenty of web catalogs to cover all your business directions and selectively assign web catalogs to the required websites.
   > ![Select a custom web catalog](user/img/concept-guides/websites/selecting_webcatalog.png)

## Product Visibility per Website

As an alternative to hiding the whole web catalog category, you can set [visibility restrictions to each product](../../../back-office/products/products/managing-product-visibility.md#products-product-visibility) individually. This allows configuring products differently for each website.

For instance, your subdivision in the US has received a batch of defective products (e.g., medical scrubs) from one of your suppliers. While you are waiting for another batch to replace the faulty one, you may want to keep all the scrubs but hide them on your US website to disable their purchase for a while.

![Illustrate products visibility on different websites](user/img/concept-guides/websites/product_visibility_restrictions.png)

## Price Lists per Website

The [prices on the website](../../../back-office/system/websites/manage.md#user-guide-system-websites-price-lists) can come either from the default price lists or from the price lists created specifically for the website’s locale and market. Different price lists enable you to use different pricing strategies considering the regional discounts, signed contracts, and local taxation.

![A list of available price lists to be selected for the selected website](user/img/concept-guides/websites/price_lists_per_website.png)

## Product Inventory per Website

OroCommerce supports tracking your [inventory data](../../../back-office/inventory/index.md#user-guide-inventory) per website. It is useful when you have your own warehouse in your region, and you store all goods there. This way, you can monitor the availability of the products in stock and their quantity per specific website. While one website may have zero quantity of one product in stock, the other website can have plenty. As the inventory values are dynamic, they are refreshed shortly after the customer makes a purchase, so you can always view the updated data in the storefront and in the back-office.

![Illustrate the way the product quantity is changed due to different warehouse settings](user/img/concept-guides/websites/product_inventory_per_website.png)

## Shipping and Payment per Website

With OroCommerce, you can either share the same payment and shipping methods across all running websites or use only specific ones. You can add the selected providers that would suit a particular website best considering the local delivery and payment options. For example, you can configure four different payment options for the US, while only PayPal would be available in Germany. Any other solution is possible here.

#### HINT
Check out the Integrations guide to learn more on [payment and shipping method integrations and providers](../../../back-office/system/integrations/index.md#user-guide-integrations).

![Different payment options for different websites](user/img/concept-guides/websites/payment_options_per_website.png)

**Related Topics**

* [Websites User Guide](../../../back-office/system/websites/index.md#system-websites)
* [System Configuration for Website](../../../back-office/system/websites/web-configuration/index.md#doc-website-configuration)
* [Setup a Website Host](../../../../backend/setup/installation-in-sub-folder.md#system-websites-prepare-to-host-a-website-in-the-domain-sub-folder)
* [Manage a Website](../../../back-office/system/websites/manage.md#user-guide-system-websites-manage-websites)
* [Website Routing Configuration](../../../back-office/system/configuration/system/websites/global-routing.md#sys-config-sysconfig-websites-routing)
* [Storefront Menu](../../../back-office/system/frontend-menus/index.md#backend-frontend-menus)
