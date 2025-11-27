<a id="mc-sales-rfq-wf"></a>

# Use RFQ Workflows

#### HINT
This section is part of the [RFQ and Quote Management](../../../concept-guides/customers-sales/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides a general understanding of the RFQ and quote concepts in OroCommerce.

The RFQ management procedure depends on the active RFQ-related workflows. Out of the box, the Oro application supports RFQ Submission Flow and RFQ Management Flow.

## RFQ Submission Flow

### Overview

RFQ (Request For Quote) Submission Flow Workflow is a [system workflow](../../system/workflows/index.md#user-guide-system-workflow-management-system-custom) that defines the sequence of [steps and transitions](../../system/workflows/steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that an RFQ can go through in the storefront and the back-office.

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.
2. Click **RFQ Submission Flow** to open the flow.

On the RFQ Submission Flow page, you can disable the workflow by clicking <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** the workflow.

![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_1.png)

Within the Workflows list, you can perform the following actions for the RFQ Submission Flow workflow:

* View the workflow: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
* Deactivate the workflow: <i class="fa fa-times fa-lg" aria-hidden="true"></i>

![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_2.png)

### RFQ Customer Statuses

[RFQ Management Flow](../../system/workflows/system-workflows/rfq-backoffice.md#system-workflows-rfq-backoffice-workflow) and Submission Flow workflows are interconnected. When both workflows are active, the following statuses are available:

<!-- start_customer_statuses -->
1. Customer Statuses (correspond to RFQ Submission Flow on the RFQ page) are the statuses displayed to customers in the storefront. In the back-office, they are visible on the RFQ page:
   > 1. Submitted
   > 2. Pending Approval
   > 3. Requires Attention
   > 4. Cancelled

<!-- stop_customer_statuses -->![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_3.png)
1. Internal Statuses (correspond to RFQ Management Flow) are described in [RFQ Management Flow workflow](../../system/workflows/system-workflows/rfq-backoffice.md#system-workflows-rfq-backoffice-workflow).

#### NOTE
Neither customer nor internal statuses can be edited or deleted.

Statuses are also displayed in the RFQ list:

![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_4.png)

The following table describes which options are available for each of the statuses, and how the corresponding transitions change them.

| Step                                                                                                       | Current Internal Status    | Current Customer Status                          |
|------------------------------------------------------------------------------------------------------------|----------------------------|--------------------------------------------------|
| An RFQ is submitted by a customer                                                                          | Open                       | Submitted                                        |
| The RFQ is marked as processed by sales representative. The customer is not authorized to view this status | Processed                  | Submitted                                        |
| Sales representative requests more information from the customer                                           | More Information Requested | Requires Attention                               |
| The customer responds to the request and provides the additional information                               | Open                       | Submitted                                        |
| The RFQ is declined                                                                                        | Declined                   | Cancelled                                        |
| The RFQ is deleted and no further actions are possible unless it is reopened                               | Deleted                    | The RFQ is removed from the customer user’s page |

#### NOTE
You can add and remove columns in the workflows list by clicking <i class="fas fa-cog" aria-hidden="true"></i> on the far right of the list.

![image](user/img/system/workflows/rfq/frontoffice/GridSettings.png)

### Steps and Transitions

The RFQ Submission Flow consists of the following steps and transitions:

1. Steps:
   1. Submitted
   2. Requires Attention
   3. Cancelled
2. Transitions:
   1. For **Submitted**: Cancel, Decline, Request More Information
   2. For **Requires Attention**: Cancel, Decline, Provide More Information
   3. For **Cancelled**: Resubmit, Reopen

![image](user/img/system/workflows/rfq/frontoffice/RFQFrontOfficeTable.png)

#### NOTE
Please note that the Request For Information, Reopen and Decline transitions are visible only in the back-office for the sales personnel.

![image](user/img/system/workflows/rfq/frontoffice/RFQFrontofficeGrid_2.png)

### Sample Flow

As an illustration, let us go through a sample flow to see RFQ Submission Flow in action:

1. A customer user creates an RFQ in the storefront. Once the RFQ is sent, its customer status is marked as Submitted.
   ![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_3.png)
2. In the back-office, a sales representative sees the RFQ and requests more information. The RFQ is now in the Requires Attention customer status.
   ![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_6.png)
3. The customer user receives the request in the storefront, clicks Provide Information in the right corner of the page and replies to the message. The customer status is now Submitted.
   ![image](user/img/system/workflows/rfq/frontoffice/RFQProvideInfo.png)![image](user/img/system/workflows/rfq/frontoffice/RFQInformationProvided.png)
4. The sales representative reads the reply in the Notes section of the RFQ page, marks the RFQ processed and creates a quote from the same page. The RFQ is now in the Processed customer status.

## RFQ Management Flow

### Overview

RFQ (Request For Quote) Management Flow workflow is a [system workflow](../../system/workflows/index.md#user-guide-system-workflow-management-system-custom) that defines the sequence of [steps and transitions](../../system/workflows/steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that an RFQ can go through in the back-office.

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.
2. Click **RFQ Management Flow** to open the flow.

On the RFQ Management Flow page, you can disable the workflow by clicking **Deactivate** the workflow.

![image](user/img/system/workflows/rfq/backoffice/rfq_management_flow_1.png)

Within the Workflows list, you can perform the following actions for the RFQ Management Flow workflow:

* View the workflow: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
* Deactivate the workflow: <i class="fa fa-times fa-lg" aria-hidden="true"></i>

![image](user/img/system/workflows/rfq/backoffice/rfq_management_flow_2.png)

### RFQ Internal Statuses

RFQ Management Flow and [Submission Flow](../../system/workflows/system-workflows/rfq-frontoffice.md#system-workflows-rfq-frontoffice-workflow) workflows are interconnected. When both workflows are active, the following statuses are available:

1. Customer Statuses (correspond to RFQ Submission Flow on the RFQ page) are described in [RFQ Submission Flow](../../system/workflows/system-workflows/rfq-frontoffice.md#system-workflows-rfq-frontoffice-workflow).

<!-- start_internal_statuses -->
1. Internal Statuses (correspond to RFQ Management Flow on the RFQ page) are the statuses displayed in OroCommerce to the sales personnel:
   > 1. Open
   > 2. Processed
   > 3. More Information Requested
   > 4. Declined
   > 5. Cancelled
   > 6. Deleted

#### NOTE
RFQs with internal status Deleted are not visible in the storefront.

<!-- stop_internal_statuses -->

#### NOTE
Neither customer nor internal statuses can be edited or deleted.

<!-- start_csv_table_statuses -->![image](user/img/system/workflows/rfq/backoffice/Statuses.png)

The following table describes which options are available for each of the statuses, and how the corresponding transitions change them.

| Step                                                                                                       | Current Internal Status    | Current Customer Status                          |
|------------------------------------------------------------------------------------------------------------|----------------------------|--------------------------------------------------|
| An RFQ is submitted by a customer                                                                          | Open                       | Submitted                                        |
| The RFQ is marked as processed by sales representative. The customer is not authorized to view this status | Processed                  | Submitted                                        |
| Sales representative requests more information from the customer                                           | More Information Requested | Requires Attention                               |
| The customer responds to the request and provides the additional information                               | Open                       | Submitted                                        |
| The RFQ is declined                                                                                        | Declined                   | Cancelled                                        |
| The RFQ is deleted and no further actions are possible unless it is reopened                               | Deleted                    | The RFQ is removed from the customer user’s page |
<!-- stop_csv_table_statuses -->

#### NOTE
You can add and remove columns in the list by clicking <i class="fas fa-cog" aria-hidden="true"></i> on the far right.

![image](user/img/system/workflows/rfq/frontoffice/GridSettings.png)

### Steps and Transitions

RFQ Management Flow consists of the following steps and transitions:

1. Steps:
   > 1. Open
   > 2. More Information Requested
   > 3. Processed
   > 4. Declined
   > 5. Cancelled
   > 6. Deleted
2. Transitions:
   > 1. For **Open**: Mark as Processed, Request More Information, Decline, Cancel, Delete.
   > 2. For **More Information Requested**: Cancel, Delete, Info Provided.
   > 3. For **Processed**: Delete.
   > 4. For **Declined**: Cancel, Delete, Reprocess.
   > 5. For **Cancelled**: Delete, Reprocess.
   > 6. For **Deleted**: Undelete.

#### NOTE
Please note that the Info Provided transition for the More Information Requested step is automatically triggered and it does not, therefore, take the form of a button in the interface.

![image](user/img/system/workflows/rfq/backoffice/RQF_steps_transitions_table.png)

#### NOTE
Steps that follow the **Undelete** transition depend on the internal and/or customer statuses prior to deletion:

- If the previous internal status is Cancelled By Customer (step Cancelled), the internal status becomes Cancelled By Customer.
- If the current customer status is Submitted or Cancelled and the previous internal status is not Cancelled By Customer (step Open), the internal status becomes Open and the customer status becomes Submitted.
- If the current customer status is Requires Attention and the previous internal status is not Cancelled By Customer (step More Info Requested), the internal status becomes More Info Requested.

### Sample Flow

<!-- begin_back_rfq -->

As an illustration, let us go through a sample flow to see RFQ Management Flow in action:

1. Once an RFQ is received, it is automatically moved to the Open step with a possibility to mark this request processed, request more information, decline or delete it.

![image](user/img/system/workflows/rfq/backoffice/rfq_management_flow_3.png)
1. More information has been requested, the RFQ is now in the More Information requested step with Requires Attention customer status. The only transition available in this step is Delete.

![image](user/img/system/workflows/rfq/backoffice/rfq_management_flow_4.png)

#### NOTE
It is possible to create a quote or an order straight from the RFQ page by clicking on the corresponding buttons in the top right corner of the page.

1. More information has been provided, the sales person marks the RFQ processed and creates a quote straight from the RFQ view page.
   <!-- check if this workflow is correct! -->

![image](user/img/system/workflows/rfq/backoffice/rfq_management_flow_5.png)![image](user/img/system/workflows/rfq/backoffice/rfq_back_9.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
