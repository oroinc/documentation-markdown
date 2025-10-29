<a id="user-guide-customers-checkout-settings"></a>

# Configure Checkout (Order Limits) Settings per Customer

#### NOTE
You can configure checkout settings [globally](../../../../../system/configuration/commerce/sales/global-checkout-config.md#user-guide-system-configuration-commerce-sales-checkout), [per organization](../../../../../system/user-management/organizations/org-configuration/commerce/sales/organization-guest-checkout.md#user-guide-system-configuration-commerce-sales-organization), [website](../../../../../system/websites/web-configuration/commerce/sales/website-guest-checkout.md#user-guide-system-configuration-commerce-sales-checkout-website), [customer group](../../../../customer-groups/customer-group-configuration/commerce/sales/customer-group-checkout-settings.md#user-guide-customer-group-checkout-settings), or customer.

The Checkout Order Limits functionality allows merchants to set Minimum Order Values for specific customers. This feature helps prevent small and unprofitable orders from being processed. If a customer’s shopping list subtotal is below the set minimum, they will see a notification indicating the required amount to check out. Once the subtotal exceeds the minimum, the notification will disappear, and the “Create Order” button will become enabled.

To configure the checkout order limits per customer:

1. Navigate to **Customers > Customers** in the main menu.
2. For the necessary customer, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.

![Checkout order limits customer configuration settings](user/img/customers/customers/configuration/customer-order-limits-settings.png)
1. Select **Commerce > Sales > Checkout** in the menu to the left.
2. In the Checkout section, clear the **Use Customer Group** checkbox and configure the following options:
   * **Minimum Order Amount** — Specify the minimum subtotal required to start the checkout process. If the shopping list subtotal is less than the specified value, the **Checkout** button will be disabled, and customers will see an error notification, prompting them to add more products to proceed. Once the subtotal meets or exceeds the minimum amount, the error message disappears, and the **Checkout** button is enabled. If [multiple currencies](../../../../../system/user-management/organizations/org-configuration/general-setup-org/organization-currency.md#admin-configuration-currency-org) are enabled in the storefront, they are rendered as separate inputs for each currency. Validation in the storefront uses the value configured for the current currency. No automatic currency conversions are applied.
   * **Maximum Order Amount** — Specify the maximum subtotal required to start the checkout. If the shopping list subtotal exceeds the specified value, the **Checkout** button will be disabled, and customers will see an error notification, prompting them to remove some products to proceed. Once the subtotal is within the allowed limit, the error message disappears, and the **Checkout** button is enabled. If [multiple currencies](../../../../../system/user-management/organizations/org-configuration/general-setup-org/organization-currency.md#admin-configuration-currency-org) are enabled in the storefront, they are rendered as separate inputs for each currency. Validation in the storefront uses the value configured for the current currency. No automatic currency conversions are applied.
3. Click **Save Settings**.

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
