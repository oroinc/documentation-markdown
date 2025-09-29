<a id="user-guide-system-configuration-commerce-sales-quick-order-form-organization"></a>

# Configure Quick Order Form Settings per Organization

Registered and unregistered customers can use a quick order form for fast purchases in the Oro storefront. By default, quick order form is enabled, while optimized quick order and guest quick order form are disabled. You can configure the quick form functionality on three levels – [globally](../../../../../configuration/commerce/sales/guest-quick-order-global.md#user-guide-system-configuration-commerce-sales-quick-order-form-global), per organization, and [per website](../../../../../websites/web-configuration/commerce/sales/website-guest-quick-order.md#user-guide-system-configuration-commerce-sales-quick-order-form-website).

#### NOTE
Please note that website settings override organization, organization settings override system settings.

To configure the quick order form for registered and unregistered users per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Sales > Quick Order Form** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![Configure quick order form per organization](user/img/system/user_management/org_configuration/sales/org_quick_order_form.png)
1. Clear the **Use System** checkbox to override the system-wide configuration options.
2. In the **Quick Order Form** section:
   * **Enable Quick Order Form** — enable or disable the quick order form functionality for the registered users. By default the quick order form is enabled.
   * **Enable Optimized Quick Order Form** — enable optimized quick order form when you upload over 1000 products per order. By default, the optimized order form is disabled. The feature is available starting from OroCommerce Enterprise v5.0.8. To check which application version you are running, see the [system information](../../../../../system-information/index.md#system-information).
3. In the **Guest Quick Order Form** section, set whether guests are allowed to create a quick order form. By default, the guest quick order form is disabled.
4. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
