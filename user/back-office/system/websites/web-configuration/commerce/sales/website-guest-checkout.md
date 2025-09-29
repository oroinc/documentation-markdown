<a id="user-guide-system-configuration-commerce-sales-checkout-website"></a>

<a id="user-guide-system-configuration-commerce-sales-checkout-registration-web"></a>

# Configure Checkout Settings per Website

#### HINT
This section is part of the [Checkout Configuration Concept Guide](../../../../../../concept-guides/checkout/index.md#checkout-management-concept-guide) topic that provides the general understanding of single-page and multi-page checkout concepts.

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Sales > Checkout** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![image](user/img/system/websites/web_configuration/CheckoutWeb.png)
4. Clear the **Use Organization** check box to change the organization-wide setting.
5. In the **Customer Users Registration** section, you can:
   1. **Allow Registration** —  when the option is enabled, registration is allowed for customers on the checkout page.
   2. **Allow Checkout without Email Confirmation** — when the option is enabled, customers proceed to the checkout immediately once registration details are provided. When this option is disabled, the checkout does not start until the user confirms their email address.

   #### NOTE
   By default, both options are *enabled*. However, they are only relevant when [guest checkout](../../../../configuration/commerce/sales/global-checkout-config.md#user-guide-system-configuration-commerce-sales-checkout) is enabled.
6. In the **Guest Checkout** section, set whether guest checkout should be enabled or disabled.

   By default, guest checkout is disabled.
7. In the **Guest Checkout Owner Settings** section, select the default owner of the guest checkout. Depending on the roles and permissions of the owner, guest data (e.g., shopping lists) may or may not be viewed and managed by the users who are subordinated to the owner.

   #### NOTE
   To enable users from the same business unit or organization (that the owner belongs to) to view and manage guest checkout data, adjust permissions for the checkout entity in their roles accordingly.
8. In the **Checkout Options** section, set the following option:
   * **Maximum Line Items per Page** — Set the number of line items to display on the checkout page. The provided value will be used as the implied maximum number of checkout line items to display at once. If the number of checkout line items exceeds this value, the “Show All Items” will no longer be available and this number will be shown as the maximum pager value.
9. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
