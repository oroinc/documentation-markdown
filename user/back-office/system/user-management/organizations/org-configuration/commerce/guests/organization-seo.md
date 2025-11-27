<a id="sys-conf-commerce-guest-seo-org"></a>

# Configure SEO Settings per Organization

To configure the SEO settings per organization:

1. Navigate to **System > User Management > Organizations**.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization, and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Guests > SEO** in the menu on the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![SEO settings configuration per organization](user/img/system/config_commerce/seo/org-seo-settings.png)
1. Clear the **Use System** checkbox to change the system-wide settings.
2. In the **Schema.org** section, configure the following options:
   * **Disable Product Microdata Without Price** — Select the option to disable Schema.org Microdata for the products without prices. All products that do not have assigned prices contain the Schema.org Microdata markup with a product schema without price information. Some search crawlers (e.g., Google) consider these products invalid and can exclude them from the search index. To prevent products without prices from being blocked by search crawlers, it is recommended to disable the Schema.org Microdata, unless you have an alternative custom solution (e.g., reviews or aggregated ratings system) in place.
   * **Used Product Description Field** — The setting enables you to control which product field to be used for the Schema.org description property. Select the required description type from the dropdown. Available options are *Simplified [Long] Description*, *SEO Meta Description*, and *Simplified Short Description*.
3. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
