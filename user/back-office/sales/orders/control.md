# Move an Order Through Its Lifecycle

From the order view page, you can control the order lifecycle, cancel or close orders, mark orders as shipped, and archive the old ones.

<a id="doc-orders-actions-cancel"></a>

## Cancel an Order

#### IMPORTANT
This operation is available only for orders with status *Open*.

There are many circumstances in which you may need to cancel the order. For example, the order has expired, or your organization cannot fulfill the order for any reason, or the buyer asked you to do so.

To cancel an order:

1. In the main menu, navigate to **Sales > Orders**.
2. Choose the order in the list and click it. The order details page opens.
3. Click the **Cancel** button on the top right of the page.

The order [internal status](statuses.md#doc-orders-statuses-internal) becomes *Cancelled*.

#### HINT
The orders can be canceled automatically upon expiration. For this, an administrator must enable the corresponding functionality in the [order automation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).

After the order has been canceled for some time and does not require any further actions, you may wish to [close](#doc-orders-actions-close) it.

<a id="doc-orders-actions-close"></a>

## Close an Order

#### IMPORTANT
This operation is available only for orders with status *Open*, *Cancelled*, and *Shipped*.

After an order has been successfully delivered, has been canceled for some time, etc., and does not require any further actions from any party, you may wish to close it, thus indicating that all your obligations regarding the order are fulfilled.

To close an order:

1. In the main menu, navigate to **Sales > Orders**.
2. Choose the order in the list and click it. The order details page opens.
3. Click the **Close** button on the top right of the page.

The order [internal status](statuses.md#doc-orders-statuses-internal) becomes *Closed*.

After you make sure that no further actions with the order will be required (the buyer is not going to send a return request, etc.), you can [archive](#doc-orders-actions-archive) the closed order. Archived orders are old orders stored for historical purposes only.

<a id="doc-orders-actions-mark-shipped"></a>

## Mark an Order as Shipped

#### IMPORTANT
This operation is available only for orders with status *Open*.

To indicate that the order has been shipped to the customer:

1. In the main menu, navigate to **Sales > Orders**.
2. Choose the order in the list and click it. The order details page opens.
3. Click the **Mark as Shipped** button on the top right of the page.

The order [internal status](statuses.md#doc-orders-statuses-internal) becomes *Shipped*.

After the order is delivered and does not require any further actions, you may wish to [close](#doc-orders-actions-close) it.

<a id="doc-orders-actions-archive"></a>

## Archive an Order

#### IMPORTANT
This operation is available only for orders with status *Closed*.

After you make sure that no further actions with an order are required (the buyer is not going to send a return request, etc.), you can archive the closed order. Archived orders are old orders stored for historical purposes only.

To archive an order:

1. In the main menu, navigate to **Sales > Orders**.
2. Filter the order list by internal status to show only closed orders.
3. Choose the order you want to archive in the filtered list and click it. The order details page opens.
4. Click the **Archive** button on the top right of the page.

The order [internal status](statuses.md#doc-orders-statuses-internal) becomes *Archived*.
