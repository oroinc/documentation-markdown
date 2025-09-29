<a id="sys-conf-commerce-guest-seo-org"></a>

# Configure SEO Settings per Organization

The SEO-related settings can be configured [globally](../../../../../configuration/commerce/guests/global-seo.md#sys-conf-commerce-guest-seo-global), per organization, and [per website](../../../../../websites/web-configuration/commerce/guests/website-seo.md#sys-conf-commerce-guest-seo-website).

To configure the settings per organization:

1. Navigate to **System > User Management > Organizations**.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization, and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Guests > SEO** in the menu on the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![SEO settings configuration per organization](user/img/system/config_commerce/seo/org-seo-settings.png)
1. Clear the **Use System** checkbox to change the system-wide settings.
2. In the **Schema.org** section, configure the following options:
   * **Disable Product Microdata Without Prices** — The setting disables Schema.org Microdata for products without prices. All products that do not have assigned prices contain Schema.org Microdata markup with a product schema without price information. Some search crawlers (e.g., Google) consider these products invalid and can exclude them from the search index. Select the checkbox to prevent products without prices from being blocked by search crawlers (available starting from v5.0.3. To check which application version you are running, see the [system information](../../../../../system-information/index.md#system-information)).
   * **Include Product Description** — Select the checkbox to include product description into the Schema.org markup for products (available starting from v5.0.7. To check which application version you are running, see the [system information](../../../../../system-information/index.md#system-information)).
   * **Used Product Description Field** — Select which product description field type will be used for the Schema.org description property from the dropdown. Available options are *Simplified [Long] Description*, *SEO Meta Description*, and *Simplified Short Description* (available starting from v5.0.7. To check which application version you are running, see the [system information](../../../../../system-information/index.md#system-information)).
3. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
