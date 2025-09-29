<a id="quotes-basic-lifecycle-management"></a>

# Basic Quote Lifecycle Management (When Workflows Are Disabled)

Available options depend on the current status of the quote and your permissions. These actions appear only when all the quote-related workflows are disabled and the default (basic) quote management applies.

## Edit a Quote

#### IMPORTANT
This option is available only when:

* [Quote Management Flow](index.md#simple-quote-management) / [Backoffice Quote Flow with Approvals](index.md#quote-management-with-approvals) are inactive.
* One of the workflows is active and the current workflow step allows editing the quote.

To edit a quote:

1. Navigate to **Sales > Quotes** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon to start editing its details.

   #### IMPORTANT
   Note that the icon that starts a workflow looks alike to the **Edit** icon. Please check the hint that appears when you hoover over the icon to make sure that you select the desired action.
3. Update the **Quote General Information**, **Line Items**, **Shipping Address**, or **Shipping Information** sections. See [Create a Quote](../create/create-from-scratch.md#quote-create-from-scratch) topic for detailed information on the available options.
4. Click **Save** on the top right of the page.

The quote is updated.

Learn [more ways to edit a quote](../manage.md#quotes-actions-edit).

<a id="quotes-actions-notify-customer"></a>

## Notify a Customer About the Quote

<!-- begin -->

#### IMPORTANT
You can send notification to the customer in this way only when the [Quote Management Flow](index.md#simple-quote-management) / [Backoffice Quote Flow with Approvals](index.md#quote-management-with-approvals) are inactive.

To notify a customer that their quote is prepared:

1. In the main menu, navigate to **Sales > Quotes**.
2. Choose the quote in the list and click it. The quote details page opens.
3. Click <i class="fa fa-caret-down fa-lg" aria-hidden="true"></i> next to **Notify Customer** on the top right of the page, and then click **Notify By Email**.
4. In the **Notify By Email** dialog that appears, review the email draft. If required, add additional recipients to the **To**, **CC**, or **BCC** fields, or make other changes. The email body may be adjusted to be more personalized.
   ![A sample of an email sent to a customer to notify them about the quote readiness](user/img/sales/quotes/quotes_notifycustomer2.png)
5. Click **Send**.

#### HINT
By default, the quote_email_link email template is used for this type of notifications. You can select another one or, if you have corresponding permissions, you can [adjust the email template](../../../system/emails/email-templates.md#user-guide-email-template). If you do not have permissions to modify templates, ask your administrator for help.

The quote internal status becomes *Sent to Customer*.

<!-- finish -->

<a id="quotes-actions-expire"></a>

## Mark a Quote as Expired

<a id="quotes-actions-expire-fromgrid"></a>

### Expire a Quote From the Grid

<!-- begin -->

#### IMPORTANT
You can expire a quote in this way only when the [Quote Management Flow](index.md#simple-quote-management) / [Backoffice Quote Flow with Approvals](index.md#quote-management-with-approvals) are inactive.

![Click the Expire Quote button](user/img/sales/quotes/quotes_expire.png)

To indicate that the quote’s validity period is over from the quote list:

1. In the main menu, navigate to **Sales > Quotes**. The quote list opens.
2. Choose the quote that you need to expire, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the <i class="far fa-clock" aria-hidden="true"></i> **Expire Quote** icon.
3. In the confirmation dialog, click **Mark as Expired**.

The quote’s **Expired** field in the list is now set to *Yes*.

<!-- finish -->

<a id="quotes-actions-expire-fromviepage"></a>

### Expire a Quote From the Quote View Page

#### IMPORTANT
You can expire a quote in this way only when the [Quote Management Flow](index.md#simple-quote-management) / [Backoffice Quote Flow with Approvals](index.md#quote-management-with-approvals) are inactive.

To indicate that the quote’s validity period is over from the quote details page:

1. In the main menu, navigate to **Sales > Quotes**.
2. Choose the quote in the list and click it. The quote details page opens.
3. Click the **Expire Quote** button on the top right of the page.
4. In the confirmation dialog, click **Mark as Expired**.

The quote is now marked as *Expired*:

![A sample of the quote that is marked as expired](user/img/sales/quotes/quotes_expired.png)

### Expire a Quote From the Quote Edit Page

#### IMPORTANT
You can expire a quote in this way only when the [Quote Management Flow](index.md#simple-quote-management) / [Backoffice Quote Flow with Approvals](index.md#quote-management-with-approvals) are inactive.  Otherwise, use the Edit transition defined within the active workflow:

![Click the Edit button within the active Backoffice Quote Flow with Approvals workflow](user/img/sales/quotes/quotes_workflowedit1.png)

To indicate that the quote’s validity period is over from the quote details page:

1. In the main menu, navigate to **Sales > Quotes**.
2. Choose the quote in the list and click it. The quote details page opens.
3. Click **Edit** on the top right of the page:
   ![Click the Edit button on the quote edit page](user/img/sales/quotes/quotes_edit1.png)
4. Update the **Quote General Information**, **Line Items**, **Shipping Address**, or **Shipping Information** sections. See [Create a Quote](../create/index.md#user-guide-quotes-create) section for detailed information on the available options.
5. Click **Save** on the top right of the page.

The quote is updated.

Learn [more ways to expire a quote](#quotes-actions-expire).

### Delete a Quote

#### IMPORTANT
This option is available only when:

* [Quote Management Flow](index.md#simple-quote-management) / [Backoffice Quote Flow with Approvals](index.md#quote-management-with-approvals) are inactive.
* One of the workflows is active and the current workflow step allows editing the quote.

To edit a quote:

1. Navigate to **Sales > Quotes** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon to start editing its details.

   #### IMPORTANT
   Note that the icon that starts a workflow looks alike to the **Edit** icon. Please check the hint that appears when you hoover over the icon to make sure that you select the desired action.
3. Update the **Quote General Information**, **Line Items**, **Shipping Address**, or **Shipping Information** sections. See [Create a Quote](../create/create-from-scratch.md#quote-create-from-scratch) topic for detailed information on the available options.
4. Click **Save** on the top right of the page.

The quote is updated.

Learn [more ways to delete a quote](../manage.md#quotes-actions-delete).

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
