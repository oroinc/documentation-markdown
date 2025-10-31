<a id="sys-integrations-manage-integrations-infinitepay"></a>

# Configure InfinitePay Payment Method Integration in the Back-Office

<!-- begin -->

This section describes the steps that are necessary to expose InfinitePay service as a payment method for OroCommerce orders and quotes.

#### NOTE
Before you begin, see [InfinitePay Services overview](index.md#user-guide-payment-payment-providers-overview-infinitepay) and learn about [InfinitePay integration prerequisites](infinitepay-prerequisites.md#user-guide-payment-prerequisites-infinitepay) - the preparation steps that should be performed on the InfinitePay service side.

To enable payments using InfinitePay:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu. The **Manage Integrations** page opens.
2. Click **Create Integration**.
3. In the **Basic Information** section, provide the following details:
   * **Type** — Select *Infinite Pay* for **Type**
   * **Name** — The payment method name that is shown as an option for payment configuration in the OroCommerce back-office.
   * **Label** — The payment method name/label displayed as a payment option for the buyer in the OroCommerce storefront during the checkout. To translate the label into other languages, click on the <i class="fas fa-language" aria-hidden="true"></i> icon next to the field.

     #### NOTE
     It doesn’t have to include the payment processor name if you want to hide it from the buyers. For example, you can enter ‘Credit Card Payments’ if you have a single payment method configured for processing credit cards.
   * **Short label** — The payment method name/label that is shown in the order details in the OroCommerce back-office and storefront after the order is submitted. To translate the label into other languages, click on the <i class="fas fa-language" aria-hidden="true"></i> icon next to the field.
   * **Client Reference** — The unique identifier of your InfinitePay account.
   * **Username** — Login for your InfinitePay account that is used to authenticate OroCommerce calls to the InfinitePay API.
   * **Password** — Password that is used to authenticate OroCommerce calls to the InfinitePay API.
   * **Secret (For Security Code)** — This is a pre-shared key used to cipher payment information.
   * **Auto-Capture** — When enabled, the amount for payment is blocked on the buyer’s InfinitePay account (limit) immediately after the order is submitted. See more information about the [InfinitePay guarantee actions](index.md#user-guide-payment-configuration-payment-method-integration-infinitepay-payment-actions) (reserve, capture, and activate).
   * **Auto-Activation** — When enabled, the payment guarantee is activated upon the order submission. The successful activation means that InfinitePay approves the payment, provides a guarantee for the financial risks related to the future payment. See more information about the [InfinitePay guarantee actions](index.md#user-guide-payment-configuration-payment-method-integration-infinitepay-payment-actions) (reserve, capture, and activate).
   * **Test mode** — An option that enables calling PayPal API in the test mode.
   * **Debug Mode** — When enabled, InfinitePay transactions include more detailed information in the response. This mode may be helpful when troubleshooting payment-related issues.
   * **Invoice Due Period** — The unified invoice due period that is applied to the invoices created in InfinitePay. It is taken into account to estimate the payment due date.
   * **Shipping Duration (In Days)** — the unified timeframe reserved for shipping. It is taken into account to estimate the payment due date.
   * **Status**  — Set the status to **Active** to enable the integration.
   * **Default Owner** — A user who is responsible for this integration and manages it.
4. Click **Save and Close**.

Next, set up a payment rule that enables this payment method for all or some customer orders via the [Payment Rules Configuration](../../../payment-rules/index.md#sys-payment-rules) page.

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
