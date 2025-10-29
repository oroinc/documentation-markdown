<a id="user-guide-payment-payment-providers-overview-infinitepay"></a>

# Manage InfinitePay Payment Service in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment) topic that provides a general understanding of the payment concept in OroCommerce.

#### HINT
The feature requires extension, so visit Oro Extensions Store to download the <a href="https://marketplace.oroinc.com/orocommerce/extension/orocommerce-infinitepay-integration/" target="_blank">InfinitePay extension</a> and then use the composer to [install the extension to your application](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

InfinitePay is a financial management company that provides guaranteed delayed payments on open account terms.

Integration of OroCommerce with InfinitePay enables you to secure your company from financial risks related to delayed payments.

You can secure payments from the buyers in more than 40 countries worldwide. Contact the InfinitePay support for the complete list of the countries in which InfinitePay supports claims.

To set up InfinitePay payment service in OroCommerce:

1. Learn the [Prerequisites for InfinitePay Integration](infinitepay-prerequisites.md#user-guide-payment-prerequisites-infinitepay) that will help configure the integration properly and retrieve corresponding credentials.
2. Configure [InfinitePay Integration](infinitepay-integration.md#sys-integrations-manage-integrations-infinitepay) under **System > Integrations > Manage Integrations**.
3. Create a [payment rule](../../../payment-rules/index.md#sys-payment-rules) under **System > Payment Rules** and add your integration to it to display this method to the customers at the checkout.

<a id="user-guide-payment-configuration-payment-method-integration-infinitepay-payment-actions"></a>

## Guarantee Actions

Depending on the way InfinitePay integration parameters are configured, the following InfinitePay transaction(s) may happen when the order is submitted using the InfinitePay payment method:

* **Reserve** — the buyer’s identity and credit worthiness are verified by InfinitePay. This acts as a basic validation of the future payment and happens for every order where InfinitePay is selected as a payment method.
* **Capture** — confirms the order submission, automatically transfers the order to Financial Management Solutions where the buyer’s InfinitePay guaranteed limit is adjusted by deducting the reserved amount. When the **Auto-Capture** is *enabled*, this transaction happens for every order submitted via InfinitePay.
* **Activate** — as a result of payment activation step, InfinitePay guarantees or denies the payment based on the payment due date and shipping information. When **Auto-Activation** is *enabled*, this transaction happens for every order submitted via InfinitePay.

  #### NOTE
  When InfinitePay denies the activation, to unblock the debtor limit, the order needs to be canceled manually via the InfinitePay portal.

**Related Topics**

* [Payment Configuration Concept Guide](../../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
