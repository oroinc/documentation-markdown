<a id="user-guide-payment-payment-providers-overview-payment-term-config"></a>

# Configure Payment Terms in the Back-Office

#### HINT
This section is part of the [Payment Configuration](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment) topic that provides a general understanding of the payment concept in OroCommerce.

In OroCommerce, you can use [payment terms](../../../../../glossary.md#term-Payment-Term) configured per customer to help them use the payment conditions guaranteed by their contract with your company.

Payment term is a set of conditions required for the sale to be completed, e.g. the period that is allowed to a buyer to pay off the amount due. Payment terms may also include cash in advance requirement, cash collection on delivery, a deferred payment period of 10/20/30 days, etc.

**To use payment terms in your OroCommerce storefront:**

1. [Enable Payment Terms Integration]().
2. [Create a Payment Term]() with the conditions you would like to offer your buyers.
3. [Link a Payment Term to a Customer Based on Their Sales Agreement]() (optional).
4. [Create a payment rule](../../../payment-rules/index.md#sys-payment-rules) and add your integration to it to display this method to the customers at checkout.

<a id="sys-integrations-manage-integrations-payment-term"></a>

## Enable Payment Terms Integration

To expose payment terms as a payment method for OroCommerce orders and quotes, enable payment using payment terms:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration**.
3. In the **Basic Information** section, provide the following information:
   ![image](user/img/system/integrations/payment_terms/payment_terms.png)
   * **Type** —  Select *Payment Terms*.
   * **Name** — The payment method name that is shown as an option for payment configuration in the OroCommerce back-office.
   * **Label** — The payment method name/label displayed as a payment option for the buyer in the OroCommerce storefront during the checkout. To translate the label into other languages, click on the <i class="fas fa-language" aria-hidden="true"></i> icon next to the field.

     #### NOTE
     It doesn’t have to include the payment processor name if you want to hide it from the buyers. For example, you can enter ‘Credit Card Payments’ if you have a single payment method configured for processing credit cards.
   * **Short label** — The payment method name/label that is shown in the order details in the OroCommerce back-office and storefront after the order is submitted. To translate the label into other languages, click on the <i class="fas fa-language" aria-hidden="true"></i> icon next to the field.
   * **Status**  — Set the status to **Active** to enable the integration.
   * **Default Owner** — A user who is responsible for this integration and manages it.
4. Click **Save and Close**.

Next, set up a [payment rule](../../../payment-rules/index.md#sys-payment-rules) that enables this payment method for all or some customer orders, create individual payment terms based on the sales agreement with your customers to cover all the agreed payment terms/options, and bind your customers to their respective payment term. You may use only one payment term per customer.

## Create a Payment Term

To create a new payment term:

1. Navigate to **Sales > Payment Terms** in the main menu.
   ![Create a new payment method](user/img/sales/payment_terms/payment_terms_list.png)
2. Click **Create Payment Term**.
   ![Provide payment term name](user/img/sales/payment_terms/PaymenttermsCreate.png)
3. Type in the label that is informative for both the salesperson and the customer buyer, as it will be exposed as one of the payment options for both parties.
4. Click **Save**.

## Link a Payment Term to a Customer Based on Their Sales Agreement

You can bind a customer to a payment term in the customer details:

1. Navigate to **Customers > Customers** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details.
3. Scroll down to the **Additional** section and select one of the existing payment terms (start typing or click (v) to see the options) or create a new one (click **+**, add a new payment term label in the box that opens, and click **Save**).
4. Click **Save**.

The customer is now bound to the selected payment term.

**Related Topics**

* [Payment Configuration Concept Guide](../../../../../concept-guides/payment-configuration/index.md#user-guide-payment)
* [Payments at Checkout (Illustration)](../checkout/index.md#doc-payment-checkout)
* [System Payment Configuration](../../../configuration/commerce/payment/index.md#configuration-guide-commerce-configuration-payment)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
