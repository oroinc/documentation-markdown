<a id="sys-config-sysconfig-websites-sitemap"></a>

# Configure Global Sitemap Settings

You can control the way sitemap is generated for all websites.

#### NOTE
[Website level configuration](../../../websites/web-configuration/general-sys-config/websites/website-sitemap.md#sys-websites-sysconfig-websites-sitemap) has higher priority and overrides this configuration settings.

To change the default global sitemap settings:

1. Navigate to **System > Configuration** in the main menu.
2. Select **System Configuration > Websites > Sitemap** in the menu to the left.
   ![Global website sitemap configuration](user/img/system/config_system/sitemaps.png)

   The frequency and priority options may be configured globally or specifically for product, category and the cms page level.
3. To customize any of these options:
   1. Clear the **Use Default** box next to the option.
   2. Select the new option.
4. To configure which pages to include and exclude from the sitemap file, enable the following options:

* **Exclude Direct URLs Of Landing Pages** - Enable the option to include only landing pages that are assigned to particular web catalog nodes into the website’s sitemap and exclude those accessed via direct URL. Enabling the option prevents landing page duplication in the sitemap file.

#### HINT
The *Include Landing Pages Not Used In Web Catalog* feature is available starting from OroCommerce v5.0.6. To check which application version you are running, see the [system information](../../../system-information/index.md#system-information).

* **Include Landing Pages Not Used In Web Catalog** - Enable the option to include both assigned to web catalog nodes and unassigned landing pages into the sitemap file.

Possible combinations

![Table that explains what landing pages are included and excluded into the sitemap file depending on the selected config options](user/img/system/config_system/sitemap-config-options.png)
1. Click **Save**.
