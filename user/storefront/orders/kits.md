<a id="storefront-guide-orders-kits"></a>

# Order a Product Kit in the Storefront

#### NOTE
Product Kits in the back-office are available as of 5.1LTS. Product Kits in the storefront are available as of 5.1.3. By default, the product kits feature is disabled for v.5.1 but you can enable it with developer assistance in the <a href="https://github.com/oroinc/orocommerce/blob/5.1/src/Oro/Bundle/ProductBundle/Resources/config/oro/app.yml" target="_blank">yaml file of the ProductBundle</a>.

You can select which items to add to the product kit you are purchasing in the storefront. The items available as part of the kit are pre-configured in the back-office, but you can select optional items that you would like to purchase.

To configure a product kit in the storefront, click **Configure and Add to Shopping List** on its product page.

![Products available as part of the kit in the storefront](user/img/products/products/kits/kit-front-configure.png)

Here, you can select which of the available items to select as part of the kit, with links to each individual item. If the item does not contain a link, it means that this item is available only as part of the kit, and its visibility is purposefully restricted in the back-office.

Once you have selected the items, click **Add to Shopping List**.

You will be able to see the the price of each item in the kit on the shopping list page before you create an order.

![Kit in a shopping list](user/img/products/products/kits/kit-sl.png)

As you proceed though the checkout, you will continue to see the product kit items and the breakdown of prices per item.

![Kit at payment step of the checkout](user/img/products/products/kits/kit-checkout.png)

This information will be preserved in the details of the order under **Order History** in your storefront account.

![Order containing a product kit in the Order History](user/img/products/products/kits/kit-order-history.png)
