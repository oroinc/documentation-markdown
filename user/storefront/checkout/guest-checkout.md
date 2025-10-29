<a id="frontstore-guide-orders-checkout-guest"></a>

# Navigate through Guest Checkout in the Storefront

#### HINT
This section is part of the [Checkout Configuration Concept Guide](../../concept-guides/administration/checkout/index.md#checkout-management-concept-guide) topic that provides a general understanding of single-page and multi-page checkout concepts.

In the Oro storefront, [guest customers](../../concept-guides/administration/guests/index.md#sys-conf-commerce-guest) can place orders similarly to registered users, if guest access is enabled and configured in the [back-office](../../back-office/system/configuration/commerce/sales/index.md#configuration-guide-commerce-configuration-sales). They are, however, limited to just one shopping list.

Unauthenticated customers can proceed to the checkout through:

* Guest Quick Order Forms
* Guest Shopping Lists

At the checkout, guest customers can:

* Login if they have forgotten to do this before placing items in the shopping list
* Create an account

<!-- begin_sample_checkout -->

## Sample Guest Checkout

As an illustration, let us follow the steps of the checkout as an unauthenticated user. The following example has registration options available at the checkout. However, please keep in mind, that your website configuration may be different and registration options may be unavailable.

1. Add selected items to the shopping list.
   ![image](user/img/storefront/orders/SampleGuestCheckout1.png)
2. Navigate to **Shopping List** on the top right of the page, and click **Checkout**.
   ![image](user/img/storefront/orders/SampleGuestCheckout2.png)
3. The following options are available on the page that opens:
   > ![image](user/img/storefront/orders/SampleGuestCheckout5.png)
   * Log in
   * Proceed to Guest Checkout
   * Create an Account and Continue
4. Click **Proceed to Guest Checkout**.

   #### NOTE
   You can also register during later during the order review.
5. Fill in the billing and shipping information, as well as select the shipping method and provide payment details.
   ![image](user/img/storefront/orders/SampleGuestCheckout8.png)
6. At the **Order Review** step, you can save the provided details and create an account.

   As **Save my data and create an account** is enabled, you can provide your credentials for a quick registration:
   * Enter your email address.
   * Enter password.
   * Reenter password for confirmation.

   ![image](user/img/storefront/orders/SampleGuestCheckout9.png)
7. Click **Submit Order**.
8. To complete registration, open your mailbox and check the registration confirmation email.

**Related Articles**

* [Guest Functions Concept Guide](../../concept-guides/administration/guests/index.md#sys-conf-commerce-guest)
* [Enable Global Guest Access in the Back-Office](../../back-office/system/configuration/commerce/guests/index.md#configuration-guide-commerce-configuration-guests)
* [Configure Guest Quick Order Form in the Back-Office](../../back-office/system/configuration/commerce/sales/guest-quick-order-global.md#user-guide-system-configuration-commerce-sales-quick-order-form)
* [Configure Guest Quotes in the Back-Office](../../back-office/system/configuration/commerce/sales/guest-quote.md#sys-conf-commerce-guest-enable-guest-quotes)

<!-- finish_sample_checkout -->
