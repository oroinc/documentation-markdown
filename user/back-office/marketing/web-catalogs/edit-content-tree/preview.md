<a id="user-guide-marketing-web-catalog-preview"></a>

# Preview Web Catalog

OroCommerce enables you to preview web catalog pages in the storefront, applying different restrictions dynamically and checking how the content is reflected depending on these restrictions.

#### NOTE
The ability to preview web catalog nodes is controlled by the *Storefront Preview* permissions defined for the selected role in the system configuration.

![Storefront Preview capabilities enabled for the admin role](user/img/marketing/web_catalogs/preview_web_catalog_permissions.png)

To start previewing a selected node, follow the steps outlined below:

1. Enable the web catalog either on the [global level](../../../system/configuration/system/websites/global-routing.md#user-guide-marketing-web-catalog-enable-globally) or per [website](../../../system/websites/web-configuration/general-sys-config/websites/website-routing.md#user-guide-marketing-web-catalog-enable-per-website).
2. Navigate to the required web catalog details page under **Marketing > Web Catalogs** and click <i class="fa fa-sitemap fa-lg" aria-hidden="true"></i> **Edit Content Tree** in the more options menu of the related web catalog.
3. Select the content node to preview and click <i class="far fa-eye" aria-hidden="true"></i> **Preview** on the top right.
   > ![Clicking Preview on the top right of the Lighting  Products content node](user/img/marketing/web_catalogs/web_catalog_preview.png)
4. The storefront page of the related content node opens in the preview mode in a new tab. The mode allows you to browse other pages as well. The configuration panel on the top of the page enables you to switch between websites, localizations, customer groups, and customers to ensure that the page is displayed correctly, based on different restriction scopes.
   > ![Configuration panel in the storefront](user/img/marketing/web_catalogs/preview_mode.png)
5. If you want to adjust any settings and preview the results, you need to save these settings first.

To illustrate the example, let’s consider the case where you run two businesses in the US and Canada selling various lighting products. While the US warehouse is all packed with the necessary products, the warehouse in Canada is only expecting the delivery. You have created a dedicated landing page to notify the wholesale customers that the products are on the way. This way, your restrictions for the *Lighting Products* node can be configured the following way:

* The Lighting Products category page is visible for all customers, customer groups, and localizations of the US website.
* The related landing page is visible for all wholesale customers of the Canada website.
  > ![Restrictions set fot the lighting products content node](user/img/marketing/web_catalogs/lighting_products_restrictions.png)

When previewing this page, you need to set the same restrictions in the configuration panel to see how the page will be rendered in the storefront:

* for the US website
  > ![Restrictions set fot the lighting products content node](user/img/marketing/web_catalogs/US_storefront_preview.png)
* for the Canada website
  > ![Restrictions set fot the lighting products content node](user/img/marketing/web_catalogs/Canada_storefront_preview.png)
* If the web catalog page is not visible within the applied restrictions, the customers will see the 404 error.
  > ![Restrictions set fot the lighting products content node](user/img/marketing/web_catalogs/404_error.png)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
