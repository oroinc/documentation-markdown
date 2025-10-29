<a id="bundle-docs-commerce-inventory-bundle"></a>

# OroInventoryBundle

<a href="https://github.com/oroinc/orocommerce/tree/master/src/Oro/Bundle/InventoryBundle" target="_blank">OroInventoryBundle</a> enables the OroCommerce back-office users to specify and manage current inventory levels for every product and set up a threshold for the low inventory status.
The low inventory highlights functionality adds an inventory status message to products when their quantity drops below the value defined in Low Inventory Threshold. Reaching the defined Low Inventory Threshold level triggers a warning message to the buyer in the storefront.

## Configuration

```yaml
product_inventory_options:
    children:
        - oro_inventory.highlight_low_inventory
        - oro_inventory.low_inventory_threshold
```

The oro_inventory.highlight_low_inventory option is used to enable highlighting low inventory for products. Contains the `true` or `false` values.
When the quantity of the product is lower than or equals the value of the `oro_inventory.low_inventory_threshold` option, then the product gets highlighted as low inventory in the storefront.

## Options

Two new options are added for products and categories. These options are `highlightLowInventory` and `lowInventoryThreshold`.
These options help configure options for each category or product individually. By default, these options use the value from the system configuration.
To check the currently configured fallback for product or category, use <a href="https://github.com/oroinc/platform/blob/master/src/Oro/Bundle/EntityBundle/Fallback/EntityFallbackResolver.php" target="_blank">Oro\\Bundle\\EntityBundle\\Fallback\\EntityFallbackResolver</a>.

Example:

```php
$lowInventoryThreshold = $this->entityFallbackResolver->getFallbackValue(
            $product,
            'lowInventoryThreshold'
        );
```

For more details, check the [LowInventoryProvider]() section below.

## Listeners

### ProductDatagridListener

This listener contains the method that adds information about low inventory to the product grid.

#### onPreBuild

This method is called before the grid is built. It adds a new `low_inventory` property to the grid configuration that enables adding the low inventory information to the property and thus, displaying it in the layout when required.

#### onResultAfter

This method is called when we execute query and have data result.
This method uses the logic of [LowInventoryProvider]() . It adds information about the low inventory option for each product in the collection. It also adds a boolean value to `low_inventory` which will then be used in the layout.
The following is an <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/InventoryBundle/Resources/views/layouts/default/imports/oro_product_list_item/low_inventory.html.twig" target="_blank">example of using low_inventory</a> in the layout of the product grid:

```twig
{% block _product_datagrid_row__product_low_inventory_label_widget %}
    {% if (product.low_inventory) %}
        <div class="grid">
            <div class="grid__row">{{ "oro.inventory.low_inventory.label"|trans }}</div>
        </div>
    {% endif %}
{% endblock %}
```

### LowInventoryCheckoutLineItemValidationListener

The <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/InventoryBundle/EventListener/LowInventoryCheckoutLineItemValidationListener.php" target="_blank">Oro\\Bundle\\InventoryBundle\\EventListener\\LowInventoryCheckoutLineItemValidationListener</a> class.
This listener contains a method that checks low inventory for line item products and adds a warning message if a product has low quantity.

#### onLineItemValidate

```php
public function onLineItemValidate(LineItemValidateEvent $event)
```

It validates the product from the line item and adds a warning message if this product has a low inventory level.

## Providers

### LowInventoryProvider

The <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/InventoryBundle/Inventory/LowInventoryProvider.php" target="_blank">Oro\\Bundle\\InventoryBundle\\Inventory\\LowInventoryProvider</a> class.

This class contains a method that helps you quickly get information about low quantity for the current product or product collection.

#### isLowInventoryProduct

```php
public function isLowInventoryProduct(Product $product, ProductUnit $productUnit = null)
```

This method returns information about the low inventory status of the current product.  It returns `true` if the quantity of the product is less than the  `lowInventoryThreshold` option.  It returns `false` if the quantity of the product is greater than the `lowInventoryThreshold` option, or if the `highlightLowInventory` is not checked.

#### isLowInventoryCollection

```php
/**
  * Returns low inventory flags for product collection.
  * Will be useful for all product listing (Catalog, Checkout, Shopping list)
  *
  * @param array $data products collection with optional ProductUnit's
  * [
  *     [
  *         'product' => Product entity,
  *         'product_unit' => ProductUnit entity (optional),
  *         'highlight_low_inventory' => bool (optional),
  *         'low_inventory_threshold' => int (optional)
  *     ],
  *     ...
  * ]
  *
  * @return [product id => is low inventory, ...]
  */
 public function isLowInventoryCollection(array $data)
```

It works in the same way as the [isLowInventoryProduct]() method, but has differences in taken up arguments and returned values.
This method takes an argument as an array of the <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Entity/Product.php" target="_blank">Product entity</a> and <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/ProductBundle/Entity/ProductUnit.php" target="_blank">ProductUnit entity</a> entities and returns an array of product ids with a boolean result.
`true` is returned if the quantity of the product is less than the `lowInventoryThreshold` option. `false` is returned if the quantity of the product is greater than the `lowInventoryThreshold` option, or if `highlightLowInventory` is not checked.

## Twig

To to check low inventory for a specific product in Twig templates, the `oro_is_low_inventory_product` Twig function
is used. The following example illustrates how to use this function/how this function is used:

```twig
{% if (oro_is_low_inventory_product(mainProduct)) %}
        <div class="product-low-inventory">{{ "oro.inventory.low_inventory.label"|trans }}</div>
{% endif %}
```

## Validators

### LowInventoryCheckoutLineItemValidator

The <a href="https://github.com/oroinc/orocommerce/blob/master/src/Oro/Bundle/InventoryBundle/Validator/LowInventoryCheckoutLineItemValidator.php" target="_blank">Oro\\Bundle\\InventoryBundle\\Validator\\LowInventoryCheckoutLineItemValidator</a> class.
This class contains a method that returns a message if a product has low quantity.

#### getLowInventoryMessage

```php
public function getLowInventoryMessage(LineItem $lineItem)
```

When a product is marked as low inventory, the method returns a string message. Otherwise, it will return `false`.
This method uses the logic from [LowInventoryProvider]().

<!-- Frontend -->
