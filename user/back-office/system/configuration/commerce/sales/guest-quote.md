<a id="sys-conf-commerce-guest-enable-guest-quotes"></a>

# Configure Global Settings for Quotes

<!-- begin_guest_quote -->

#### HINT
This section is part of the [RFQ and Quote Management](../../../../../concept-guides/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides a general understanding of the RFQ and quote concepts in OroCommerce.

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
4. In the **General** section, toggle the **Enable Quote (Store Front)** option to display or hide the Quote section under the Account menu for registered customers.
5. In the **Guest Quote** section, select the **Enable Guest Quote** checkbox to generate unique links for sending quotes to guest users.
6. Click **Save Settings**.

<!-- finish_guest_quote -->

**Related Topics**

* [Send a Guest Quote in the Back-Office](../../../../sales/quotes/guest-quote.md#user-guide-sales-guest-quotes)
* [Send a Guest Quote in the Storefront](../../../../../storefront/quotes/guests.md#frontstore-guide-guest-quotes)
