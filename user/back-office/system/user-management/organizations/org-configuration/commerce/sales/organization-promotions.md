<a id="sys-conf-commerce-sales-promotions-organization"></a>

# Configure Promotions Settings per Organization

The settings controls whether to enable or disable entering coupon codes that are different only by letter case (e.g., *SpringSale*, *SPRINGSALE*, *springsale*) during the checkout. Depending on the configuration you set, the coupon codes can be considered either equal or different.

#### NOTE
The configuration is available [globally](../../../../../configuration/commerce/sales/promotions-settings.md#sys-config-commerce-sales-promotions) in Community edition. In Enterprise edition, it’s available at the organization level only.

To configure the setting per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Sales > Promotions** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![Configure promotions per organization](user/img/system/user_management/org_configuration/sales/promotions-org.png)

1. Clear the **Use System** checkbox to customize the setting.
2. **Case-Insensitive Coupon Codes** — The option determines whether to consider or ignore the letter case of the applied coupon codes. By default, the option is disabled, meaning that the system carefully checks the entered coupon code against the letter case, so *SpringSale*, *SPRINGSALE*, and *springsale*, are considered to be the three different codes. When the option is enabled, the mentioned codes will be considered equal.
3. Click **Save**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
