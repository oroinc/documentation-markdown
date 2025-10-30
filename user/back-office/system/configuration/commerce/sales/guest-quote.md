<a id="sys-conf-commerce-guest-enable-guest-quotes"></a>

# Configure Global Settings for Quotes

<!-- begin_guest_quote -->

#### HINT
This section is part of the [RFQ and Quote Management](../../../../../concept-guides/customers-sales/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides a general understanding of the RFQ and quote concepts in OroCommerce.

The section describes how to enable or disable the quote functionality for the registered and guest users. The settings can be configured on three levels, [global](#sys-conf-commerce-guest-enable-guest-quotes), [organization](../../../user-management/organizations/org-configuration/commerce/sales/organization-quote.md#sys-organization-quotes), and [website](../../../websites/web-configuration/commerce/sales/website-quotes.md#sys-websites-quotes).

#### NOTE
Keep in mind that the following options must be enabled, too:

* [Guest Website Access](../guests/global-guest-access.md#sys-conf-commerce-guest-enable-access)
* [Guest Checkout](global-checkout-config.md#user-guide-system-configuration-commerce-sales-checkout)
* [Guest RFQ](rfq.md#user-guide-system-configuration-commerce-sales-rfq)
* [Guest Shopping List](global-shopping-list.md#user-guide-system-configuration-commerce-sales-shopping-list)

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Sales > Quotes** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![System configuration option for enabling quotes](user/img/system/config_commerce/sales/global_quote_config.png)
3. Clear the **Use Default** checkbox to change the value.
4. In the **General** section, toggle the following options:
   * **Enable Quote (Storefront)** — allows you to control whether to display or hide the Quote section under the Account menu for registered customers.

   #### NOTE
   The Enable Quote Project Name feature was introduced in OroCommerce versions 6.1.3 and 6.1.4.

   * **Enable Quote Project Name** — this option enables project name management for quotes in the storefront. In the back-office, the feature is enabled automatically if it is turned on for an organization or for at least one website within that organization. Once active, a Project Name field appears on quote edit pages, and a Project Name column is added to the quotes grid in the back-office. The project name serves as an optional identifier that helps users search for and track quotes by name, particularly when records originate from external systems or third parties.
5. In the **Guest Quote** section, select the **Enable Guest Quote** checkbox to generate unique links for sending quotes to guest users.
6. Click **Save Settings**.

<!-- finish_guest_quote -->

**Related Topics**

* [Send a Guest Quote in the Back-Office](../../../../sales/quotes/guest-quote.md#user-guide-sales-guest-quotes)
* [Send a Guest Quote in the Storefront](../../../../../storefront/quotes/guests.md#frontstore-guide-guest-quotes)
