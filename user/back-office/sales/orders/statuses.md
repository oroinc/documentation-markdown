<a id="doc-orders-statuses-internal"></a>

# View Order Internal Statuses

An internal status is a status visible only in the back-office.

An order can have the following internal statuses:

> * *Open* — The order has been submitted and is being processed. You can [cancel](control.md#doc-orders-actions-cancel), [mark as shipped](control.md#doc-orders-actions-mark-shipped), and [close](control.md#doc-orders-actions-close) an open order.
> * *Canceled* — The order that has been submitted but successively canceled. There are many circumstances in which you may need to cancel the order. For example, if the order has expired, your organization cannot fulfill the order for any reason, or the buyer asked you to do so. An administrator may cancel the submitted order or automatically when its Do Not Ship Later Than date is passed.

>   You can [close a canceled order](control.md#doc-orders-actions-close).

>   #### HINT
>   For orders to be automatically canceled upon expiration, an administrator must enable the corresponding functionality in the [order automation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).
> * *Shipped* — The order is on the way or delivered to the buyer. You can [close a shipped order](control.md#doc-orders-actions-close).
> * *Closed* — The order does not require any further actions: it has been successfully delivered, canceled for some time, etc. You can [archive a closed order](control.md#doc-orders-actions-archive).
> * *Archived* – An old order stored for historical purposes only. No further actions with the order are required (the buyer will not send a return request, etc.).

#### HINT
By default, an order has the internal status *Open* on creation. If another status is required for new orders, an administrator must adjust the [order creation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).
