<a id="user-guide-sales-orders-view"></a>

# View Order Details

<!-- begin_view -->

To view details of an order:

1. Navigate to **Sales > Orders** in the main menu.
2. Find the line with the necessary order and click it.

Alternatively, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View**.

![An order details page](user/img/sales/orders/order_all_page.png)

You can see the order name on the top left of the page.

In the next row, you can find when the order was created and last updated and whether the customer user who created the order has already been contacted.

To manage an order, use the actions buttons on the top right of the page. The following buttons are
available by default but depend on the order status:

- **Shipping Tracking** — Click to add [shipping tracking](track-order.md#user-guide-shipping-order).
- **Cancel** — Click to [cancel an order](control.md#doc-orders-actions-cancel). Available only for open orders.
- **Close** — Click to [close an order](control.md#doc-orders-actions-close). Available only for open and canceled orders.
- **Add Special Discount** — Click to [add special discounts](../../marketing/promotions/promotions/manage-discounts-in-orders.md#user-guide-sales-orders-promotions-add-special-discount).
- **Add Coupon Code** — Click to [provide a coupon code](../../marketing/promotions/coupons/index.md#user-guide-marketing-promotions-coupons-edit-on-order-page).
- **Edit** — Click to [edit an order](manage.md#user-guide-sales-orders-edit).
- **Delete** — Click to [delete an order](manage.md#doc-orders-actions-delete).
- **Download** — Click to download a PDF of the current order. Each time you click, a new PDF is generated with an updated timestamp.
- **More Actions** drop-down:
  - **Add Attachment** — Click to [attach a file to the order](../../getting-started/information-management/attachments.md#user-guide-activities-attachments).
  - **Add Note** — Click to [make a note regarding this order](../../getting-started/information-management/notes.md#user-guide-add-note).
  - **Add Event** — Click to [add an event](../../activities/calendar-events/index.md#doc-activities-events).
  - **Send Email** — Click to [send an email related to the order](../../getting-started/user-menu/my-emails.md#user-guide-using-emails).

In the next row, you can check which user is responsible for the order (owns it). Click the owner name to open the profile of the corresponding user. Enclosed in parentheses is the name of the organization to which the owner belongs.

Click the **Change History** link to see who, how, and when modified the product.

**General**

This section is for order details, such as who created the order or to which website this order applies.

![The General section of the order details page](user/img/sales/orders/order_details_general.png)

| Field                      | Description                                                                                                                                                                                                                                                        |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Order Number**           | The unique order reference number. It is generated automatically for new orders.                                                                                                                                                                                   |
| **PO Number**              | Another order reference number. It is usually defined by the buyer and used by the buyer’s side to match invoice and received goods with purchase.                                                                                                                 |
| **Currency**               | The currency in which the order is made.                                                                                                                                                                                                                           |
| **Subtotal**               | The amount due for items in the order. Does not include additional costs, taxes, discounts.                                                                                                                                                                        |
| **Customer**               | The customer that made the order.                                                                                                                                                                                                                                  |
| **Customer User**          | The customer user that created an order on behalf of their customer.                                                                                                                                                                                               |
| **Internal Status**        | The order status is managed only in the back-office. See the [description of internal statuses](statuses.md#doc-orders-statuses-internal).                                                                                                                         |
| **Do Not Ship Later Than** | The date on which the order expires.                                                                                                                                                                                                                               |
| **Source Document**        | If the order has been created from an RFQ, quote, or another order, this field contains a link to the corresponding record. If the order was created from scratch (in the back-office) or through the quick order form (in the storefront), the field shows ‘N/A’. |
| **Created By**             | The name of the user who created an order on behalf of a customer user, either via the back-office or [customer user impersonation](../../customers/customer-users/index.md#user-guide-customers-customer-user-impersonate) in the storefront.                     |
| **Payment Method**         | The payment method selected to pay for the order.                                                                                                                                                                                                                  |
| **Payment Status**         | Whether the order is already paid in full, the payment for the order is authorized, etc.                                                                                                                                                                           |
| **Website**                | The storefront website from which the order was made.                                                                                                                                                                                                              |
| **Billing Address**        | The address where the buyer receives the payment statements. Some payment providers use a billing address to authorize payments and demand it to match the payment account holder’s current address.                                                               |
| **Shipping Address**       | The address to deliver the ordered goods to.                                                                                                                                                                                                                       |
| **Customer Notes**         | Any additional information or wishes provided by the buyer regarding the order.                                                                                                                                                                                    |
| **Payment Term**           | The terms and conditions for order payment. For more information, see [Payment Terms Integration](../../system/integrations/payment-integration/payment-terms/index.md#sys-integrations-manage-integrations-payment-term).                                         |
| **Warehouse**              | The warehouse from which the goods are shipped.                                                                                                                                                                                                                    |

**Line Items**

This section lists products added to the order and their details.

![The Line Items section of the order details page](user/img/sales/orders/order_details_lineitems.png)

The product information visible by default is the following:

| Field                 | Description                                                                       |
|-----------------------|-----------------------------------------------------------------------------------|
| **SKU**               | The stock keeping unit that helps identify the product and track it in inventory. |
| **PRODUCT**           | The name of the product, the way it appears on the user interface.                |
| **QUANTITY**          | The ordered quantity of product units.                                            |
| **PRODUCT UNIT CODE** | Whether the product variant is enabled and can be used.                           |
| **PRICE**             | Agreed price for the individual product unit.                                     |
| **SHIP BY**           | The date before this product must be shipped.                                     |

If an order contains [product kit(s)](../../products/products/create-kit.md#products-products-create-product-kit), each individual item will contain a link to its view page in the back-office.

![Product kit in the Line Items section of the order view page with links to each item in the kit](user/img/products/products/kits/kit-in-bo-orders.png)

**Shipping Information**

This section displays details of shipping tracking and cost.

**Discounts**

This section provides information about promotions and discounts applied to the order. The section is divided into **All Promotions** and **All Special Discounts**.

Within **All Promotions**, you can view:

* Promotions added automatically if the order qualifies
* Coupon codes added manually

#### NOTE
Promotions can be disabled for orders via REST API, in which case the following message is displayed:

*Promotions are disabled for the order.*

Within **All Special Discounts**, you can view:

* Special discounts added manually

For more information, see [Promotions and Discounts](../../marketing/promotions/promotions/index.md#user-guide-marketing-promotions).

**Totals**

This section shows order costs, including any discounts (in all currencies, configured for the purpose).

![The Totals section of the order details page](user/img/sales/orders/order_details_totals.png)

**Payments**

This section provides information about payment transactions related to the order.

![The Payment History section of the order details page](user/img/sales/orders/order_details_paymenthistory.png)

| Field              | Description                                                                                                                                 |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **ID**             | The unique identifier of the payment transaction.                                                                                           |
| **PAYMENT METHOD** | The payment method used to pay for the order.                                                                                               |
| **TYPE**           | The type of the transaction. For example:<br/><br/>> * *Authorize*<br/>> * *Charge*<br/>> * *Validate*<br/>> * *Capture*<br/>> * *Purchase* |
| **AMOUNT**         | The transaction amount and currency.                                                                                                        |
| **ACTIVE**         | Whether the transaction is being processed.                                                                                                 |
| **SUCCESSFUL**     | Whether the transaction has been successfully processed.                                                                                    |
| **Created At**     | The date and time when the transaction started.                                                                                             |
| **Updated At**     | The date and time when the transaction information was last updated.                                                                        |
<!-- For information on configuring visible fields, the number of items per page, etc., see the :ref:`Grids <doc-grids>` topic. -->

#### HINT
This section is visible only to the users with the corresponding permission.

If you do not see this section, contact your administrator.

If you are an administrator, find the Order entity and check the access level configured for the View Payment action.

**Invoices**

When the invoice functionality is [enabled in the system configuration](../../system/configuration/commerce/sales/global-invoices.md#configuration-guide-commerce-configuration-sales-invoices), you can view invoices associated with an order in the dedicated *Invoices* tab. Click on the invoice to open its view page.

![Invoices tab on the order view page](user/img/sales/invoices/invoices-order-view-page.png)

**Activity**

This section displays any notes, calendar events, conversations or emails related to the order.

You can filter activities by type and by date (e.g., the exact date or a date range that covers the activity date) and browse them from the newest to the oldest and vice versa.

You can see who started the activity, its type, name, and description, when it was created, and the number of comments left for it.

Click the activity to see detailed information about it.

![The details of the selected activity](user/img/sales/orders/products_review_activity_manage2.png)

To edit the activity, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Update**. In the dialog that appears, make the required changes and then click **Save**.

To delete the activity, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete**. In the confirmation dialog, click **Yes, Delete**.

You can add and delete an activity context.

To add a context to the activity, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click <i class="fa fa-link fa-lg" aria-hidden="true"></i> **Add Context**. In the **Add Context Entity** dialog, select the desired context and click it to select.

![Available options displayed after clicking the More Options menu](user/img/sales/orders/activity_note_moreoptions.png)

You can reply/reply to all/forward the corresponding email for email activity. To do this, click the corresponding icon in the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the activity row. Alternatively, click activity to expand it, and select the required action from the list on the right.

![Available email activity options displayed after clicking the More Options menu](user/img/sales/orders/activity_email_moreoptions.png)

To delete a context from the activity, click the activity to expand it, and under the activity name, click the **x** icon next to the context you want to remove.

You can add a comment under a particular activity. To do this:
Click the activity to expand it, and click **Add Comment**.
In the **Add Comment** dialog, type your message.
Use the built-in text editor to format your comment. You can also attach a file to your comment.
For this, click the **Upload** link in the dialog and locate the required file. When the comment is ready, click **Add**.

To edit or delete a comment, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu next to it and click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** or ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** icon correspondingly.

For more information about activities, see the [Activities](../../activities/index.md#user-guide-productivity-tools) guide.

**Marketing Activity**

This section shows any activity of this kind associated with the order.

**Additional Information**

This section includes any attachments, if available.

For information on attachments and how to manage them, see the [Attachments](../../getting-started/information-management/attachments.md#user-guide-activities-attachments) guide.

<!-- finish_view -->
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
