<a id="mc-sales-quotes-wf"></a>

# Use Quotes Workflows

The quote management procedure depends on the active quote-related workflow. Out of the box, the Oro application supports Simple Quote Management and Quote Management with Approvals.

<a id="simple-quote-management"></a>

## Simple Quote Management

#### NOTE
This flow is used when the [Quote Management Flow](../../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#system-workflows-quote-backoffice-workflow) is active.

<!-- As an illustration, let us see the quote in action and walk through the steps a buyer and a sales manager may follow to communicate or negotiate for the sale: -->

### Overview

Quote Management Flow (QBW) is a [system](../../../system/workflows/index.md#user-guide-system-workflow-management-system-custom) workflow that defines a sequence of [steps and transitions](../../../system/workflows/steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that a quote can go through as a deal progresses.

#### NOTE
The difference between the simple Quote Management Flow and the one with approval is covered in the [Understanding Quote Workflows](../../../system/workflows/system-workflows/quote-flows-overview.md#system-workflows-quote-understanding) section.

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.
2. Click **Quote Management Flow** to open the flow. The following page opens:

![image](user/img/system/workflows/workflows/QuoteBackofficeFlow.png)

#### NOTE
Since Quote Management Flow is a system workflow, it cannot be edited or deleted.

On the Quote Management Flow page, you can perform the following actions:

<!-- Clone the workflow - click |IcClone| to clone the workflow. -->
* Deactivate the workflow - click **Deactivate** to deactivate the workflow.

### Statuses

When the QMF is active, the following statuses are available:

1. Internal Statuses are the statuses displayed in OroCommerce to the sales personnel:
   1. Draft
   2. Sent to Customer
   3. Expired
   4. Accepted
   5. Declined
   6. Deleted
   7. Cancelled

![image](user/img/system/workflows/workflows/InternalStatusesGrid.png)
1. Customer Statuses are the statuses displayed to customers in the storefront:
   1. Open
   2. Expired
   3. Accepted
   4. Declined

#### NOTE
These statuses cannot be edited or deleted.

### Steps and Transitions

The QMF consists of the following steps and transitions:

1. Steps:
   1. Draft
   2. Sent to Customer
   3. Closed
   4. Deleted
2. Transitions:
   1. For **Draft**: Edit, Clone, Delete, Send to Customer
   2. For **Sent to Customer**: Cancel, Expire, Delete, Create New Quote, Accept, Decline, Declined by Customer
   3. For **Closed**: Reopen
   4. For **Deleted**: Undelete

![image](user/img/system/workflows/workflows/QBW_steps_transitions_table.png)

#### NOTE
Please note that Accepted and Declined transitions for the Sent to Customer step are automatically triggered by the changes of customer statuses and they do not, therefore, take the form of buttons in the interface.

### Sample Flow

As an illustration, let us go through a sample flow to see the QMF in action:

<!-- quote_in_use -->
1. Once a quote is created, it is automatically moved to the **Draft** step with the possibility to edit, clone, delete and send the quote to a customer.
   ![image](user/img/system/workflows/workflows/Illustration_1.png)
2. The quote with an offer valid until 19 April is sent to a customer.
   ![image](user/img/system/workflows/workflows/Illustration_2.png)

> The quote transitions from **Draft** state into **Sent to Customer**. Now it is possible to cancel, expire, delete, create a quote, or mark it as declined by customer.

> ![image](user/img/system/workflows/workflows/Illustration_3.png)

> #### NOTE
> If a customer generates an order based on the quote, you can leave the quote in the **Sent to Customer** state so that customer user could reuse it for future orders, or expire it to disable orders based on this quote.
1. The customer provided no feedback on the quote before 19 April, and the quote is expired by the sales personnel, leaving it in the **Closed** step.

> ![image](user/img/system/workflows/workflows/Illustration_4.png)
1. The offer has been reconsidered and validation date was extended until 21 April. The quote is reopened. It is moved back to the draft step with the possibility to edit, clone, delete and send the quote to a customer. The quote number is changed (in our case, from 21 to 22).

> ![image](user/img/system/workflows/workflows/Illustration_5.png)

#### NOTE
See more information about the [simple quote management](../../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#system-workflows-quote-backoffice-workflow) via the **Quote Management Flow**. You will learn additional details on the steps and actions available at every step.

<a id="quote-management-with-approvals"></a>

## Quote Management with Approvals

#### NOTE
This flows activates when the [Backoffice Quote Flow with Approvals](../../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#doc-workflows-backoffice-quote-flow-with-approvals) is enabled.

Read more in [Quote Management with Approvals](../../../system/workflows/system-workflows/backoffice-quote-flow-with-approvals.md#doc-workflows-backoffice-quote-flow-with-approvals) via the **Backoffice Quote Flow with Approvals**. You will learn additional details on the steps and actions available at every step.

## Workflow-Specific Statuses and Steps

Depending on the active workflow, the quote statuses and management steps may differ.

Follow the links below for more information on available steps and transitions.

* [Simple quote management (workflow-based)](steps-in-simple-quote-management.md#simple-quote-management-steps)
* [Quote management with approvals (workflow-based)](steps-in-quote-management-with-approvals.md#quote-management-with-approvals-steps)
* [Basic quote lifecycle management actions](steps-in-quote-management-no-workflow.md#quotes-basic-lifecycle-management) are used when quote-related workflows are disabled.
