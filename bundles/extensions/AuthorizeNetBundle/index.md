<a id="bundle-docs-extensions-authorizenet"></a>

# OroAuthorizeNetBundle

<a href="https://github.com/oroinc/OroAuthorizeNetBundle" target="_blank">OroAuthorizeNetBundle</a> adds the <a href="https://www.authorize.net/" target="_blank">Authorize.Net</a> <a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/IntegrationBundle" target="_blank">integration</a> to OroCommerce applications.

The bundle allows admin users to enable and configure the Authorize.Net payment method for customer orders, which allows customers to pay for orders with credit and debit cards or eChecks using Authorize.Net Payment Gateway.

## Setting Up Connection

For steps on configuring the integration on the AuthorizeNet and Oro sides, please see [Prerequisites for Authorize.Net Integration in the Back-Office](../../../user/back-office/system/integrations/payment-integration/authorizenet/authorizenet-prerequisites.md#user-guide-payment-prerequisites-authorizenet) and [Configure Authorize.Net Integration in the Back-Office](../../../user/back-office/system/integrations/payment-integration/authorizenet/authorizenet-integration.md#user-guide-payment-configuration-payment-method-integration-authorizenet-details).

## eCheck payments

In addition to regular credit card payments, Authorize.Net allows to process <a href="https://www.authorize.net/payments/echeck/" target="_blank">eCheck transactions</a>.

Before enabling the eCheck payment option in the back-office integration settings, make sure that it is enabled for your Authorize.Net merchant account.

Enabling the eCheck option in the integration settings turns on the eCheck payment option for payment rules and allows to manage eCheck payment profiles if <a href="https://www.authorize.net/our-features/secure-customer-data/" target="_blank">CIM</a> is enabled.

eCheck transactions are placed with the “Authorize and Charge” payment action.

See [Configure Authorize.Net Integration in the Back-Office](../../../user/back-office/system/integrations/payment-integration/authorizenet/authorizenet-integration.md#user-guide-payment-configuration-payment-method-integration-authorizenet-details) for details on eCheck configuration.

## Customer Information Management

<a href="https://www.authorize.net/our-features/secure-customer-data/" target="_blank">CIM</a> is also available in the integration settings to simplify the checkout process for registered customers. It allows customers to store and manage their payment profiles (credit cards or eCheck) and pay with a saved profile during checkout.

Sensitive payment data (credit card number, CVV, eCheck account number, etc.) is neither passed nor stored in the application and is securely transferred to Authorize.Net using <a href="https://developer.authorize.net/api/reference/features/acceptjs.html" target="_blank">Accept.js</a>.

For more information on payment profiles, see the [Manage Payment Profiles (Authorize.Net Customer Profiles)](../../../user/storefront/account/cim/index.md#frontstore-guide-cim) topic in the OroCommerce Storefront guide.

## Test Settings

Authorize.Net has a <a href="https://sandbox.authorize.net/" target="_blank">Sandbox test server</a> where you can register a test account and try it for free. For this, please proceed to <a href="https://developer.authorize.net/" target="_blank">Developers site</a> and follow instructions to retrieve the credentials for the Authorize.Net sandbox server (API Login ID, Transaction Key, Client key). Make sure you enable the Test Mode option when creating a test integration.

To test the CIM integration within the sandbox account, make sure the sandbox account is switched to the Live mode.

#### BUSINESS TIP
## Business Tip

Technologies are the driving force for digital transformation in important industries like manufacturing. Learn more about the role of eCommerce in <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">manufacturing digital transformation</a>.

<!-- Frontend -->
