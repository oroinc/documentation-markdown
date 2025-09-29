<a id="user-guide-payment-payment-providers-overview-paypal"></a>

# Configure Multiple PayPal Payment Services in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment) topic that provides a general understanding of the payment concept in OroCommerce.

PayPal is a fast, safe and reliable online global payment system that offers easy online payments for businesses and individuals.

OroCommerce supports integration with PayPal services to offer the following payment methods:

* **PayPal Payflow Gateway**
* **PayPal Payments Pro**
* **PayPal Express Package**

#### NOTE
Depending on PayPal policies, payment methods may be different in various countries. Therefore, the list of available payment methods in OroCommerce may also vary when integrated using PayPal accounts created in different countries.

## PayPay Services Overview

### PayPal Payflow Payment Gateway VS PayPal Payments Pro

* **PayPal Payflow Gateway** is a secure payment gateway that receives information about payments via debit and credit cards, authorizations, captures, etc., processes this information and sends payment transactions to the external payment processor that handles the credit card payments.
* **PayPal Payment Pro** uses PayPal Payflow Payment Gateway and PayPal payment processor.

### PayPal Gateway/Pro Ordinary VS Express Checkout

* For the **ordinary** checkout, a customer user enters the card number, issue date, and, optionally, CVV code. This information is kept in their browser until it is sent directly to the payment gateway server (avoiding the website). Ordinary checkout in OroCommerce enables delayed payment capture.
* The **express** checkout helps the customer user complete payment immediately using the credit card payment capture form hosted by PayPal or via their PayPal account.

<a id="user-guide-payment-payment-providers-overview-paypal-express"></a>

### PayPal Express Payment Service Package

It is a fast, safe and reliable online global payment system that offers easy online payments for businesses and individuals.

PayPal Express, **unlike Gateway and Pro**, comes as a separate OroCommerce package and requires [installation](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer) of the <a href="https://packagist.oroinc.com/?#oro/paypal-express" target="_blank">Oro PayPal Express Integration</a> package.

Keep in mind that depending on PayPal policies, payment methods may be different in some countries. Therefore, the list of available payment methods in OroCommerce may also vary when integrated using PayPal accounts created in different countries. You can verify PayPal Express availability in your country on the <a href="https://www.paypal.com/us/webapps/mpp/country-worldwide" target="_blank">PayPal website</a>.

## PayPal Gateway/Pro Configuration Flow

To enable PayPal payment methods at the checkout of the OroCommerce storefront:

1. Learn the [Prerequisites for PayPal Services Integration](paypal-prerequisites.md#user-guide-payment-prerequisites-paypal) that will help configure the integration properly and retrieve corresponding credentials. Keep in mind that you might need a separate instance for a sandbox, test, staging/pre-production, and production environment.
2. Configure [PayPal Payflow Gateway/PayPal Payment Pro Integration](gateway-pro/index.md#sys-integrations-manage-integrations-paypal-payflow-gateway) under **System > Integrations > Manage Integrations** filling in the corresponding section of the integration configuration page.
3. Create a [payment rule](../../../payment-rules/index.md#sys-payment-rules) under **System > Payment Rules** and add your integration to it to display this method to the customers at the checkout.

## PayPal Express Configuration Flow

1. Install <a href="https://packagist.oroinc.com/#oro/paypal-express" target="_blank">PayPal Express Package</a>.
2. Learn the [Prerequisites for PayPal Express Configuration](express/paypal-express-prerequisites.md#user-guide-payment-prerequisites-paypal-express).
3. Configure [PayPal Express Integration](express/index.md#config-guide-payment-paypal-express) under **System > Integrations > Manage Integrations**.
4. Create a [payment rule](../../../payment-rules/index.md#sys-payment-rules) under **System > Payment Rules** and add your integration to it to display this method to the customers at the checkout.

**Related Articles**

* [Payment Configuration Concept Guide](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment)
* [Payment Actions (Authorize/Authorize and Charge)](paypal-payment-actions.md#user-guide-payment-configuration-payment-method-integration-payment-actions)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
