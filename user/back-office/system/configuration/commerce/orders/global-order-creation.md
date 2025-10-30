<a id="configuration-commerce-orders-order-creation-global"></a>

<a id="configuration-commerce-orders-create"></a>

# Configure Global Order Creation Settings

You can automatically assign a status to new [orders](../../../../../glossary.md#term-Order) once they are created.

#### HINT
This can be done globally, [per organization](../../../user-management/organizations/org-configuration/commerce/orders/organization-order-creation.md#configuration-commerce-orders-order-creation-organization) and [per website](../../../websites/web-configuration/commerce/orders/website-order-creation.md#configuration-commerce-orders-order-creation-website).

To assign an order status globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Orders > Order Creation** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).
3. In the **Order Creation** section, clear the **Use Default** checkbox next to the required option, if it is selected, to toggle the following options:
   * **New Internal Order Status** — Select the [status](../../../../sales/orders/statuses.md#doc-orders-statuses-internal) to be assigned to all newly created orders. This status is displayed in the back-office.
   * **Enable Order PDF Download Storefront** — When enabled, customers can download a PDF version of the order from the storefront order pages. The PDF is generated using the most up-to-date order data at the time of download.

   ![Illustration of the Order Download Button in the storefront](user/img/system/config_commerce/order/order-pdf.png)
   * **Generate PDF When Order is Created** — When this option is enabled, a PDF is generated after an order is placed. To include the PDF in the email, navigate to **System > Emails > Templates** in the back-office menu, open the edit page of the Order Confirmation Email template, and select Order Default PDF Template in the [Attachments field](../../../emails/email-templates.md#email-templates-attachments).

   ![Screenshot of the back-office Email Templates edit page showing the Order Confirmation template. The Attachments field is highlighted, with the Order Default PDF Template selected to include the PDF in confirmation emails.](user/img/system/config_commerce/order/order-pdf-template-attachment.png)

   #### NOTE
   Order PDF functionality is available as of OroCommerce version 6.1.6.
4. Click **Save Settings**.

**Related Topic**

* [Orders](../../../../sales/orders/index.md#user-guide-sales-orders)

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
