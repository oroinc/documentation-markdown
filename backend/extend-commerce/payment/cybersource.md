# OroCommerce Integration with CyberSource

OroCyberSourceBundle adds the <a href="https://www.cybersource.com" target="_blank">CyberSource</a> integration to OroCommerce applications.

The bundle allows admin users to enable and configure the CyberSource payment method for customer orders, which allows customers to pay for orders with credit and debit cards using CyberSource Payment Gateway.

## Installation

Add oro/commerce-cybersource package to your installation:

```none
composer require "oro/commerce-cybersource"
```

In case the package is added to an already installed application, then [platform update](../../setup/upgrade-to-new-version.md#upgrade-application) is required.

## Configuration

For the detailed instructions on the integration configuration, see the [user guide](../../../user/back-office/system/integrations/payment-integration/cybersource/index.md#user-guide-payment-payment-providers-cybersource).

## Overview

Integration Methods:

* **Hosted checkout** - When a customer in the storefront creates an order, they are redirected to a CyberSource payment form page to provide card authorization details. Any payment type supported by CyberSource is allowed.
* **Checkout API** - Payment is processed via an REST API call. Only debit and credit cards are allowed.

## Hosted Checkout Method Lifecycle

1. After a customer clicks *Submit Order* in the storefront, the paymentTransaction is processed in <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/Method/PaymentAction/CheckoutApi/PurchasePaymentAction.php" target="_blank">PurchasePaymentAction</a> and JS component <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/Resources/public/js/app/components/hosted-checkout/order-review-component.js" target="_blank">OrderReviewComponent</a> redirects customer to the CyberSource side.
2. <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/EventListener/Callback/CyberSourceCheckoutListener.php" target="_blank">CyberSourceCheckoutListener</a> processes the success or error response from the CyberSource side.

## Checkout API Method Lifecycle

1. When a customer inputs credit card data, <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/Resources/public/js/app/components/checkout-api/credit-card-component.js" target="_blank">CreditCardComponent</a> generates token value using <a href="https://developer.cybersource.com/api/soap-developer-guides/dita-flex/SAFlexibleToken/FlexMicroform.html" target="_blank">Flex Microform</a> and saves it in the payment transaction as additionalData value.
2. After a click on the *Submit Order* button, the paymentTransaction is processed in <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/Method/PaymentAction/CheckoutApi/PurchasePaymentAction.php" target="_blank">PurchasePaymentAction</a>. It uses token from the previous step for processing payment transaction.

## Payment Transaction Actions

The CyberSource payment method supports **Capture** and **Cancel** actions. Both of them can be performed for payment transactions of the **Authorize** type and - only in case there no successful transactions - of the **Capture** or **Cancel** type.

* Business logic for **Capture** action is implemented in <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/Method/PaymentAction/CapturePaymentAction.php" target="_blank">CapturePaymentAction</a>
* Business logic for **Cancel** action is implemented in <a href="https://github.com/oroinc/cybersource/blob/4.2-beta/src/Oro/Bundle/CyberSourceBundle/Method/PaymentAction/CancelPaymentAction.php" target="_blank">CancelPaymentAction</a>

#### BUSINESS TIP
## Business Tip

Digital technologies help manufacturing brands remain competitive. Find out how eCommerce and <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a> can propel your company’s growth.

<!-- Frontend -->
