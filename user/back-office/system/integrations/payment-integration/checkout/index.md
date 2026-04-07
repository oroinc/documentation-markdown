<a id="doc-payment-checkout"></a>

# View Payments at Checkout

After the integration is complete, the customer user may select one of the payment methods that are shown after the connectivity check and payment rules evaluation.

## PayPal Payflow Gateway with No CVV Required

![image](user/img/system/integrations/checkout/checkout_payments_pro_no_cvv.png)

#### NOTE
If the order total is zero, the PayPal Payment method will be hidden and unavailable for selection.

## PayPal Payments Pro with Require CVV Entry Enabled

![image](user/img/system/integrations/checkout/checkout_payments_pro_cvv.png)

#### NOTE
If the order total is zero, the PayPal Payment method will be hidden and unavailable for selection.

## PayPal Payments Pro Express Checkout

<!-- Express Checkout is part of the payment method name (PayPal Payments Pro Express Checkout). Unintentionally, it is forced to duplicate the parent header. Other payment methods do not have to follow this style. -->![image](user/img/system/integrations/checkout/checkout_payments_pro_express.png)

#### NOTE
If the order total is zero, the PayPal Payment method will be hidden and unavailable for selection.

## PayPal Payments Express Checkout

![image](user/img/system/integrations/checkout/checkout_paypal_express.png)

#### NOTE
Before you can use PayPal Express in OroCommerce, [install](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer) the <a href="https://packagist.oroinc.com/?#oro/paypal-express" target="_blank">Oro PayPal Express Integration</a> package.

#### NOTE
If the order total is zero, the PayPal Payment method will be hidden and unavailable for selection.

## Authorize.Net

#### WARNING
For security reason, the Authorize.Net payment option appears only when a buyer access your OroCommerce site via the https protocol.

![image](user/img/system/integrations/checkout/checkout_authorizenet.png)
