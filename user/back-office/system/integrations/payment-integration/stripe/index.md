<a id="user-guide-payment-payment-providers-stripe-overview"></a>

<a id="user-guide-payment-payment-providers-stripe-element"></a>

# Configure Stripe Payment Element Integration in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment) topic that provides a general understanding of the payment concept in OroCommerce.

Stripe is a payment service provider that helps accept online payments from customers in the OroCommerce storefront. The Stripe Payment Element integration allows customers to pay both invoices and orders directly at checkout, offering a wide range of payment options in a single, unified UI. This includes credit and debit cards, local payment methods in international markets, payment wallets, and buy-now-pay-later options. The integration also supports order splitting, enabling you to capture, cancel, or refund (fully or partially) payments for each sub-order separately, while providing tools to detect potential fraudulent activity and prevent fraudulent orders.

#### NOTE
See a short demo on <a href="https://www.youtube.com/watch?v=CUjmniejCQU" target="_blank">how to configure integration with Stripe</a> or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/CUjmniejCQU?si=xuUwGKosDUQbsgRZ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

#### NOTE
Stripe Integration comes as a separate OroCommerce package and requires [installation](../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer) of the <a href="https://packagist.oroinc.com/#oro/commerce-stripe" target="_blank">Stripe Integration</a> package.

To start using Stripe Payment Element with the OroCommerce application:

1. Register with <a href="https://stripe.com/" target="_blank">Stripe</a> to receive the test credentials.
   ![Test credentials under the Stripe account](user/img/system/integrations/stripe/stripe-account-test.png)
2. To get the live credentials and start accepting payments, <a href="https://dashboard.stripe.com/account/onboarding/business-structure" target="_blank">add your business details</a> to view live keys.
3. In the main menu of the OroCommerce back-office, navigate to **System > Integrations > Manage Integrations**.
4. Click **Create Integration** on the top right.
5. Provide the following information in the form:
   ![Create an integration with Stripe Payment Element in the back-office](user/img/system/config_commerce/sales/stripe-integration-element.png)
   * **Type** - Select *Stripe Payment Element* from the drop-down list.
   * **Name** - Provide the payment method name that is shown as an option for payment configuration in the OroCommerce back-office.
   * **API Public Key** - An identifier that helps authenticate your account. It refers to **Publishable key** on the Stripe side. You must use separate keys for the test and production environments.
   * **API Secret Key** - A pre-shared key used to cipher payment information. It refers to **Secret key** on the Stripe side. You must use separate keys for the test and production environments.
   * **Payment Method Name** - The name for the payment method in back-office, e.g., *Stripe Payment Element*.
   * **Payment Method Label** - The label for the payment method in storefront, e.g., *Stripe Payment*.
   * **Payment Method Short Label** - The short variant of the label for payment method in storefront, e.g., *Stripe*.
   * **Create Webhook Endpoint Automatically** - If enabled, the system automatically creates and configures a Stripe webhook endpoint. This ensures real-time payment events (e.g., successful charges, refunds, or failures) are sent to your application. If you choose to create webhook manually, please provide [Webhook Signing Secret](#stripe-integration-webhook-signing-secret).

     <a id="stripe-integration-webhook-signing-secret"></a>

     #### HINT
     To obtain the Signing secret:
     1. Navigate to **Developers > Webhooks** in the Stripe dashboard and click **Add an endpoint**. Endpoint is a unique URL of your Oro application that is created to receive and process data from Stripe in real-time. URL format should be: `https://my_website_domain.com/stripe/handle-events`. You can use one endpoint to handle several different event types at once, or set up individual endpoints for specific events.

     ![3 steps that instruct how to add a webhook endpoint](user/img/system/integrations/stripe/creating-webhooks-steps.png)
     1. Provide the endpoint URL and select the three events to listen to, **charge.refunded**, **payment_intent.canceled**, and **payment_intent.succeeded**. Keep in mind that Oro supports only these three events. Click **Add events**.

     ![Providing an endpoint and three events that Oro supports](user/img/system/integrations/stripe/add-endpoint.png)
     1. Click **Add endpoint** and copy the generated **Signing secret** to your Stripe integration creation field.

     ![Highlighting the signing secret in the Stripe dashboard](user/img/system/integrations/stripe/signing-secret.png)
   * **Payment Actions for Supported Methods** — Select one of the options for credit cards:
     - *Manual (Authorize)* — The payment gateway checks with the cardholder’s issuing bank that the submitted card is valid and that there are sufficient funds to cover the transaction. The required amount is placed on hold on the card **for 7 days** but not yet charged. When you click **Capture** in the order details (Sales > Orders), the customer is charged the given amount. Payment status changes from **Payment Authorized** to **Paid in Full**. If you do not capture the funds within 7 days, the funds are returned to the customer, and the payment status changes to **Canceled**.
     - *Automatic (Capture)* — The payment gateway checks the card with the cardholder’s issuing bank and, if everything is OK, initiates a money transfer from the card to your account. The customer is charged the given amount in full automatically.
   * **User Monitoring** - Select the option to enable Stripe to fight fraud by detecting suspicious behavior. When enabled, the Stripe.js script is loaded on all storefront pages to provide real-time fraud protection.
   * **Status** - Select whether the integration is active or inactive.
   * **Default Owner** - A user responsible for this integration and its management.

#### NOTE
In the **Synchronization Settings** section, select the **Log Warnings** checkbox if you want all synchronization errors to be written into the application log.

1. Click **Save and Close**

Once the integration is saved, you can connect it as a payment method in the [configuration settings for Invoices](../../../configuration/commerce/sales/global-invoices.md#configuration-guide-commerce-configuration-sales-invoices) or create [payment rules](../../../payment-rules/index.md#sys-payment-rules) to enable it for order payments in the storefront checkout.

## Connect Stripe as Payment Method for Invoice Payments

Stripe Payment Element can be used to pay invoices in the OroCommerce storefront. To set it up, first create a Stripe Payment Element integration under **System > Integrations > Manage Integrations**, as described above. Then, add this integration as a **Payment Method** in the Invoices configuration settings under **System > Commerce > Sales > Invoices** at the level you want it to be available ([global](../../../configuration/commerce/sales/global-invoices.md#configuration-guide-commerce-configuration-sales-invoices), [per organization](../../../user-management/organizations/org-configuration/commerce/sales/organization-invoices.md#user-guide-system-configuration-commerce-sales-invoices-org), or [per website](../../../websites/web-configuration/commerce/sales/website-invoices.md#user-guide-system-configuration-commerce-sales-invoices-per-website)).

![Illustration of the system configuration settings where you can connect the Stripe payment element to the Invoices functionality](user/img/system/integrations/stripe/connect-stripe-to-invoices.png)

Once configured, customers will see Stripe as a payment option when paying invoices.

## Connect Stripe as Payment Method for Storefront Checkout

Once the payment method is added to a [payment rule](../../../payment-rules/index.md#sys-payment-rules), it becomes available at checkout in the OroCommerce storefront. When a customer picks Stripe Payment Element, a modal pops up with the Stripe widget after the final step of the checkout, showing the most relevant payment options—credit and debit cards, wallets, local methods, and even buy-now-pay-later—based on their location, currency, and order total. When they click **Pay Order**, the payment goes through securely, with 3DS and SCA handled automatically.

![Stripe Payment Element modal at checkout, showing relevant payment options and the Pay Order button](user/img/system/integrations/stripe/stripe-payment-method-checkout.png)

## Sub-Order Checkout with Stripe Payment Element

If the [order split](../../../configuration/commerce/sales/global-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping) is enabled for the application, then each sub-order is processed separately by Stripe Payment Element.

![A sample checkout with the order split to two sub-orders](user/img/system/integrations/stripe/sub-order-checkout.png)

Once submitted, the system splits the order to the respective sub-orders, assigning them the corresponding reference codes. The codes are used to identify the order on the Stripe side. You can find the details on the primary or sub-order details page, under the **Payments** section.

> ![Highlighting reference codes for both primary order and its sub-orders](user/img/system/integrations/stripe/sub-order-reference-codes.png)

To **capture** an authorized payment:

1. From the primary order details page — Select the sub-order tab under the **Sub-Orders Payment History** menu and click <i class="far fa-credit-card" aria-hidden="true"></i>.
2. From the sub-order details page — Click <i class="far fa-credit-card" aria-hidden="true"></i> at the end of the row under the **Payments** section.

To **cancel** an authorized payment:

1. From the primary order details page — Select the sub-order tab under the **Sub-Orders Payment History** menu and click **X**.
2. From the sub-order details page — Click **X** at the end of the row under the **Payments** section.

To **refund** (partially or fully) any successful payment:

1. Find the payment that you want to refund.
2. Click <i class="fa fa-share fa-lg" aria-hidden="true"></i> at the end of the row to open the refund dialog.
3. By default, you’ll issue a full refund. For a partial refund, enter a different refund amount.
4. Provide an internal note with the reason for the refund under the **Notes** section.
5. Select another refund reason from the dropdown. It will be recorded on the Stripe side.
6. Click **Yes. Refund Payment**.

![Illustrating the refund flow in steps](user/img/system/integrations/stripe/payment-refund-flow.png)

You can issue more than one refund, but you cannot refund a total greater than the original charge amount.

**Related Topics**

* [Payment Configuration Concept Guide](../../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
* [Invoices](../../../../sales/invoices/index.md#user-guide-sales-invoices)
* [Invoice Configuration Settings](../../../configuration/commerce/sales/global-invoices.md#configuration-guide-commerce-configuration-sales-invoices)
* [Invoices in the Storefront](../../../../../storefront/account/invoices/index.md#frontstore-guide-invoices)

<!-- Frontend -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
