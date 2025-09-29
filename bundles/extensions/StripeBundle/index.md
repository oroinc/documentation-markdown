<a id="bundle-docs-extensions-stripe"></a>

# OroStripeBundle

#### HINT
The Stripe payment service is available starting from OroCommerce v5.0.9. To check which application version you are running, see the [system information](../../../user/back-office/system/system-information/index.md#system-information).

OroStripeBundle provides Stripe payment service for card payments.

## Configuration

To be able to use Stripe for payments, first configure an [integration in the back-office](../../../user/back-office/system/integrations/payment-integration/stripe/index.md#user-guide-payment-payment-providers-stripe-overview)

## Payment Flow

Current integration implementation is based on the logic described in the <a href="https://stripe.com/docs/payments/accept-a-payment-synchronously" target="_blank">Finalize payments on the server</a> article.
The Stripe API provides a payment process based on Stripe PaymentMethod and Stripe PaymentIntents objects.
Stripe provides a Stripe.js library to handle actions in the storefront. It comes with its own UI elements, managed
by the library itself. Custom js components implemented in this bundle use Stripe library for:

- gathering card information and creating a payment method used for the PaymentIntents confirmation.
- card data validation
- handling the required additional actions (for example, 3D secure authentication)

Currently, Oro Stripe payment integration supports the following actions:

- Authorize
- Capture
- Confirm (custom action)

Oro Stripe integration also supports webhooks events handling, which helps to handle actions
performed from the Stripe Dashboard (cancel, capture, refund). There are only three supported events types:

- **payment_intent.succeeded** – performed when payment is captured successfully
- **payment_intent.canceled** – initiated when authorized payment canceled
- **charge.refunded** – performed when refunded some amount of captured payment

Configure the webhook callback URL in the Stripe Dashboard in the *Developers* section to use this functionality. Use the
*Webhooks* menu item and click **Add Endpoint** to set a URL and select the supported events. The **Endpoint URL** format should be `{base_url}/stripe/handle-events`. Make sure you add events described before in the section “*Select events to listen to*, as this helps reduce request numbers to the Oro application from Stripe service.

## Customizations

Stripe.js provides <a href="https://stripe.com/docs/js/appendix/style" target="_blank">Style object</a> to customize Stripe Payment card elements.
Override block **\_payment_methods_stripe_payment_widget** from **layouts/imports/oro_payment_method_options** to apply
custom styles. See list of available css options in the <a href="https://stripe.com/docs/js/appendix/style" target="_blank">Style object</a>.

To support Stripe events that are not currently supported, create a new EventHandler responsible for the event data
handling logic. Handler should implement the `Oro\Bundle\StripeBundle\EventHandler\StripeEventHandlerInterface` interface.

**Related Articles**

* [Manage Stripe Payment Service in the Back-Office](../../../user/back-office/system/integrations/payment-integration/stripe/index.md#user-guide-payment-payment-providers-stripe-overview)
* [Payment Configuration Concept Guide](../../../user/concept-guides/payment-configuration/index.md#user-guide-payment)

<!-- Frontend -->
