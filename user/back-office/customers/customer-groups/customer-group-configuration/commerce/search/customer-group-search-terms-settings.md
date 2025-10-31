<a id="user-guide-customer-groups-configuration-settings-search"></a>

# Configure Search History Settings per Customer Group

#### HINT
Read [Search Functions Concept Guide](../../../../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search) to get a general understanding of the search functionality in OroCommerce.

#### NOTE
You can configure search history globally, [per organization](../../../../../system/user-management/organizations/org-configuration/commerce/search/org-search-terms.md#organization-commerce-configuration-search-history), [website](../../../../../system/websites/web-configuration/commerce/search/website-search-terms.md#configuration-website-commerce-search-history), customer group, or [customer](../../../../customers/customer-configuration/commerce/search/customer-search-settings.md#user-guide-customers-search-settings).

Search History enables users to view a history of all searches performed in the storefront.

To configure the search history settings per customer group:

1. Navigate to **Customers > Customer Groups** in the main menu.
2. For the necessary customer group, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary group and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.

![Customer group search terms configuration settings](user/img/customers/customer_groups/configuration/customer-group-config-search.png)
1. Select **Commerce > Search > Search Terms** in the menu to the left.
2. In the Search History section, clear the **Use Website** checkbox and configure the following option:
   * **Enable Search History Collection** - depends on the [Enable Search History Reporting option](../../../../../system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-history). When Enable Search History Collection is enabled, all search queries are logged into the database. This option allows enabling/disabling certain groups of visitors. For example, you can choose not to log requests from anonymous users by turning off this option at customer group level for Anonymous customers. Exercise care when enabling this option on popular websites as it may result in a large number of records saved to the database.
3. Click **Save Settings**.

**Related Topics**

* [Manage Search History in the Back-Office](../../../../../marketing/search/index.md#user-guide-search-search-history)
* [Search (Terms) Report](../../../../../reports-segments/reports/search-report.md#user-guide-search-terms-report)

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
