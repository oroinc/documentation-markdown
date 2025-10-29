<a id="bundle-docs-extensions-stripe-payment-bundle-invoice-payments"></a>

# Invoice Payments

Stripe Payment Element payment method is registered as a payment method for the invoice payments.

## Implementation Details

`\Oro\Bundle\StripePaymentBundle\PaymentMethod\StripePaymentElement\StripePaymentElementMethod` payment method implements the `\Oro\Bundle\PaymentBundle\Method\PaymentMethodGroupAwareInterface` interface. The applicable payment method groups are defined in the `oro_stripe_payment.payment_method.stripe_payment_element.payment_method_groups` service container parameter that contains the oro_invoice_payment_storefront payment method group. Therefore, the Stripe Payment Element payment methods will be returned by the `oro_invoice_payment.payment_method.composite_provider` service.

<!-- Frontend -->
