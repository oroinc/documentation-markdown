<a id="mc-sales-rfq-manage"></a>

# Manage RFQs

#### HINT
This section is part of the [RFQ and Quote Management](../../../concept-guides/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides a general understanding of the RFQ and quote concepts in OroCommerce.

From the **Requests for Quote** page, you can perform the following actions:

* [Create a Quote from an RFQ]()
* [Create an Order from an RFQ]()
* [Edit an RFQ]()
* [Use RFQ Transitions]()
* [Mark the RFQ as Processed]()
* [Request More Information from the Customer]()
* [Decline an RFQ]()
* [Delete an RFQ]()

You can also engage RFQs in various activities, such as [adding a note](../../getting-started/information-management/notes.md#user-guide-add-note), [sending an email](../../getting-started/user-menu/my-emails.md#user-guide-using-emails) or [adding an event](../../activities/calendar-events/index.md#doc-activities-events) to an RFQ.

![Various activities available for rfqs](user/img/sales/rfq/rfq_4.png)

## Create a Quote from an RFQ

To create a new quote from a specific RFQ:

1. Navigate to **Sales > Request for Quotes** in the main menu.
2. Find the required RFQ and click on it.
3. Click **Create Quote**.

See more information about creating a quote from the RFQ in the relevant [Create a Quote from the RFQ](../quotes/create/create-from-rfq.md#quote-create-from-rfq) topic.

Additionally, you can perform the following actions by clicking on the corresponding buttons on the far right of the Quote page:

* Click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to edit the quote.
* Click <i class="far fa-copy" aria-hidden="true"></i> to clone the quote.
* Click <i class="fas fa-trash-alt" aria-hidden="true"></i> to delete it.
* Click <i class="fa fa-envelope fa-lg" aria-hidden="true"></i> **Send to Customer** to send a notification email message the customer user regarding their quote.
  ![The steps you need to take to create send a quote to a customer](user/img/sales/rfq/rfq_7.png)

Once the message is prepared and sent, the quote backoffice status is changed to *Sent to customer*.

![A sample of the quote with the Sent to Customer status and available actions](user/img/sales/rfq/rfq_8.png)

From this page, you can cancel <i class="fa fa-times fa-lg" aria-hidden="true"></i> or expire <i class="far fa-clock" aria-hidden="true"></i> the quote, delete <i class="fas fa-trash-alt" aria-hidden="true"></i> the quote, and the back-office status will change to *Closed*.

Additionally, you can create a new quote for the customer, or if the customer declined the offer, you can mark it as **Declined by Customer**.

For more detailed information, please check the [Quote Management Flow](../quotes/flows/index.md#simple-quote-management) to learn additional details on the steps and actions available at every step.

## Create an Order from an RFQ

To create an order from an RFQ:

1. Navigate to **Sales > Request for Quotes** in the main menu.
2. Find the required RFQ and click on it.
3. Click **Create an Order** on the top right.

#### NOTE
You can find more information on how to create an order from an RFQ, add additional products, add offers specifically for the customer, edit or add shipping and billing information, calculate shipping options, add discounts, and more in the relevant [Create an Order from an RFQ](../orders/create.md#user-guide-sales-orders-create-from-rfq) topic.

The **More Actions** menu enables users to [add notes](../../getting-started/information-management/notes.md#user-guide-add-note) to the order, [send an email](../../getting-started/user-menu/my-emails.md#user-guide-using-emails) to the customer or [add an event](../../activities/calendar-events/index.md#doc-activities-events). An event could be used to schedule a call or a meeting.

![Click Create Order from the RFQ view page](user/img/sales/rfq/rfq_11.png)

<a id="user-guide-sales-requests-for-quote-edit"></a>

## Edit an RFQ

To edit an RFQ:

1. Navigate to **Sales > Request for Quotes** in the main menu.
2. Find the required RFQ and click on it.
3. Click **Edit** on the top right of the page.
4. Check the fields required in the **General** section and modify the information, if necessary.
5. Add notes and assignees.
6. Adjust target prices and quantity and add additional products.
7. Click **Save and Close** on the top right to save all the changes made.

<a id="user-guide-sales-requests-for-quote-steps-and-transitions"></a>

## Use RFQ Transitions

#### NOTE
The workflow transitions are available for customers and sales representatives when [RFQ Submission Flow](../../system/workflows/system-workflows/rfq-frontoffice.md#system-workflows-rfq-frontoffice-workflow) and [RFQ Management Flow](../../system/workflows/system-workflows/rfq-backoffice.md#system-workflows-rfq-backoffice-workflow) workflows are activated in the system configuration.

To control RFQ using transitions exposed by RFQ workflows ([RFQ Submission Flow](../../system/workflows/system-workflows/rfq-frontoffice.md#system-workflows-rfq-frontoffice-workflow) and [RFQ Management Flow](../../system/workflows/system-workflows/rfq-backoffice.md#system-workflows-rfq-backoffice-workflow)):

1. Navigate to **Sales > Request for Quotes** in the main menu.
2. Find the required RFQ and click on it to open RFQ details.

Now you can perform the following actions with an RFQ in the back-office:

> * [Mark the RFQ as Processed](#mark-the-rfq-as-processed)
> * [Request More Information from the Customer](#request-more-information-from-the-customer)
> * [Decline an RFQ](#decline-an-rfq)
> * [Delete an RFQ](#delete-an-rfq)

Once a customer submits the RFQ in the storefront, it becomes immediately available in the RFQ back-office in the *Open* status.

![Display the RFQ with the customer status Submitted in the storefront](user/img/sales/rfq/rfq_12.png)![Display the RFQ with the internal status Open in the back-office](user/img/sales/rfq/rfq_13.png)

<a id="user-guide-sales-requests-for-quote-steps-and-transitions-processed"></a>

### Mark the RFQ as Processed

Click **Mark as Processed** <i class="fa fa-archive fa-lg" aria-hidden="true"></i> on the RFQ page to mark the RFQ as processed. This will notify the assigned sales representative that the quote is being processed.

Marking RFQ as processed will change its internal status to *Processed*.

![Display the RFQ with the internal status Processed in the back-office](user/img/sales/rfq/rfq_14.png)

<a id="user-guide-sales-requests-for-quote-steps-and-transitions-more-info"></a>

### Request More Information from the Customer

To request more information from a customer:

1. Click **Request More Information** <i class="far fa-question-circle" aria-hidden="true"></i> to open a text dialog for you to communicate with the customer.
2. Enter a comment.
3. Click **Submit**.

The customer will be notified by email and through the customer’s store account that more information is required.

The internal status should then change to *More Information Requested*, and the customer status should change to *Requires Attention*.

![Display the RFQ with the internal status More Information Requested in the back-office](user/img/sales/rfq/rfq_16.png)

Once the customer responds to the request for additional information, the assigned sales representative is notified that the customer has provided the requested information and can continue processing the request.

The internal status changes back to *Open*, and the customer status changes back to *Submitted*.

<a id="user-guide-sales-requests-for-quote-steps-and-transitions-decline"></a>

### Decline an RFQ

To decline the RFQ,  click **Decline** on the RFQ page.

This will change the internal status to *Declined\*and the customer status to \*Cancelled*.

![Display the RFQ with the internal status Declined in the back-office](user/img/sales/rfq/rfq_17.png)

<a id="user-guide-sales-requests-for-quote-steps-and-transitions-delete"></a>

### Delete an RFQ

Click **Delete** on the RFQ page to delete the RFQ from the list.

The RFQ will be removed from the customer user’s account.

The internal status will be changed to *Deleted*.

![Display the RFQ with the internal status Deleted in the back-office](user/img/sales/rfq/rfq_18.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
