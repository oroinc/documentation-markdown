<a id="sys-config-commerce-sales-promotions"></a>

# Configure Global Promotions Settings

<!-- begin -->

You can enable or disable [promotions](../../../../marketing/promotions/promotions/index.md#user-guide-marketing-promotions) and [coupons](../../../../marketing/promotions/coupons/index.md#user-guide-marketing-promotions-coupons), as well as control their strategy across your application in the system configuration. You can also control whether to enable or disable entering coupon codes that are different only by letter case (e.g., *SpringSale*, *SPRINGSALE*, *springsale*) during the checkout.

To reach promotion configuration:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Sales > Promotion** in the menu to the left.

![Global promotions configuration](user/img/system/config_commerce/sales/PromotionSysConfig.png)

#### NOTE
By default, promotions are enabled and the **Combine All Discounts** strategy is set.

1. To customize the default settings, clear the **Use Default** checkbox next to the option.
2. Enable or disable the following options as required:

**Enable Promotions** — the option determines whether to activate or deactivate the promotions feature and promotions-related functionality in your Oro application.

**Case-Insensitive Coupon Codes** — the option determines whether to consider or ignore the letter case of the applied coupon codes. By default, the option is disabled, meaning that the system carefully checks the entered coupon code against the letter case, so *SpringSale*, *SPRINGSALE*, and *springsale*, are considered to be the three different codes. When the option is enabled, the mentioned codes will be considered equal.

> #### NOTE
> The Case-Insensitive Coupon Codes setting is available globally in Community edition. In Enterprise edition, it’s available at the [organization](../../../user-management/organizations/org-configuration/commerce/sales/organization-promotions.md#sys-conf-commerce-sales-promotions-organization) level only.

**Discount Strategy** — the option determines which strategy to use when calculating the promotion discount for a product:

> * When *Combine All Discounts* is selected, all discount options applicable to products are used in combination.
> * When *Best Value Discounts Only* is selected, only the promotion that gives the best value is applied to products.
1. Click **Save**.

**Related Topics**

* [Promotions in OroCommerce](../../../../marketing/promotions/promotions/index.md#user-guide-marketing-promotions)
* [Promotions and Coupons in Use](../../../../marketing/promotions/coupons/sample-coupon.md#user-guide-marketing-promotions-coupons-sample)
* [Coupons](../../../../marketing/promotions/coupons/index.md#user-guide-marketing-promotions-coupons)

<!-- finish -->
