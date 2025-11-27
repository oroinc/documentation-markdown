<a id="user-guide-system-configuration-commerce-sales-rfq-organization"></a>

# Configure Request for Quote Settings per Organization

#### HINT
This section is part of the [RFQ and Quote Management](../../../../../../../concept-guides/customers-sales/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides a general understanding of the RFQ and quote concepts in OroCommerce.

On the RFQ configuration page, you can enable RFQ feature for the back-office and storefront, control RFQ Notification options and Guest RFQs.

To configure the request for quote settings per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Sales > Request for Quote** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![Rfq configuration options per organization](user/img/system/user_management/org_configuration/sales/org_rfq_config.png)
4. Clear the **Use System** checkbox to override the global configuration options.
5. In the **General** section, customize the following options:
   * **Enable RFQ** — the option enables the OroCommerce-driven RFQ functionality for the back-office. The back-office users will be able to work with the submitted RFQs, process them, and convert to quotes if accepted.
   * **Enable RFQ (Storefront)** — the option enables the OroCommerce-driven RFQ functionality for the storefront. Your customers will be able to submit RFQs from the storefront.
   * **Enable RFQ Project Name** — this option enables project name management for RFQs in the storefront. In the back-office, the feature is enabled automatically if it is turned on for an organization or for at least one website within that organization. Once active, a Project Name field appears on RFQ edit pages, and a Project Name column is added to the RFQ grid in the back-office. The project name serves as an optional identifier that helps users search for and track RFQs by name, particularly when records originate from external systems or third parties.
6. In the **Notifications** section, configure notifications for all the parties concerned, namely:
   * an assigned sales representatives of the customer
   * the owner of the customer user
   * the owner of the customer

For the aforementioned parties the options are the following:

> * Select **Always** to notify the related entity each time an RFQ is submitted.
> * Select **If user has no sales reps assigned** to notify the related entity only in case they do not have any assigned sales representatives.
1. In the **Guest RFQ** section, set whether guests are allowed to submit a request for quote. By default, guest request for quote submission is disabled. To enable it, clear *Use System* and select the *Enable Guest RFQ* checkbox. When the guest RFQ is enabled, click **Save Settings** to display the additional **Guest RFQ Owner Settings** section.

> #### HINT
> Make sure you enable [Guest Shopping Lists](organization-guest-shopping-list.md#user-guide-system-configuration-commerce-sales-shopping-list-per-organization) in the back-office to let guest customers create RFQs from the shopping lists in their storefront.
1. In the **Guest RFQ Owner Settings** section, select the user who will be the default owner of all guest RFQs.  Depending on the roles and permissions of the owner, guest RFQs may or may not be viewed and managed by the users who are subordinated to the owner.

   #### NOTE
   To enable users from the same business unit or organization (that the owner belongs to) to view and manage guest RFQs, adjust permissions for the Request for Quote entity in their roles accordingly.
2. Click **Save Settings**.

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
