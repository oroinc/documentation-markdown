# Manage Orders

<a id="user-guide-sales-orders-viewlist"></a>

## Manage Orders in the Order Grid

To view the list of existing orders, navigate to **Sales > Orders** in the main menu.

![The list of existing orders](user/img/sales/orders/OrdersGrid.png)

The following information about orders is available:

* **Order Number** — The unique order reference number. It is generated automatically for new orders.
* **PO Number** — Another order reference number. It is usually defined by the buyer and used by the buyer’s side to match the invoice and the received goods with the purchase.
* **Ship by** — The date on which the order expires.
* **Currency** — The currency in which the order is made.
* **Subtotal** — The amount due for items included in the order. Does not include additional costs, taxes, or discounts.
* **Total** — The final amount due for the order. Includes all the additional costs (like shipping costs), taxes or discounts.
* **Customer** — The customer that made the order.
* **Customer User** — The customer user who made an order on behalf of the customer.
* **Internal Status** — The order status is managed only in the back-office. See the [description of internal statuses](statuses.md#doc-orders-statuses-internal).
* **Status** — An external order status displayed in the title next to the internal status and the order number. This status can be used by an external system and is visible when [Enable External Status Management](../../system/configuration/commerce/orders/global-order-status-management.md#sys-commerce-orders-status-management) configuration option is enabled in the system configuration, and status options are created for the order status entity field via [entity management](../../system/entities/index.md#entities-management). When enabled, this external order status will be visible in the Order History grid and on the order view page in the storefront user [account](../../../storefront/account/order-history.md#my-account-order-history). If disabled, Internal Status will be displayed instead. Please be aware that the external order status is managed via the order [REST API](../../../../api/index.md#web-services-api).

![Illustration of external order status on the order view page and on the order status entity field page with sample options.](user/img/sales/orders/external-order-status.png)
* **Owner** — The back-office user responsible for the order.
* **Payment Status** — Whether the order is already paid in full, the payment for the order is authorized, etc.
* **Payment Method** — The payment method selected to pay for the order.
* **Shipping Method** — The shipping method selected for the order delivery.
* **Source Document** — If the order has been created from an RFQ, quote, or another order, this field contains a link to the corresponding record. If the order has been created from scratch (in the back-office) or the quick order form (in the storefront), the field shows ‘N/A’.
* **Discount** — The total of all discounts applied to the order.
* **Created At** — The date and time the order was created.
* **Created By** — The name of the user who created an order on behalf of a customer user, either via the back-office or [customer user impersonation](../../customers/customer-users/index.md#user-guide-customers-customer-user-impersonate) in the storefront.
* **Updated At** — The date and time when the order was last updated.
* **Payment Term** — The terms and conditions for order payment. For more information, see [Payment Terms Integration](../../system/integrations/payment-integration/payment-terms/index.md#sys-integrations-manage-integrations-payment-term).
* **Warehouse** — The warehouse from which the goods are shipped.

#### HINT
To manage the columns displayed within the grid, click <i class="fas fa-cog" aria-hidden="true"></i> on the right of the grid and select the information you wish to be displayed.

To handle the significant volume of data, use the page switcher, increase the ‘view per page’ value, or use <i class="fa fa-filter fa-lg" aria-hidden="true"></i> filters to narrow down the list to the needed information.

<!-- For more information on configuring visible fields, the number of items per page, etc., see the :ref:`Grids <doc-grids>` topic. -->

At the top right, you can see the name of the view. The views are defined by default:

* Open Orders — Shows only orders with the status ‘Open’.
* All Orders — Shows all existing orders regardless of their statuses.

To change the view, click the drop-down next to the view name and select the required view.

![Required view options available in the dropdown next to the view name](user/img/sales/orders/orders_views.png)

You can also create and save new views for future use.

<a id="user-guide-sales-orders-edit"></a>

## Edit Order Details

To edit an order:

1. Navigate to **Sales > Orders** in the main menu.
2. Choose an order in the list, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item, and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details.

   Alternatively, click the order to open its details. On the order details page, click the **Edit** button on the top right.
3. Update the required information. See [Create an Order from Scratch](create.md#user-guide-sales-orders-create) and [Manage Promotions in Orders](../../marketing/promotions/promotions/manage-discounts-in-orders.md#user-guide-sales-orders-promotions) topics for detailed information on the available options.

   If the order contains [product kit(s)](../../products/products/create-kit.md#products-products-create-product-kit), you can add items that qualify for it to the order.
4. Click **Save** on the top right of the page.

<a id="user-guide-sales-orders-reorder"></a>

## Re-Order

If the order does not have sub-orders, it can be re-ordered.

To re-order an existing order:

1. Navigate to **Sales > Orders** in the main menu.
2. Choose an order in the list, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item, and click **Re-order** to start a new order from the existing one.

   Alternatively, click the order to open its details. On the order details page, click the **Re-order** button on the top right.
3. Update the required information. See [Create an Order from Scratch](create.md#user-guide-sales-orders-create) and [Manage Promotions in Orders](../../marketing/promotions/promotions/manage-discounts-in-orders.md#user-guide-sales-orders-promotions) topics for detailed information on the available options.
4. Click **Save** on the top right of the page.

## Schedule a Recurring Order

Back-office users can schedule a [recurring order](../recurring-orders/index.md#user-guide-sales-recurring-orders) based on an existing order.

To schedule a recurring order from the order view page:

1. Navigate to **Sales > Orders** in the main menu.
2. Click the required order to open its details page.
3. Click **Schedule Recurring Order** at the top of the page.
4. When the new page opens, configure the recurring order schedule by selecting the repeat frequency, start date, and optional end date, as well as selecting which line items to include.
5. Click **Save and Close**.

![image](user/img/sales/recurring-orders/new-ro.png)

Alternatively, a recurring order can be scheduled directly from the **Orders** grid. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu for the required order and click **Schedule Recurring Order**.

![image](user/img/sales/recurring-orders/new-ro-grid.png)

Once scheduled, the recurring order is created and managed separately from the original order under **Sales > Recurring Orders** in the back-office menu.

<a id="doc-orders-actions-delete"></a>

## Delete an Order

<a id="doc-orders-actions-delete-fromgrid"></a>

### Delete an Order from the Order Grid

1. In the main menu, navigate to **Sales > Orders**.
2. Select the order you need to delete, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** icon.
3. In the confirmation dialog, click **Yes, Delete**.

<a id="doc-orders-actions-delete-fromviewpage"></a>

### Delete an Order from the Order View Page

1. In the main menu, navigate to **Sales > Orders**. The order list opens.
2. Click the order that you need to delete. The order view page opens.
3. Click **Delete** on the top right.
4. In the confirmation dialog, click **Yes, Delete**.

<a id="doc-orders-actions-delete-multiple"></a>

### Delete Multiple Orders

1. In the main menu, navigate to **Sales > Orders**. The order list opens.
2. Select the checkboxes in front of the orders you need to delete, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the list header, and then click ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete**.

   #### TIP
   To select a bulk of items quickly, click <i class="fa fa-caret-down fa-lg" aria-hidden="true"></i> next to the checkbox at the beginning of the table header and then select one of the following options:
   * *All* — Select all orders.
   * *All Visible* — Select only orders that are visible on the page now.

   To clear the selection, select *None*.
3. In the confirmation dialog, click **Yes, Delete**.

**Related Topics**

* [Configure Recurring Orders Globally](../../system/user-management/organizations/org-configuration/commerce/sales/organization-recurring-orders.md#user-guide-system-configuration-commerce-sales-recurring-orders)
* [Recurring Orders in the Storefront](../../../storefront/account/recurring-orders.md#my-account-recurring-orders)

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
