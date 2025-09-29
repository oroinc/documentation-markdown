<a id="user-guide-payment-check-money-order"></a>

# Configure Check/Money Order Service Integration in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment) topic that provides the general understanding of the payment concept in OroCommerce.

Money order is a paper document similar to check that is prepaid for certain amount. It does not require a check account and may be issued by banks, post, money transfer companies, etc.

To create a check/money order:

1. Configure [Check/Money Order Integration](#sys-integrations-manage-integrations-check-money-order) under **System > Integrations > Manage Integrations** to enable check/money order as a payment method in the system.
2. Create a [payment rule](../../../payment-rules/index.md#sys-payment-rules) under **System > Payment Rules** and add your integration to it to display this method to the customers at the checkout.

<a id="sys-integrations-manage-integrations-check-money-order"></a>

## Enable Check/Money Order Payment Integration

<!-- begin -->

To enable check/money order payments, complete the following steps:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. On the **Manage Integrations** page, click **Create Integration**.

   The following page is displayed:
   ![image](user/img/system/integrations/check_money_order/check_money_order.png)
3. In the **Basic Integration Details** section, provide the following details:
   * **Type** – -Select *Check/Money Order* for **Type**.
   * **Name** — The payment method name that is shown as an option for payment configuration in the OroCommerce back-office.
   * **Label** — The payment method name/label displayed as a payment option for the buyer in the OroCommerce storefront during the checkout. To translate the label into other languages, click on the <i class="fas fa-language" aria-hidden="true"></i> icon next to the field.

     #### NOTE
     It doesn’t have to include the payment processor name if you want to hide it from the buyers. For example, you can enter ‘Credit Card Payments’ if you have a single payment method configured for processing credit cards.
   * **Short label** — The payment method name/label that is shown in the order details in the OroCommerce back-office and storefront after the order is submitted. To translate the label into other languages, click on the <i class="fas fa-language" aria-hidden="true"></i> icon next to the field.
   * **Pay To** — Provide the name of the company or a person to file the payment to.
   * **Send To** — Provide directions and the address to send the check or money order to.

     This information is shared with the customer together with other payment instructions at checkout.
   * **Status** — Set the status to *Active* to enable the integration.
4. Click **Save and Close**.

Next, set up a payment rule that enables this payment method for all or some customer orders via the [Payment Rules Configuration](../../../payment-rules/index.md#sys-payment-rules) page.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->

**Related Topics**

* [Payment Configuration Concept Guide](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)
