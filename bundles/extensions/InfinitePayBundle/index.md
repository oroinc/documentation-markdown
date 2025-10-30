<a id="bundle-docs-extensions-infinitepay"></a>

# OroInfinitePayBundle

<a href="https://github.com/oroinc/OroInfinitePayBundle" target="_blank">OroInfinitePayBundle</a> adds <a href="https://www.infinitepay.de/" target="_blank">Infinite Pay</a> <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/IntegrationBundle" target="_blank">integration</a> into Oro applications.

The bundle helps admin users to enable and configure Infinite Pay <a href="https://github.com/oroinc/orocommerce/tree/master/src/Oro/Bundle/PaymentBundle" target="_blank">payment method</a> for customer orders, and therefore allows customers to pay for orders with Invoices attested by Infinite Pay service.

For prerequisites and steps on configuring the integration, please see [user configuration documentation](../../../user/back-office/system/integrations/payment-integration/infinitepay/index.md#user-guide-payment-payment-providers-overview-infinitepay).

**Checkout**

For a successful payment request to InfinitePay the customer must also provide additional information on the payment step.
The following fields will be shown on the payment step if InfinitePay was selected as payment provider:

- company
- email address
- legal form (i.e., Freelancer, GbR)

**Payment Finalization**

To set an invoice as paid, there are two approaches. The first one is auto-detection by InfinitePay. This requires the shop owner to book this option with InfinitePay and making the company bank account accessible to InfinityPay. The second option is to inform InfinitePay when the money for an order (respective invoice) was received. This is done by triggering **Apply Transaction** to InfinityPay referencing the order id.

#### BUSINESS TIP
# Business Tip

Considering <a href="https://oroinc.com/b2b-ecommerce/what-is-b2b-ecommerce/" target="_blank">business to business eCommerce</a> for your company? Our comprehensive guide packed with relevant stats and examples will help you decide.

**Related Documentation**

* [Prerequisites for InfinitePay Integration](../../../user/back-office/system/integrations/payment-integration/infinitepay/infinitepay-prerequisites.md#user-guide-payment-prerequisites-infinitepay)
* [InfinitePay Integration](../../../user/back-office/system/integrations/payment-integration/infinitepay/infinitepay-integration.md#sys-integrations-manage-integrations-infinitepay)
* [Payment Configuration Concept Guide](../../../user/concept-guides/administration/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../../../user/back-office/system/integrations/payment-integration/checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../user/back-office/system/configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)

<!-- Frontend -->
