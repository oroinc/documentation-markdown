<a id="user-guide-payment-payment-providers-overview-authorizenet"></a>

# Manage Authorize.Net Payments Services in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment) topic that provides the general understanding of the payment concept in OroCommerce.

#### HINT
The feature requires extension, so visit Oro Extensions Store to download the <a href="https://marketplace.oroinc.com/orocommerce/extension/orocommerce-authorize.net-integration/" target="_blank">Authorize.Net extension</a> and then use the composer to [install the extension to your application](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

Authorize.Net is one of the world’s most popular payment gateways. It provides services for businesses based in the United States, Canada, United Kingdom, Europe, and Australia. It ensures secure and reliable money transactions and offers a wide range of additional services.

Integration of OroCommerce with Authorize.Net enables you to accept credit and debit cards on your OroCommerce website.

While your business must be based in one of the aforementioned countries, you can accept payments from the buyers worldwide.

#### IMPORTANT
Note that to accept card payments, business must have a *merchant account*. This is a special bank account to which payments are transferred as soon as they are received from buyers. In next step, money is transferred from the merchant account to your regular bank account, from which you can withdraw it. You can acquire a merchant account on your own, or obtain it from Authorize.Net.

To configure payment integration with Authorize.Net services:

1. Learn the [Prerequisites for Authorize.Net Integration](authorizenet-prerequisites.md#user-guide-payment-prerequisites-authorizenet) that will help configure the integration properly and retrieve corresponding credentials.
2. Configure [Authorize.Net Integration](authorizenet-integration.md#user-guide-payment-configuration-payment-method-integration-authorizenet-details) under **System > Integrations > Manage Integrations**.
3. Create a [payment rule](../../../payment-rules/index.md#sys-payment-rules) under **System > Payment Rules** and add your integration to it to display this method to the customers at the checkout.

## eCheck.Net Integration

In addition to accepting various cards, Authorize.Net offers eCheck.Net service to process e-check payments. When setting up your Authorize.Net integration in the OroCommerce back-office, you can configure your OroCommerce application to expand transaction options at the checkout to e-checks. For setup instructions, proceed to the eCheck section of the [integration with Authorize.Net](authorizenet-integration.md#user-guide-payment-configuration-payment-method-integration-authorizenet-details) topic.

#### NOTE
For more information on e-check payments, see the <a href="https://www.authorize.net/content/dam/authorize/documents/echecknetcomplianceguide.pdf" target="_blank">official education guide for merchants</a>.

## Customer Payment Profiles (CIM) Integration

OroCommerce supports an integration with the Customer Information Manager (CIM) service offered by Authorize.Net. With its help, customer users can save and manage up to 10 payment profiles for future orders in their [OroCommerce storefront account](../../../../../storefront/account/cim/index.md#frontstore-guide-cim). All payment profiles are synchronized with Authorize.Net as soon as they are added or modified on the OroCommerce side.

For setup instructions, proceed to the CIM section of the [integration with Authorize.Net](authorizenet-integration.md#user-guide-payment-configuration-payment-method-integration-authorizenet-details) topic.

#### NOTE
For more information on payment profiles, see the [Manage Payment Profiles (Authorize.Net Customer Profiles)](../../../../../storefront/account/cim/index.md#frontstore-guide-cim) topic in the OroCommerce Storefront guide.

## Security

OroCommerce server never stores buyer’s sensitive payment information (complete card number, expiration date, and cvv code), this information is directly sent to Authorize.Net.

As Authorize.Net servers are PCI DSS complaint, this ensures that you provide to your buyers the security of payments that meets requirements of the controlling organizations.

OroCommerce uses <a href="https://developer.authorize.net/api/reference/features/acceptjs.html" target="_blank">Authorize.Net Accept.js</a> library to process buyer’s sensitive information in their web browser.

Transaction response from the payment gateway also does not contain sensitive information about a buyer’s card. It serves as an identifier of the initial authorization that is solely handled by the payment gateway.

**Related Topics**

* [Payment Configuration Concept Guide](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
