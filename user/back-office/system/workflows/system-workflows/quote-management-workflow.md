<a id="system-workflows-quote"></a>

# Configure Quote Management Flow in the Back-Office

<!-- start_quote_management_flow -->

Quote Management Flow (QMF) is a [system](../index.md#user-guide-system-workflow-management-system-custom) workflow that defines a sequence of [steps and transitions](../steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that a quote can go through as a deal progresses.

#### NOTE
For more information on the difference between the simple Quote Management Flow and the one with approvals, see [Configure Quote Workflows in the Back-Office](quote-flows-overview.md#system-workflows-quote-understanding).

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.
2. Click **Quote Management Flow** to open the flow. The following page opens:

![image](user/img/system/workflows/workflows/QuoteBackofficeFlow.png)

#### NOTE
Since Quote Management Flow is a system workflow, it cannot be edited or deleted.

On the Quote Management Flow page, you can perform the following actions:

<!-- Clone the workflow - click |IcClone| to clone the workflow. -->
* Deactivate the workflow - click **Deactivate** to deactivate the workflow.

## Statuses

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

## Steps and Transitions

The QMF consists of the following steps and transitions:

| Steps            | Transitions                                                                                                     | Post-Transition Steps                                                                             |
|------------------|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| Draft            | * Edit<br/>* Clone<br/>* Delete<br/>* Send to Customer                                                          | * Draft<br/>* Draft<br/>* Deleted<br/>* Sent to Customer                                          |
| Sent to Customer | * Cancel<br/>* Expire<br/>* Delete<br/>* Create New Quote<br/>* Accept<br/>* Decline<br/>* Declined by Customer | * Closed<br/>* Closed<br/>* Deleted<br/>* Sent to Customer<br/>* Closed<br/>* Closed<br/>* Closed |
| Closed           | * Reopen                                                                                                        | * Closed                                                                                          |
| Deleted          | * Undelete                                                                                                      | * Draft                                                                                           |

#### NOTE
Please note that Accepted and Declined transitions for the Sent to Customer step are automatically triggered by the changes of customer statuses and they do not, therefore, take the form of buttons in the interface.

## Sample Flow

As an illustration, let us go through a sample flow to see the QMF in action:

<!-- quote_in_use -->
1. Once a quote is created, it is automatically moved to the **Draft** step with the possibility to edit, clone, delete and send the quote to a customer.
   ![image](user/img/system/workflows/workflows/Illustration_1.png)
2. The quote with an offer valid until a specific date is sent to a customer.
   ![image](user/img/system/workflows/workflows/Illustration_2.png)

> The quote transitions from **Draft** state into **Sent to Customer**. Now it is possible to cancel, expire, delete, create a quote, or mark it as declined by customer.

> ![image](user/img/system/workflows/workflows/Illustration_3.png)

> #### NOTE
> If a customer generates an order based on the quote, you can leave the quote in the **Sent to Customer** state so that customer user could reuse it for future orders, or expire it to disable orders based on this quote.
1. The customer provided no feedback on the quote before the given date, and the quote is expired by the sales personnel, leaving it in the **Closed** step.

> ![image](user/img/system/workflows/workflows/Illustration_4.png)
1. The offer has been reconsidered and validation date was extended until a later date. The quote is reopened. It is moved back to the draft step with the possibility to edit, clone, delete and send the quote to a customer. The quote number is changed (in our case, from 21 to 22).

> ![image](user/img/system/workflows/workflows/Illustration_5.png)
<!-- finish_quote_management_flow -->
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
