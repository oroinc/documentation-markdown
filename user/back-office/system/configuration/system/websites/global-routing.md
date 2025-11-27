<a id="sys-config-sysconfig-websites-routing"></a>

<a id="user-guide-marketing-web-catalog-enable-globally"></a>

# Configure Global Routing Settings

Global routing configuration includes the following information:

* Global website URL when reached using secure (https) and insecure (http) connection
* Options that impact the way metadata for the search engine is generated
* Meaningful URL (e.g. /product/view/4 vs /500-watt-work-light)

#### NOTE
The website routing settings can be configured globally, per [organization](../../../user-management/organizations/org-configuration/general-setup-org/organization-routing.md#organization-config-website-routing), per [website](../../../websites/web-configuration/general-sys-config/websites/website-routing.md#sys-websites-sysconfig-websites-routing), [customer group](../../../../customers/customer-groups/customer-group-configuration/system-configuration/websites/customer-group-routing-settings.md#user-guide-customer-groups-configuration-settings-routing) and [customer](../../../../customers/customers/customer-configuration/system-configuration/website/customer-routing-settings.md#user-guide-customer-configuration-settings-routing).

To change the default global routing settings:

1. Navigate to **System > Configuration** in the main menu.
2. Select **System Configuration > Websites > Routing** in the menu to the left.
3. In the **General** section, define the following options:
   ![Global website routing settings](user/img/system/config_system/routing_general.png)
   * **URL** - Internal links and canonical URLs (meta keywords) on the OroCommerce storefront pages may contain this value as the website base URL. This option value is used in internal links when a customer uses insecure (HTTP) connection. In the canonical links, it is used when the **Canonical URL Security Type** is set to *Secure*.
   * **Secure URL** - Internal links and canonical URLs (meta keywords) on the OroCommerce storefront pages may contain this value as the website base URL. This option value is used in internal links when a customer uses secure (HTTPS) connection. In the canonical links, it is used when the **Canonical URL Security Type** is set to *Insecure*.
   * **Create Redirects** - this option defines a strategy for creating redirects when the URL building rules change. Supported options: *Ask*, *Never*, *Always*.

     When *Ask* is selected, OroCommerce prompts to confirm redirect creation on every change.

     When *Never* is selected, OroCommerce does not create any redirects.

     When *Always* is selected, the redirects are created by default.
   * **Web Catalog** - when a Web Catalog is selected, it populates the main menu and sub-menus on the OroCommerce Storefront. If there is no Web Catalog in OroCommerce, the Master Catalog structure is mimicked.

   Once you decide on the Web Catalog, click **Save Settings**, and the detailed content tree of the selected web catalog appears under the **Navigation Root** field.
   * **Navigation Root** - select the root content node to be displayed in the OroCommerce storefront. Keep in mind that only the sub-menu nodes that belong to the selected parent node will be visible in the storefront.
     ![The selected sub-menu nodes that will be visible in the storefront](user/img/system/config_system/visible_content_node.png)
   * **Main Navigation Menu** - Select which [frontend menu](../../../frontend-menus/index.md#frontend-menus-overview) will represent the [main menu](../../../../../storefront/getting-started/general-layout.md#frontstore-guide-navigation-main-menu) in the storefront.
     ![Illustration of how changing Main Navigation Menu affects the storefront](user/img/system/frontend_menu/main-navigation-menu.png)
4. In the **Direct URLs** section, configure the following settings:
   ![Global Direct URLs settings](user/img/system/config_system/routing_direct_url.png)
   * **Enable Direct URLs** - when enabled, the page URL is built using the page slug (e.g., /500-watt-work-light). When disabled, the system path to the item and its ID is used (e.g., /product/view/4).
   * **Product URL Prefix** - the prefix that is appended to the product slug in the URL.
   * **Brand URL Prefix** - the prefix that is appended to the product brand slug in the URL.
   * **Category URL Prefix** - the prefix that is appended to the category slug in the URL.
   * **Landing Page URL Prefix** - The prefix that is appended to the landing page slug in the URL.

<a id="routing-website-matchers-global"></a>
1. In the **Canonical URLs** section, configure the following parameters:
   ![Global Canonical URLs settings](user/img/system/config_system/routing_canonical_url.png)
   * **Canonical URL Type** - this option defines whether the *System URL* or *Direct URL* should be used as a canonical link in the meta keywords in the page source code.
     * When *System URL* is selected, the page URL is built using the system path to the item and its ID (e.g. /product/view/4).
     * When *Direct URL* is selected, the page URL is built using the page slug (e.g. /500-watt-work-light).

     #### NOTE
     <a href="https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls?hl=en&visit_id=638162001252801531-2888881340&rd=1" target="_blank">Canonical link</a> is used to help search engines identify the unique content that should be indexed. Switching from one setting to the other does not modify the data stored in the database, it only controls which data is used to as a canonical URL.
   * **Canonical URL Security Type** - this option defines which value should be used as a website base URL in the canonical link in the page meta keywords. Supported options: *Insecure* and *Secure*.
     * When *Insecure* is selected, the website base URL in the canonical link matches the **URL** value.
     * When *Secure* is selected, the **Secure URL** value is used instead.
   * **Use Localized Canonical URLs** - When this option is enabled, the system generates canonical URLs using the localized version of URLs slugs (if available).
   * **Prefer Self-Contained Web Catalog Canonical URLs** - When this option is disabled, the canonical URLs point to the direct URLs of the underlying content types, if they are available. This option is enabled by default.
2. In **Website Matchers**, configure the following parameters to identify the visitors of your website through various tracking options:
   ![Global website matchers configuration](user/img/system/config_system/routing_website_matchers.png)

   #### NOTE
   The Website Matchers feature is only available in the Enterprise edition.

   * **Website Matchers** - with this option, you can define the way OroCommerce will identify the website customer uses. It is recommended to select at least one option. Supported options: *ENV Variable Based*, *Cookie Based*, *URL Based*. When more than one option is selected, set the method priority in the **sort order** column to define the most reliable and trusted one.
   * **Enable Redirect** - indicates whether the customer should be automatically redirected to the website that was identified using one of the website matching methods (e.g., user navigated to the *us-store.com* but their cookies indicate that they are visiting the *uk-store.com*).
   * **Cookie Name** - the name of the cookie that stores information about the current website in the customer’s browser. To track the website, you need to set the related cookie value in the [website’s configuration](../../../websites/web-configuration/general-sys-config/websites/website-routing.md#sys-websites-sysconfig-websites-routing) creating an individual parameter specific for the required website.
3. To customize any of these options:
   1. Clear the **Use Default** box next to the option.
   2. Select the new option.
4. Click **Save Settings**.
