<a id="bundle-docs-extensions-paypalexpress"></a>

# OroPayPalExpressBundle

This extension provides an implementation of PayPal Express payment integration that can be used in European countries (please check the PayPal website in your country to confirm the availability of PayPal Express in your country).

## Overview

The bundle provides integration between OroCommerce and PayPal through <a href="https://developer.paypal.com/api/rest/" target="_blank">PayPal REST API</a>. The main difference between PayPal payment methods defined in OroPayPalBundle and OroPayPalExpressBundle is how they communicate with PayPal. While OroPayPalBundle uses <a href="https://developer.paypal.com/api/nvp-soap/payflow/payflow-gateway/" target="_blank">Payflow Gateway</a>, OroPayPalExpressBundle uses <a href="https://developer.paypal.com/api/rest/" target="_blank">PayPal REST API</a>. Both ways have their restrictions.

Under the hood, this bundle is using <a href="https://github.com/paypal/PayPal-PHP-SDK" target="_blank">PayPal PHP SDK</a> to communicate with <a href="https://developer.paypal.com/api/rest/" target="_blank">PayPal REST API</a>. See more in <a href="http://paypal.github.io/PayPal-PHP-SDK/sample/" target="_blank">REST API Samples</a> documentation on the PayPal side.

## Structure

The following diagram illustrates the structure of PaypalExpressBundle, with the arrows placed in the direction of dependency:

![The diagram illustrating the structure of paypalbundle](img/bundles/PaypalExpressBundle/structure.png)

The example Anti-Corruption Layer depends on PayPal SDK.

## Installation

This extension can be added to an existing installation of OroCommerce:

Use composer to add the package code:

```bash
composer require oro/commerce-paypal-express
```

Perform the installation:

```bash
php bin/console oro:platform:update --env=prod
```

## Responsibilities and Extension Points

### Anti-Corruption Layer

Anti-Corruption Layer is responsible for the communication with <a href="https://developer.paypal.com/api/rest/" target="_blank">PayPal REST API</a> through <a href="https://github.com/paypal/PayPal-PHP-SDK" target="_blank">PayPal PHP SDK</a> and the conversion of OroPayPalExpress DTO to PayPal SDK domain data objects. Keep in mind that reverse translation is not implemented.

The anti-corruption layer includes a couple of DTO objects, as well as:

* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Transport/PayPalExpressTransport.php" target="_blank">PayPalExpressTransport</a>
* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Transport/PayPalClient.php" target="_blank">PayPalClient</a>
* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Transport/PayPalSDKObjectTranslator.php" target="_blank">PayPalSDKObjectTranslator</a>

The primary goal of this layer is to hide the actual way of communication with <a href="https://developer.paypal.com/api/rest/" target="_blank">PayPal REST API</a>. It also helps avoid backward-incompatible changes if PayPal changes its REST API in the future. It is also helpful for implementing the reverse side integration with PayPal.

#### PayPalExpressTransport

PayPalExpressTransport is responsible for the interaction with <a href="https://github.com/oroinc/paypal-express/blob/4.2/Transport/PayPalClient.php" target="_blank">PayPalClient</a> and <a href="https://github.com/oroinc/paypal-express/blob/4.2/Transport/PayPalSDKObjectTranslator.php" target="_blank">PayPalSDKObjectTranslator</a> and hiding and wrapping PayPal SDK exceptions in the client code of OroCommerce.

#### PayPalClient

PayPalClient is responsible for interacting with <a href="https://developer.paypal.com/api/rest/" target="_blank">PayPal REST API</a> through <a href="https://github.com/paypal/PayPal-PHP-SDK" target="_blank">PayPal PHP SDK</a>.

Any operation that calls PayPal REST API resource, as a result, should be added to the client.

#### PayPalSDKObjectTranslator

PayPalSDKObjectTranslator is responsible for converting anti-corruption layer DTO’s to the <a href="https://github.com/paypal/PayPal-PHP-SDK" target="_blank">PayPal PHP SDK</a> domain data objects.

### Payment Actions Layer

The payment actions layer is responsible for handling payment actions.

The layer includes:

* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/PaymentActionRegistry.php" target="_blank">PaymentActionRegistry</a>
* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/Complete/CompletePaymentActionRegistry.php" target="_blank">CompletePaymentActionRegistry</a>
* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/PaymentActionExecutor.php" target="_blank">PaymentActionExecutor</a>
* <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/CompleteVirtualAction.php" target="_blank">CompleteVirtualAction</a> in addition to supported actions and complete actions implementing <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/PaymentActionInterface.php" target="_blank">PaymentActionInterface</a>

#### PaymentActionExecutor

PaymentActionExecutor is responsible for executing a payment action. It uses <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/Complete/CompletePaymentActionRegistry.php" target="_blank">CompletePaymentActionRegistry</a> to get an appropriate payment action.

#### PaymentActionRegistry

PaymentActionRegistry is responsible for providing payment action by name. It can be used as an extension point to add custom payment action.
A possible payment action could be found in the constants of `\Oro\Bundle\PaymentBundle\Method\PaymentMethodInterface`.
Actions that are not presented in the interface can be added, but the default workflows will not support them.

#### CompleteVirtualAction

CompleteVirtualAction is responsible for receiving a complete payment action by name from <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/Complete/CompletePaymentActionRegistry.php" target="_blank">CompletePaymentActionRegistry</a> and delegating the call to the actual complete payment action.

#### CompletePaymentActionRegistry

CompletePaymentActionRegistry is responsible for providing a complete payment action by name.

A complete payment action is configured in the PayPal Express method integration settings in a field labeled “Payment Action”.

By default, two possible complete actions are available:

* Authorize (<a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/Complete/AuthorizeAndCaptureAction.php" target="_blank">AuthorizeAndCaptureAction</a>)
* Authorize and capture (<a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/Complete/AuthorizeOnCompleteAction.php" target="_blank">AuthorizeOnCompleteAction</a>)

To register a new complete payment action, create a new service with tag oro_paypal_express.complete_payment_action (class of the service must implement <a href="https://github.com/oroinc/paypal-express/blob/4.2/Method/PaymentAction/PaymentActionInterface.php" target="_blank">PaymentActionInterface</a>).

After a new service is registered, it will be available in the integration settings of the PayPal Express payment method.

<!-- Frontend -->
