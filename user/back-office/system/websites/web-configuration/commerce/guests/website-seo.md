<a id="sys-conf-commerce-guest-seo-website"></a>

# Configure SEO Settings per Website

## Disable Product Microdata Without Prices

All products that do not have assigned prices contain Schema.org Microdata markup with a product schema without price information. Some search crawlers (e.g., Google) consider these products invalid and can exclude them from the search index.

To prevent products without prices from being blocked by search crawlers, it is recommended to disable Schema.org Microdata for such products. This can be done [globally](../../../../configuration/commerce/guests/global-seo.md#sys-conf-commerce-guest-seo-global), [per organization](../../../../user-management/organizations/org-configuration/commerce/guests/organization-seo.md#sys-conf-commerce-guest-seo-org), and per website.

To configure the settings per website:

1. Navigate to **System > Websites**.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website, and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Guests > SEO** in the menu on the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

1. To customize any of the options, clear the **Use Organization** box and select a new option.
2. In the **Schema.org** section, configure the following options:
   * **Disable Product Microdata Without Price** — Select the option to disable Schema.org Microdata for the products without prices. All products that do not have assigned prices contain the Schema.org Microdata markup with a product schema without price information. Some search crawlers (e.g., Google) consider these products invalid and can exclude them from the search index. To prevent products without prices from being blocked by search crawlers, it is recommended to disable the Schema.org Microdata, unless you have an alternative custom solution (e.g., reviews or aggregated ratings system) in place.
   * **Used Product Description Field** — The setting enables you to control which product field to be used for the Schema.org description property. Select the required description type from the dropdown. Available options are *Simplified [Long] Description*, *SEO Meta Description*, and *Simplified Short Description*.
3. Click **Save Settings**.

![SEO settings configuration per website](user/img/system/config_commerce/seo/website-seo-settings.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
