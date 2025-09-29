<a id="sys-websites-sysconfig-websites-sitemap"></a>

# Configure Sitemap Settings per Website

You can control the way sitemap is generated for the specific website in OroCommerce.

#### NOTE
The website level configuration overrides [global sitemap](../../../../configuration/system/websites/global-sitemap.md#sys-config-sysconfig-websites-sitemap) configuration.

To change the default sitemap settings for the website:

1. Navigate to the system configuration (click **System > Websites** in the main menu).
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **System Configuration > Websites > Sitemap** in the menu to the left.
   ![image](user/img/system/websites/web_configuration/website-sitemaps.png)

   The frequency and priority options may be configured globally or specifically for product, category and the cms page level.
4. To customize any of these options:
   > 1. Clear the **Use Organization** box next to the option.
   > 2. Select the new option.
5. To configure which pages to include and exclude from the sitemap file, enable the following options:

* **Exclude Direct URLs Of Landing Pages** - Enable the option to include only landing pages that are assigned to particular web catalog nodes into the website’s sitemap and exclude those accessed via direct URL. Enabling the option prevents landing page duplication in the sitemap file.

#### HINT
The *Include Landing Pages Not Used In Web Catalog* feature is available starting from OroCommerce v5.0.6. To check which application version you are running, see the [system information](../../../../system-information/index.md#system-information).

* **Include Landing Pages Not Used In Web Catalog** - Enable the option to include both assigned to web catalog nodes and unassigned landing pages into the sitemap file.

Possible combinations

![Table that explains what landing pages are included and excluded into the sitemap file depending on the selected config options](user/img/system/config_system/sitemap-config-options.png)
1. Click **Save**.

<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
