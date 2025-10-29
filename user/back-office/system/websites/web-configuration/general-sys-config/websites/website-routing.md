<a id="sys-websites-sysconfig-websites-routing"></a>

<a id="user-guide-marketing-web-catalog-enable-per-website"></a>

# Configure Routing Settings per Website

To control the way OroCommerce routes HTTP requests to the components when a customer uses particular website, you may provide the following website-specific information:

* Global website URL when reached using secure (https) and insecure (http) connection
* Options that impact the way metadata for the search engine is generated
* Information for the website identification (cookie value and/or environment variable).

#### NOTE
The website level configuration overrides [organization routing](../../../../configuration/system/websites/global-routing.md#sys-config-sysconfig-websites-routing) configuration, when **Use Organization** box is cleared.

To change the default routing settings for the website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **System Configuration > Websites > Routing** in the menu to the left.
   ![image](user/img/system/websites/web_configuration/website_routing.png)
4. In the **General** section, define the following options:
   * **URL** - Internal links and canonical URLs (meta keywords) on the OroCommerce storefront pages may contain this value as the website base URL. This option value is used in internal links when a customer uses insecure (HTTP) connection. In the canonical links, it is used when the **Canonical URL Security Type** is set to *Secure*.
   * **Secure URL** - Internal links and canonical URLs (meta keywords) on the OroCommerce storefront pages may contain this value as the website base URL. This option value is used in internal links when a customer uses secure (HTTPS) connection. In the canonical links, it is used when the **Canonical URL Security Type** is set to *Insecure*.
   * **Canonical URL Type** - this option defines whether the *System URL* or *Direct URL* should be used as a canonical link in the meta keywords in the page source code.

     When *System URL* is selected, the page URL is built using the system path to the item and its ID (e.g. /product/view/4).

     When *Direct URL* is selected, the page URL is built using the page title (e.g. /500-watt-work-light).

     #### NOTE
     <a href="https://support.google.com/webmasters/answer/139066?hl=en" target="_blank">Canonical link</a> is used to help search engines identify the unique content that should be indexed.
   * **Prefer Self-Contained Web Catalog Canonical URLs** - When this option is disabled, the canonical URLs point to the direct URLs of the underlying content types, if they are available. This option is disabled by default.
   * **Canonical URL Security Type** - This option defines which value should be used as a website base URL in the canonical link in the page meta keywords. Supported options: *Insecure* and *Secure*.

     When *Insecure* is selected, the website base URL in the canonical link matches the **URL** value.

     When *Secure* is selected, the **Secure URL** value is used instead.
   * **Web Catalog** - When you add a web catalog, it populates the main menu and sub-menus of the OroCommerce storefront. If there is no web catalog available, the structure of the master catalog is used to fill the storefront menu. Once you add a web catalog, click **Save Settings** to prompt the system to show you a detailed content tree of the selected web catalog under the **Navigation Root** field.
   * **Navigation Root** - This option is available only if a web catalog has been added. Here, you can select the root content node to be displayed in the OroCommerce storefront. Keep in mind that only the sub-menu nodes that belong to the selected parent node will be visible in the storefront.

   ![The selected sub-menu nodes that will be visible in the storefront.](user/img/system/websites/web_configuration/visible_content_node_website.png)
   * **Main Navigation Menu** - Select which [storefront menu](../../../../../../concept-guides/administration/menus/index.md#menu-management-concept-guide) will represent the [main menu](../../../../../../storefront/getting-started/general-layout.md#frontstore-guide-navigation-main-menu) in the storefront.
   * **Homepage** - When no web catalog is available, you can choose any of the available landing pages as your homepage. Please note that on clean installations of Oro applications, the default homepage is blank.
5. In **Website Matchers**, configure the following values to identify the visitors of your website through various tracking options:
   ![image](user/img/system/config_system/website_matchers.png)
   * **Cookie Value** - A unique website ID that is saved in the cookies and is later used by a website matcher to identify the website customer is on. The cookie name that is configured on the [system level](../../../../configuration/system/websites/global-routing.md#routing-website-matchers-global) combined with the cookie value creates the unique parameter that will identify the required website.
   * **ENV Variable Name** - An environment variable that is used to store the unique website ID that is later used by a website matcher to identify the website customer is on.
   * **ENV Variable Value** - A unique website ID that is saved to the environment variable with the name defined in the option above.
6. To customize any of these options:
   1. Clear the **Use Organization** box next to the option.
   2. Select the new option.
7. Click **Save**.

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
