<a id="user-guide-payment-payment-providers-cybersource"></a>

# Configure Integration with CyberSource Payment Service

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment) topic that provides the general understanding of the payment concept in OroCommerce.

#### HINT
The feature requires extension, so visit Oro Extensions Store to download the <a href="https://marketplace.oroinc.com/orocommerce/extension/cybersource-orocommerce-integration/" target="_blank">CyberSource extension</a> and then use the composer to [install the extension to your application](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

CyberSource provides a secure online payment solution that enables global payment processing. The CyberSource gateway accepts all mainstream credit cards, debit cards, and other payment types.

## Integration Prerequisites

To start using CyberSource with OroCommerce application, make sure you have:

1. Registered and created a merchant profile with CyberSource.
2. Enabled the card types that you want to use for payment transactions.
3. Configured each card type.
4. <a href="https://support.cybersource.com/s/article/How-to-Create-or-Update-a-Secure-Acceptance-security-key" target="_blank">Added a security key</a>.
5. Enabled your profile.
6. <a href="https://developer.cybersource.com/api/developer-guides/dita-gettingstarted/authentication/createSharedKey.html" target="_blank">Generated an API key</a>.

## Configure Integration Settings in the Back-Office

To configure the integration between CyberSource and OroCommerce, follow the steps outlined below:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu of the OroCommerce back-office.
2. Click **Create Integration** on the top right.
3. Provide the following information in the form:
   <br/>
   ![Create an integration with Cybersource in the back-office](user/img/system/integrations/cybersource/create-integration.png)
   <br/>
   * **Type** - Select *CyberSource* from the drop-down list.
   * **Name** - Provide the payment method name that is shown as an option for payment configuration in the OroCommerce back-office.
   * **Label** - The payment method name/label displayed as a payment option for the buyer in the OroCommerce storefront during the checkout. To translate the label into other languages, click on the icon next to the field.
   * **Short label** - The payment method name/label that is shown in the order details in the OroCommerce back-office and storefront after the order is submitted. To translate the label into other languages, click on the icon next to the field.
   * **Method** - Select integration method from the list:
     * *Hosted Checkout* - When a customer in the storefront creates an order, they are redirected to a CyberSource payment form page to provide card authorization details. Any payment type supported by CyberSource is allowed.
       ![Payment in the storefront with hosted checkout](user/img/system/integrations/cybersource/hosted-checkout-storefront.png)
     * *Checkout API* - Payment is processed via an API call. Only debit and credit cards are allowed.
       ![Payment in the storefront with checkout API](user/img/system/integrations/cybersource/checkout-api-storefront.png)
   * **Test Mode** — Select this check box to use CyberSource in the test mode that enables you to use the connection to the gateway without sending transaction information for processing.
   * **Merchant ID** - A CyberSource Merchant ID, also referred to as Organization ID, is a unique value within CyberSource that you define during account registration.
   * **Merchant Descriptor** - Enables you to submit merchant descriptor value displayed on a cardholder’s statement.
   * **Profile ID** - Identifies the profile to use with each transaction
   * **Assess Key** - Secure Sockets Layer (SSL) authentication with Secure Acceptance.
   * **API Key** - An identifier that helps authenticate your account. You must use separate keys for the test and production environments.
   * **API Secret Key** - A pre-shared key used to cipher payment information. You must use separate keys for the test and production environments.
   * **Secret Key** - Signs the transaction data and is required for each transaction.
   * **Default Owner** - A user who is responsible for this integration and manages it.
4. Click **Save and Close**.

#### IMPORTANT
Once the integration with CyberSource is created, the next step is to [set up a payment rule](../../../payment-rules/index.md#sys-payment-rules) that enables CyberSource payment methods for all or some customer orders in the OroCommerce application.

## Process Payments in OroCommerce Back-Office

To view orders and payment details for orders in the OroCommerce back-office, navigate to **Sales > Orders** in the main menu.

You can either *Capture* a payment, or *Cancel* it in **Payment History** of a particular order.

* When you click **Capture**, the customer is charged the given amount. Payment status changes from **Payment Authorized** to **Paid in Full**. Payment history will show two transactions for this order, **Authorize** and **Capture**
  ![Order paid in full in the back-office](user/img/system/integrations/cybersource/paid-in-full.png)
  <br/>
* When you click **Cancel**, the payment status changes to **Payment Canceled**. Payment history will show two transactions for this order, **Authorize** and **Cancel**
  ![Payment authorized but order canceled in the back-office](user/img/system/integrations/cybersource/canceled_payment.png)
