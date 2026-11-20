<a id="bundle-docs-commerce-payment-bundle"></a>

# OroPaymentBundle

OroPaymentBundle introduces the payments framework to the OroCommerce application. It provides the ability to manage payment methods and process payments in both the back-office and storefront.

The bundle enables a developer to implement payment method integrations with third-party payment gateways. For more information on how to create a custom payment method integration, see [Creating a Payment Method Integration](../../../backend/extend-commerce/payment/index.md#dev-extend-commerce-payment-create-payment-method).

OroPaymentBundle makes it possible to configure payment methods via payment rules. Payment rules allow specifying the conditions under which a payment method is available for use. For more information, see [Configuring Payment Methods via Payment Rules](../../../user/back-office/system/payment-rules/index.md#sys-payment-rules).

The bundle introduces the `\Oro\Bundle\PaymentBundle\Entity\PaymentTransaction` entity, which represents a payment transaction. Payment transactions are used to store information about payments processed via payment methods. Based on the payment transactions, the bundle calculates the payment status of the related entity (e.g., an order or an invoice) and stores in the `\Oro\Bundle\PaymentBundle\Entity\PaymentStatus` entity. The payment status indicates whether the related entity is paid, partially paid, or unpaid. For more information, see [Payment Status](payment-status.md#bundle-docs-commerce-payment-status).

OroPaymentBundle provides the framework of merchant-initiated payments. A payment method may store the credentials of the customer in a contract during the checkout to make it possible to charge them later without the customer. For more information, see [Merchant-Initiated Payments](merchant-initiated-payments.md#bundle-docs-commerce-payment-bundle-merchant-initiated-payments).

OroPaymentBundle also provides the operations to manage payments in the back-office:

- **oro_payment_transaction_capture** — captures an authorized payment transaction;
- **oro_payment_transaction_cancel** — cancels an authorized payment transaction;
- **oro_payment_transaction_refund** — refunds a payment transaction.

* [Payment Status](payment-status.md)
* [Merchant-Initiated Payments](merchant-initiated-payments.md)

<!-- Frontend -->
