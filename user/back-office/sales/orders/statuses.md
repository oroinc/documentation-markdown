<a id="doc-orders-statuses-internal"></a>

# View Order Internal Statuses

An internal status is a status visible only in the back-office.

An order can have the following internal statuses:

> * *Open* — The order has been submitted and is being processed. You can [cancel](control.md#doc-orders-actions-cancel), [mark as shipped](control.md#doc-orders-actions-mark-shipped), and [close](control.md#doc-orders-actions-close) an open order.
> * *Cancelled* — The order that has been submitted but successively canceled. There are many circumstances in which you may need to cancel the order. For example, the order has expired, or your organization cannot fulfill the order for any reasons, or the buyer asked you to do so. The submitted order may be canceled by an administrator or automatically when its ‘do not ship later than’ date is passed.

>   You can [close a canceled order](control.md#doc-orders-actions-close).

>   #### HINT
>   For orders to be automatically canceled upon expiration, an administrator must enable the corresponding functionality in the [order automation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).
> * *Shipped* — The order is on the way or delivered to the buyer. You can [close a shipped order](control.md#doc-orders-actions-close).
> * *Closed* — The order does not require any further actions: has been successfully delivered, or canceled for some time, etc. You can [archive a closed order](control.md#doc-orders-actions-archive).
> * *Archived* – An old order stored for historical purposes only. No further actions with the order are required (the buyer is not going to send a return request, etc.).

#### HINT
By default, an order has internal status *Open* upon creation. If another status is required for new orders, an administrator must adjust the [order creation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).
