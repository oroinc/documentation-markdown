<a id="bundle-docs-commerce-order-bundle-previously-purchased-products"></a>

# Previously Purchased Products

The Previously Purchased Products functionality adds the previously purchased products grid to the customer pages under Account >  Previously Purchased on the frontend. By default, previously purchased products are disabled. To enable this functionality, navigate to **System > Configuration > Commerce > Orders > Purchase History > Enabled Purchase History** in the admin panel.

<a id="previously-purchased-products-config"></a>

## Configuration

Here is an example of the system config section.

```yaml
purchase_history:
    children:
         purchase_history:
             children:
                 - oro_order.enable_purchase_history
                 - oro_order.order_previously_purchased_period
```

The `oro_order.enable_purchase_history` option turns the feature on or off.
The `oro_order.order_previously_purchased_period` option stores the number of days that the purchase history should cover. The products listed as previously purchased are filtered using this timeframe and are displayed in the <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Resources/config/oro/datagrids.yml#L751" target="_blank">previously purchased products grid</a>.

For more information about system_config.yml, please see the relevant [system configuration documentation](../../../backend/system-configuration/index.md#backend-system-configuration).

<a id="previously-purchased-products-website-search-index"></a>

## Website Search Index

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/EventListener/WebsiteSearchProductIndexerListener.php" target="_blank">WebsiteSearchProductIndexerListener</a>. This listener contains methods which are called when reindex process is running.

### onWebsiteSearchIndex

```php
public function onWebsiteSearchIndex(IndexEntityEvent $event)
```

This method is triggered when search reindex process starts running. For example, we can start the reindex process with the `oro:website-search:reindex` command.
This method adds new columns to the records with the oro_product_WEBSITE_ID index and based on order created_at, customer_user_id, and product_id.

### Index Field

<a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Resources/config/oro/website_search.yml" target="_blank">website_search.yml</a>

```yaml
Oro\Bundle\ProductBundle\Entity\Product:
    alias: oro_product_WEBSITE_ID
    fields:
      -
        name: ordered_at_by_CUSTOMER_USER_ID
        type: datetime
```

The index field which stores information about the date of the last purchase of the product.

This field is used to select a query in the grid config for select, filter and sort data. For more information, please see <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Resources/config/oro/datagrids.yml#L75" target="_blank">datagrids.yml</a>.

```yaml
query:
    select:
        - datetime.ordered_at_by_CUSTOMER_USER_ID as recency
    where:
        and:
            - datetime.ordered_at_by_CUSTOMER_USER_ID >= @oro_order.previously_purchased.configuration->getPreviouslyPurchasedStartDateString()
```

<a id="previously-purchased-products-reindex-listeners"></a>

### Reindex Listeners

<a id="previously-purchased-products-reindex-product-line-item-listener"></a>

**ReindexProductLineItemListener**

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/EventListener/ORM/ReindexProductLineItemListener.php" target="_blank">ReindexProductLineItemListener</a>.

This listener contains methods which are called when the <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Entity/OrderLineItem.php" target="_blank">OrderLineItem</a> entity is changed, and if all conditions are correct, a message is sent to the message queue to reindex product data.

**reindexProductOnLineItemCreateOrDelete**

```php
public function reindexProductOnLineItemCreateOrDelete(OrderLineItem $lineItem, LifecycleEventArgs $args)
```

This method is triggered when we create or delete an order line item. Once the order line item is created or deleted, a message is sent to the message queue informing that reindex for a product entity is required. However, if the order has unsuitable status, or the feature has been disabled, the message for reindex is not sent.

**reindexProductOnLineItemUpdate**

```php
public function reindexProductOnLineItemUpdate(OrderLineItem $lineItem, PreUpdateEventArgs $event)
```

This method is triggered when we update the “product” field in the order line item entity, and a message is sent to the message queue that reindex for the product entity is required. However, if the order has unsuitable status, or the feature has been disabled, the message is not sent for reindex.

<a id="previously-purchased-products-reindex-product-order-listener"></a>

**ReindexProductOrderListener**

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/EventListener/ORM/ReindexProductOrderListener.php" target="_blank">ReindexProductOrderListener</a>.

This listener contains methods which are called when the <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Entity/Order.php" target="_blank">Order entity</a> is changed, and if all conditions are correct, a message is sent to the message queue to reindex product data.

**processIndexOnOrderStatusChange**

```php
public function processIndexOnOrderStatusChange(Order $order, PreUpdateEventArgs $event)
```

This method is triggered when order status is changed. But if order status is not applicable, the message for reindex is not sent.

**processIndexOnOrderWebsiteChange**

```php
public function processIndexOnOrderWebsiteChange(Order $order, PreUpdateEventArgs $event)
```

This method is triggered when order website is changed. But if order status is not applicable, the message for reindex is not sent.

**processOrderRemove**

```php
public function processOrderRemove(Order $order)
```

This method is triggered when an order is removed. But if order status is not applicable, the message for reindex process is not sent.

**processIndexOnCustomerUserChange**

```php
public function processIndexOnCustomerUserChange(Order $order, PreUpdateEventArgs $event)
```

This method is triggered when order is updated and the customerUser field is changed. However, if order status is not applicable, the message for reindex process is not sent.

**processIndexOnOrderCreatedAtChange**

```php
public function processIndexOnOrderCreatedAtChange(Order $order, PreUpdateEventArgs $event)
```

This method is triggered when order is updated and the createdAt field is changed. However, if order status is not applicable, the message for reindex process is not sent.

**PreviouslyPurchasedFeatureToggleListener**

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/EventListener/PreviouslyPurchasedFeatureToggleListener.php" target="_blank">PreviouslyPurchasedFeatureToggleListener</a>.

This listener contains methods which are called when we turn the feature on or off from the system config.

**reindexProducts**

```php
public function reindexProducts(ConfigUpdateEvent $event)
```

This method is triggered when we change the enable_purchase_history config setting. Once the setting is changed, a message is sent to reindex products in the global or website scope.

<a id="previously-purchased-products-managers"></a>

## Managers

### ProductReindexManager

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Search/Reindex/ProductReindexManager.php" target="_blank">ProductReindexManager</a>.

This manager contains methods which are used when we need to reindex a product or a collection of products. Use it when you need
to reindex product data.

**reindexProduct**

```php
public function reindexProduct(Product $product, $websiteId = null)
```

This method triggers reindex process for the current product. If the websiteId is not present, this method takes the default website id.

**triggerReindexationRequestEvent**

```php
public function triggerReindexationRequestEvent(array $productIds, $websiteId = null, $isScheduled = true)
```

This method triggers reindex process for a collection of product ids.

<a id="previously-purchased-products-providers"></a>

## Providers

**PreviouslyPurchasedConfigProvider**

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Provider/PreviouslyPurchasedConfigProvider.php" target="_blank">PreviouslyPurchasedConfigProvider</a>.

This provider provides you with the configuration for previously purchased products.

Here is a quick overview of its usage:

**getDaysPeriod**

```php
$this->get('oro_order.previously_purchased.configuration')->getDaysPeriod();
```

Returns the count of days for previously purchased products.

**getPreviouslyPurchasedStartDateString**

```php
$this->get('oro_order.previously_purchased.configuration')->getPreviouslyPurchasedStartDateString()
```

Returns the start date in string format for previously purchased products.

<a id="previously-purchased-products-latest-ordered-products-info-provider"></a>

**LatestOrderedProductsInfoProvider**

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Provider/LatestOrderedProductsInfoProvider.php" target="_blank">LatestOrderedProductsInfoProvider</a>.

This provider is used when we need more information about who and when bought products in the order.

**getLatestOrderedProductsInfo**

```php
/**
 * Returns information about who and when bought those products
 * [
 *      product id => [
 *          'customer_user_id' => customer user who bought,
 *          'created_at'       => order create \DateTime,
 *      ],
 *      ...
 * ]
 *
 * @param array $productIds
 * @param int   $websiteId
 *
 * @return array
 */
public function getLatestOrderedProductsInfo(array $productIds, $websiteId)
```

Returns information about who and when bought the products.

**PreviouslyPurchasedOrderStatusesProvider**

Class <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Provider/PreviouslyPurchasedOrderStatusesProvider.php" target="_blank">PreviouslyPurchasedOrderStatusesProvider</a>.

This service implements <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/OrderBundle/Provider/OrderStatusesProviderInterface.php" target="_blank">OrderStatusesProviderInterface</a> and contains methods which return applicable statuses for the order. For example:

```php
/**
 * @param AbstractEnumValue|null $status
 * @return bool
 */
protected function isAllowedStatus(AbstractEnumValue $status = null)
{
    // statusProvider implements OrderStatusesProviderInterface
    $availableStatuses = $this->statusesProvider->getAvailableStatuses();
    $statusId = $status !== null ? $status->getId() : null;

    return in_array($statusId, $availableStatuses);
}
```

**getAvailableStatuses**

```php
public function getAvailableStatuses()
```

This method returns an array of applicable statuses for an order. It is used in [ReindexProductOrderListener](#previously-purchased-products-reindex-product-order-listener), [ReindexProductLineItemListener](#previously-purchased-products-reindex-product-line-item-listener) and [LatestOrderedProductsInfoProvider](#previously-purchased-products-latest-ordered-products-info-provider).

<!-- Frontend -->
