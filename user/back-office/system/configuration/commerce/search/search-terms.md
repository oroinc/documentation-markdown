<a id="configuration-guide-commerce-configuration-search-history"></a>

<a id="configuration-guide-commerce-configuration-search-empty-search-results-global"></a>

# Configure Global Search Terms Settings

#### HINT
Read [Search Functions Concept Guide](../../../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search) to get a general understanding of the search functionality in OroCommerce.

#### NOTE
You can configure search history globally, [per organization](../../../user-management/organizations/org-configuration/commerce/search/org-search-terms.md#organization-commerce-configuration-search-history), [website](../../../websites/web-configuration/commerce/search/website-search-terms.md#configuration-website-commerce-search-history), [customer group](../../../../customers/customer-groups/customer-group-configuration/commerce/search/customer-group-search-terms-settings.md#user-guide-customer-groups-configuration-settings-search), or [customer](../../../../customers/customers/customer-configuration/commerce/search/customer-search-settings.md#user-guide-customers-search-settings), and empty search results page globally, [per organization](../../../user-management/organizations/org-configuration/commerce/search/org-search-terms.md#configuration-guide-commerce-configuration-search-empty-page-results-org), and [website](../../../websites/web-configuration/commerce/search/website-search-terms.md#configuration-guide-commerce-configuration-search-empty-page-results-website).

To configure the search history settings globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Search > Search Terms** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Global search history configuration options](user/img/system/config_commerce/search/global-search-history-settings.png)
1. In the **Search History** section, clear the *Use Default* checkbox to configure the following search history reporting options:
   * **Enable Search History Reporting** — enables the [Search History feature](../../../../marketing/search/index.md#user-guide-search-search-history) globally to track your customers’ search activity in the storefront. The option also enables the [a Search Terms report](../../../../reports-segments/reports/search-report.md#user-guide-search-terms-report) that collects statistics on how many times a particular search term was used, the number of times that search term returned products, and the number of times it returned an empty result. When Enable Search History Reporting is disabled, the feature is removed from the main menu and grids, along with the Search Terms report.
   * **Enable Search History Collection** — depends on the Enable Search History Reporting option above. When Enable Search History Collection is enabled, all search queries are logged into the database. This option allows enabling/disabling certain groups of visitors. For example, you can choose not to log requests from anonymous users by turning off this option at customer group level for Anonymous customers. Exercise care when enabling this option on popular websites as it may result in a large number of records saved to the database.
2. In the **Special Pages** section, clear the *Use Default* checkbox to configure the empty search results page:
   * **Empty Search Result Page** — You can configure an Empty Search Results Page, if the product search produced an empty result and there is no custom page configured for that specific combination of a [search term](../../../../marketing/search/index.md#user-guide-search-search-terms) and additional search criteria. The web-node selected for this configuration option should be available for all users and cannot have restrictions.
3. Click **Save Settings**.

**Related Topics**

* [Manage Search History in the Back-Office](../../../../marketing/search/index.md#user-guide-search-search-history)
* [Search (Terms) Report](../../../../reports-segments/reports/search-report.md#user-guide-search-terms-report)
