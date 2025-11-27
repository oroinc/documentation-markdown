<a id="configuration-guide-commerce-configuration-sales-rfq"></a>

<a id="user-guide-system-configuration-commerce-sales-rfq"></a>

<a id="sys-conf-commerce-sales-rfq-notifications-general"></a>

<a id="user-guide-system-configuration-commerce-sales-rfq-global"></a>

# Configure Global Request for Quote Settings

#### HINT
This section is part of the [RFQ and Quote Management](../../../../../concept-guides/customers-sales/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides a general understanding of the RFQ and quote concepts in OroCommerce.

On the RFQ configuration page, you can enable RFQ feature for the back-office and storefront, control RFQ Notification options and Guest RFQs.

The rfq settings can be configured on three levels – globally, [per organization](../../../user-management/organizations/org-configuration/commerce/sales/organization-guest-rfq.md#user-guide-system-configuration-commerce-sales-rfq-organization), and [per website](../../../websites/web-configuration/commerce/sales/website-guest-rfq.md#sys-conf-commerce-sales-rfq-notifications-website). Please note that website settings override organization, organization settings override system settings.

To configure the request for quote settings globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Sales > Request for Quote** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Global rfq configuration](user/img/system/config_commerce/sales/global_rfq_options.png)
1. Clear the **Use Default** checkbox to override the default configuration options.
2. In the **General** section, customize the following options:
   * **Enable RFQ** — the option enables the OroCommerce-driven RFQ functionality for the back-office. The back-office users will be able to work with the submitted RFQs, process them, and convert to quotes if accepted.
   * **Enable RFQ (Storefront)** — the option enables the OroCommerce-driven RFQ functionality for the storefront. Your customers will be able to submit RFQs from the storefront.
   * **Enable RFQ Project Name** — this option enables project name management for RFQs in the storefront. In the back-office, the feature is enabled automatically if it is turned on for an organization or for at least one website within that organization. Once active, a Project Name field appears on RFQ edit pages, and a Project Name column is added to the RFQ grid in the back-office. The project name serves as an optional identifier that helps users search for and track RFQs by name, particularly when records originate from external systems or third parties.
     ![Illustration of a project name field on the rfq edit page and a project name column in the rfq grid](user/img/system/config_commerce/sales/rfq-project-name.png)
3. In the **Notifications** section, configure notifications for all the parties concerned, namely:
   * an assigned sales representatives of the customer
   * the owner of the customer user
   * the owner of the customer

For the aforementioned parties the options are the following:

> * Select **Always** to notify the related entity each time an RFQ is submitted.
> * Select **If user has no sales reps assigned** to notify the related entity only in case they do not have any assigned sales representatives.
1. In the **Guest RFQ** section, set whether guests are allowed to request quotes on the items they are interested in. This will also allow sales reps collect information on potential sales in the back-office.

> #### HINT
> Make sure you enable [Guest Shopping Lists](global-shopping-list.md#user-guide-system-configuration-commerce-sales-shopping-list) in the back-office to let guest customers create RFQs from the shopping lists in their storefront.

> By default, guest request for quote submission is disabled. To enable it, clear *Use Default* and select the *Enable Guest RFQ* checkbox. When the guest RFQ is enabled, click **Save Settings** to display the additional **Guest RFQ Owner Settings** section.
1. In the **Guest RFQ Owner Settings** section, select the user who will be the default owner of all guest RFQs.  Depending on the roles and permissions of the owner, guest RFQs may or may not be viewed and managed by the users who are subordinated to the owner.

#### NOTE
To enable users from the same business unit or organization (that the owner belongs to) to view and manage guest RFQs, adjust permissions for the Request for Quote entity in their roles accordingly.

1. Click **Save Settings**.

<!-- finish_rfq -->
