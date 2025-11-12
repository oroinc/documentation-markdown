<a id="pre-built-integrations-payment-oropay"></a>

# Integration with OroPay Payment Service

#### HINT
Please <a href="https://oroinc.com/contact-us/" target="_blank">contact our support team</a> for more information on available integration options. You can also visit our <a href="https://extensions.oroinc.com/" target="_blank">extensions store</a> to explore other integrations and extensions.

[OroPay](../../../back-office/system/integrations/payment-integration/oropay/index.md#user-guide-payment-oropay) is a payment solution integrated into OroCommerce, designed specifically for B2B transactions. Unlike typical consumer-focused payment tools, OroPay addresses the unique needs of B2B organizations, such as large orders, recurring invoices, and complex account structures. It combines eCommerce, ERP, and payment workflows into one natural process.

OroPay is developed with Global Payments, a top company in financial technology, and offers strong reliability and compliance features. It is built directly into the OroCommerce platform, meaning it doesn’t work as a separate product. This integration removes the need for external portals or third-party services, which helps lower operational costs. As a result, businesses gain a single, trustworthy source for their financial data, making operations easier and data more accurate.

#### IMPORTANT
Before using OroPay, please contact the [OroCloud team](../../../../cloud/support.md#cloud-support) to have OroPay provisioned in your cloud environment.

![View the OroPay payment method under the Invoices section](user/img/system/integrations/oropay/oropay-invoices.png)

## Key OroPay Features

Here is an overview of the key OroPay features:

* **Payment Methods** — Supports credit card and ACH (bank transfer) payments.
* **Checkout and Invoices** — Enables buyers to pay either during the checkout process or directly from the storefront’s Invoices menu.
* **Unified Workflow** — Integrates commerce, ERP, and financial data into a single workflow, minimizing the need for duplicate systems or manual reconciliation.
* **Efficiency Gains** — Automates invoice handling and payment reconciliation, helping finance teams reduce errors and focus on higher-value tasks.

## Data Exchanged

When a payment is initiated, OroPay exchanges transactional and contextual information with multiple types of data with Global Payments to provide the smooth flow of payment information and enable secure and seamless transactions.

**Transaction Amount** — The total amount of the payment.

**Currency** — The currency in which the transaction is made.

**Customer Information** — Information about the customer making the purchase, such as name, phone number, and shipping address.

**Order Information:** Details about the products or services being purchased, including item names, quantities, prices, and any applicable taxes or discounts.

It is important to note that the exact data exchanged and the level of integration can vary depending on the configuration settings and the customization implemented within OroCommerce.

## Data Security

Security is a core component of OroPay’s architecture. OroCommerce uses Global Payments’ infrastructure to provide:

* **Real-Time Fraud Detection** — Continuous monitoring of transactions to identify and prevent suspicious activity.
* **Data Tokenization** — Sensitive payment data is replaced with secure tokens, minimizing exposure of cardholder or bank details.
* **Regulatory Compliance** — Full adherence to PCI DSS standards, SOC 1 and SOC 2 reporting, Strong Customer Authentication (SCA), and 3D Secure 2.0 protocols.

This layered security approach protects both sellers and customers, ensuring that financial data is processed and stored in line with industry best practices.

**Related Articles**

* [Payment Configuration Concept Guide](../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment)
* [Manage OroPay Payment Service in the Back-Office](../../../back-office/system/integrations/payment-integration/oropay/index.md#user-guide-payment-oropay)
* [Payment Actions (Authorize/Authorize and Charge)](../../../back-office/system/integrations/payment-integration/paypal-services/paypal-payment-actions.md#user-guide-payment-configuration-payment-method-integration-payment-actions)
* [Payments at Checkout (Illustration)](../../../back-office/system/integrations/payment-integration/checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../back-office/system/configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
