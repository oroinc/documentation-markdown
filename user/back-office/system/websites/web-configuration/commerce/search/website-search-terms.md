<a id="configuration-website-commerce-search-history"></a>

<a id="configuration-guide-commerce-configuration-search-empty-page-results-website"></a>

# Configure Search Terms Settings per Website

#### HINT
Read [Search Functions Concept Guide](../../../../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search) to get a general understanding of the search functionality in OroCommerce.

#### NOTE
You can configure search history [globally](../../../../configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-history), [per organization](../../../../user-management/organizations/org-configuration/commerce/search/org-search-terms.md#organization-commerce-configuration-search-history), [customer group](../../../../../customers/customer-groups/customer-group-configuration/commerce/search/customer-group-search-terms-settings.md#user-guide-customer-groups-configuration-settings-search), or [customer](../../../../../customers/customers/customer-configuration/commerce/search/customer-search-settings.md#user-guide-customers-search-settings), and empty search results page [globally](../../../../configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-empty-search-results-global), [per organization](../../../../user-management/organizations/org-configuration/commerce/search/org-search-terms.md#configuration-guide-commerce-configuration-search-empty-page-results-org), and website.

To configure the search history settings per website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> more actions menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Search > Search Terms** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![Search history configuration options per website](user/img/system/websites/web_configuration/web-search-terms.png)
1. In the **Search History** section, clear the *Use Organization* checkbox to configure the following search history reporting options:
   * **Enable Search History Reporting** — enables the [Search History feature](../../../../../marketing/search/index.md#user-guide-search-search-history) globally to track your customers’ search activity in the storefront. The option also enables the [a Search Terms report](../../../../../reports-segments/reports/search-report.md#user-guide-search-terms-report) that collects statistics on how many times a particular search term was used, the number of times that search term returned products, and the number of times it returned an empty result. When Enable Search History Reporting is disabled, the feature is removed from the main menu and grids, along with the Search Terms report.
   * **Enable Search History Collection** — depends on the Enable Search History Reporting option above. When Enable Search History Collection is enabled, all search queries are logged into the database. This option allows enabling/disabling certain groups of visitors. For example, you can choose not to log requests from anonymous users by turning off this option at customer group level for Anonymous customers. Exercise care when enabling this option on popular websites as it may result in a large number of records saved to the database.
2. In the **Special Pages** section, clear the *Use Organization* checkbox to configure the empty search results page:
   * **Empty Search Result Page** — You can configure an Empty Search Results Page, if the product search produced an empty result and there is no custom page configured for that specific combination of a [search term](../../../../../marketing/search/index.md#user-guide-search-search-terms) and additional search criteria. The web-node selected for this configuration option should be available for all users and cannot have restrictions.

   #### NOTE
   This option is available starting from OroCommerce version 6.0.2.
3. Click **Save Settings**.

**Related Topics**

* [Manage Search History in the Back-Office](../../../../../marketing/search/index.md#user-guide-search-search-history)
* [Search (Terms) Report](../../../../../reports-segments/reports/search-report.md#user-guide-search-terms-report)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
