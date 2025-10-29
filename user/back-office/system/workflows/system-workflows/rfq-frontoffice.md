<a id="system-workflows-rfq-frontoffice-workflow"></a>

<a id="system-workflows-rfq-frontoffice-workflow-rfq-illustration"></a>

<a id="system-workflows-rfq-frontoffice-workflow-rfq-customer-statuses"></a>

# Configure RFQ Submission Flow Workflow in the Back-Office

<!-- start_front_flow -->

## Overview

RFQ (Request For Quote) Submission Flow Workflow is a [system workflow](../index.md#user-guide-system-workflow-management-system-custom) that defines the sequence of [steps and transitions](../steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that an RFQ can go through in the storefront and the back-office.

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.
2. Click **RFQ Submission Flow** to open the flow.

On the RFQ Submission Flow page, you can disable the workflow by clicking <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** the workflow.

![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_1.png)

Within the Workflows list, you can perform the following actions for the RFQ Submission Flow workflow:

* View the workflow: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
* Deactivate the workflow: <i class="fa fa-times fa-lg" aria-hidden="true"></i>

![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_2.png)

## RFQ Customer Statuses

[RFQ Management Flow](rfq-backoffice.md#system-workflows-rfq-backoffice-workflow) and Submission Flow workflows are interconnected. When both workflows are active, the following statuses are available:

<!-- start_customer_statuses -->
1. Customer Statuses (correspond to RFQ Submission Flow on the RFQ page) are the statuses displayed to customers in the storefront. In the back-office, they are visible on the RFQ page:
   > 1. Submitted
   > 2. Pending Approval
   > 3. Requires Attention
   > 4. Cancelled

<!-- stop_customer_statuses -->![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_3.png)
1. Internal Statuses (correspond to RFQ Management Flow) are described in [RFQ Management Flow workflow](rfq-backoffice.md#system-workflows-rfq-backoffice-workflow).

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

## Steps and Transitions

The RFQ Submission Flow consists of the following steps and transitions:

| Steps                  | Transitions                                                              | Post-Transition Steps                                                           |
|------------------------|--------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| Submitted              | * Cancel<br/>* Decline<br/>* Request More Info<br/>* Cancel<br/>* Delete | * Canceled<br/>* Canceled<br/>* Requires Attention<br/>* Canceled<br/>* Deleted |
| Requires<br/>Attention | * Cancel<br/>* Declined<br/>* Provide More Info                          | * Canceled<br/>* Canceled<br/>* Submitted                                       |
| Canceled               | * Resubmit<br/>* Reopen                                                  | * Canceled<br/>* Submit                                                         |

#### NOTE
Please note that the Request For Information, Reopen and Decline transitions are visible only in the back-office for the sales personnel.

![image](user/img/system/workflows/rfq/frontoffice/RFQFrontofficeGrid_2.png)

## Sample Flow

As an illustration, let us go through a sample flow to see RFQ Submission Flow in action:

1. A customer user creates an RFQ in the storefront. Once the RFQ is sent, its customer status is marked as Submitted.
   ![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_3.png)
2. In the back-office, a sales representative sees the RFQ and requests more information. The RFQ is now in the Requires Attention customer status.
   ![image](user/img/system/workflows/rfq/frontoffice/rfq_submission_flow_6.png)
3. The customer user receives the request in the storefront, clicks Provide Information in the right corner of the page and replies to the message. The customer status is now Submitted.
   ![image](user/img/system/workflows/rfq/frontoffice/RFQProvideInfo.png)![image](user/img/system/workflows/rfq/frontoffice/RFQInformationProvided.png)
4. The sales representative reads the reply in the Notes section of the RFQ page, marks the RFQ processed and creates a quote from the same page. The RFQ is now in the Processed customer status.

<!-- finish_front_flow

  .. check this flow!

.. image:: /user/img/system/workflows/rfq/frontoffice/RFQNotes.png
.. image:: /user/img/system/workflows/rfq/frontoffice/RFQCreateQuote.png -->
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
