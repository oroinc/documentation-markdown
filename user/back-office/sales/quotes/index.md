<a id="user-guide-sales-quotes"></a>

# Manage Quotes in the Back-Office

#### HINT
This section is part of the [RFQ and Quote Management](../../../concept-guides/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides the general understanding of the RFQ and quote concepts in OroCommerce.

A [quote](../../../glossary.md#term-Quote) is used to negotiate with the customer (e.g. offer better price, more convenient quantities and additional services). A quote may be created in response to a customer request for quote, or as a result of the direct communication with the customer.  Once the customer is happy with the offer in the quote and is ready to proceed with their order, they accept the quote.

Quote management and their use in many ways depend on the following:

* [Shipping Configuration](../../../concept-guides/shipping-configuration/index.md#user-guide-shipping):
  - Create one or more shipping methods by configuring [integrations with the shipping providers](../../system/integrations/shipping-integration/index.md#sys-integrations-manage-integrations-ups-flat-rate).
  - Set up [shipping rules](../../system/shipping-rules/index.md#sys-shipping-rules) that enable shipping methods for quotes/orders created with the specific destination areas and/or limit shipping availability via custom conditions.
  - Other. See the [Shipping Configuration](../../../concept-guides/shipping-configuration/index.md#user-guide-shipping) guide for more detailed information.
* [Payment Configuration](../../../concept-guides/payment-configuration/index.md#user-guide-payment):
  - Create one or more payment methods by configuring [integrations with the payment providers](../../system/integrations/payment-integration/index.md#sys-integrations-manage-integrations-payment-methods).
  - Set up [payment rules](../../system/payment-rules/index.md#sys-payment-rules) that enable payment methods for orders created with the specific destination areas and/or limit payment availability via custom conditions.
  - Other. See the [Payment Configuration](../../../concept-guides/payment-configuration/index.md#user-guide-payment) guide for more detailed information.
* Quote Management Process Configuration (Workflows):
  - For wider possibilities, ensure that one of the quote management workflows is activated:
    * [Quote Management Flow](../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#system-workflows-quote-backoffice-workflow) — A simple quote management flow, where a sales person is not bound by any limitations and can handle the sale without supervision.
    * [Backoffice Quote flow with Approvals](../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#doc-workflows-backoffice-quote-flow-with-approvals) (QBFA)— A flow, where a sales person might have to get approval from the authorized person (e.g. their manager) before sending the quote with updated prices to the buyer.
  - For the QBFA workflow, ensure the [prerequisites](../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#doc-workflows-backoffice-quote-flow-with-approvals-prerequisites) are met and the system is properly configured for the approval process.

To learn more on how to create and use quotes and their workflows, check out the topics below:

* [Create a Quote](create/index.md)
* [Manage Quotes](manage.md)
* [Send a Guest Quote](guest-quote.md)
* [Use Quotes Workflows](flows/index.md)
* [Assign a Shipping Method to a Quote](shipping-method-for-quotes.md)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
