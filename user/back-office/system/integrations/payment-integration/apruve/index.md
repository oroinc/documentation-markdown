<a id="user-guide-payment-payment-providers-overview-apruve"></a>

# Manage Apruve Payment Service in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment) topic that provides a general understanding of the payment concept in OroCommerce.

#### HINT
The feature requires extension, so visit Oro Extensions Store to download the <a href="https://marketplace.oroinc.com/orocommerce/extension/orocommerce-and-apruve-integration/" target="_blank">Apruve extension</a> and then use the composer to [install the extension to your application](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

Apruve is a B2B credit management service that provides a credit line for your buyers. Apruve manages business account for OroCommerce sellers starting from credit approval and financing and facilitates credit-related interactions with buyer via their account set up, invoicing, and payment.

Integration of OroCommerce with Apruve enables you to secure your company from financial risks related to delayed payments. Apruve allows you to get the payment within 24 hours of any invoice being generated. You offer terms to your customer but still get the payment for your sales within 1 day.

To set up Apruve payment service in OroCommerce:

1. Learn the [Prerequisites for Apruve Integration](apruve-prerequisites.md#user-guide-payment-prerequisites-apruve) that will help configure the integration properly and retrieve corresponding credentials.
2. Configure [Apruve Payment Method Integration](apruve-integration.md#user-guide-payment-configuration-payment-method-integration-apruve) under **System > Integrations > Manage Integrations**.
3. Create a [payment rule](../../../payment-rules/index.md#sys-payment-rules) under **System > Payment Rules** and add your integration to it to display this method to the customers at the checkout.

**Related Topics**

* [Payment Configuration Concept Guide](../../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
