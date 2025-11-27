# Create an Order

<!-- begin -->

## Create an Order from Scratch

#### HINT
See a short demo on <a href="https://academy.oroinc.com/media-library/create-new-order#play=ztwuz7NX1Y4" target="_blank">how to create a new order from scratch</a> or keep reading for step-by-step guidance.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ztwuz7NX1Y4" frameborder="0" allowfullscreen></iframe>

To create a new order from the back-office:

1. Navigate to **Sales > Orders** in the main menu.
2. Click **Create Order** at the top right of the page.
3. In the **General** section, fill in the following fields:
   1. **Owner**: The owner is prepopulated with the user creating the order, but this value can be changed to another user of the system by clicking <i class="fa fa-bars fa-lg" aria-hidden="true"></i> and selecting a user from the list.
   2. **Customer**: Use the drop-down to select a customer. Click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to load the list of customers to choose from.  If this is a new customer, click the plus button to open a new customer dialog.
   3. **Customer User**: Select a customer user, if necessary. This list will be populated with customer users associated with the customer. If this is a new customer user, click **+** to open a new customer dialog.
   4. **Website**: Select the website from which the order will be created.

   ![The general section of the order details page](user/img/sales/orders/orders_create_general.png)
4. In the **Line Items** section, provide the following information:
   1. **Product**: Add products to the order by clicking **+Add Product**. Use the drop-down to select a product. Alternatively, begin typing in the name of the product to narrow down your search. To see a list of all the products, click <i class="fa fa-bars fa-lg" aria-hidden="true"></i>.
   2. **Quantity**: Enter product quantity.
   3. **Warehouse**: Choose a warehouse from the drop-down, or click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to see a list of all warehouses.
   4. **Price**: Enter the price for the product, or click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to select the price from the list.
   5. **Ship by**: If required, choose a date by which the order must be shipped at the customer’s request.
   6. **Add Notes**: Click the *add notes* link if you would like to add a note about the item.
   7. **Taxes**: View taxes calculated for the product(s) (if configured).

   #### NOTE
   To add additional products to the order, click **+Add Product**. To remove a product, click <i class="fa fa-times fa-lg" aria-hidden="true"></i>.

   ![The Line Items section of the order details page](user/img/sales/orders/orders_create_lineitems.png)
5. In the **Billing Address** section, fill in the billing address details when you are done adding products. Use the drop-down list to select an existing billing address, or select **Enter Other Address** to add a new one.
6. In the **Shipping Address** section, fill in the shipping address details. Use the drop-down list to select an existing shipping address, or select **Enter Other Address** to add a new one.
7. In the **Shipping Information** section, provide information for the following:
   1. **Shipping Method**: Click **Calculate Shipping** to display any shipping options.
   2. **Shipping Options**:  Use the radio button to select a shipping option among the preliminary configured shipping rules.
   3. **Overridden Shipping Cost Amount**: If required, override the shipping cost by adding your own value.

   ![The shipping options are displayed after clicking the Calculate Shipping button.](user/img/sales/orders/orders_create_shippinginfo2.png)
8. In the **Additional** section, enter additional details, if required (e.g., the PO number, the Do Not Ship Later Than date, the payment term, and the warehouse to ship the items from), and add notes for the customer.
9. In the **Order Totals** section, review the final amount.
10. To save the order, click **Save** on the top right of the page.

#### HINT
By default, an order has [internal status](statuses.md#doc-orders-statuses-internal) *Open* upon creation. If another status is required for new orders, an administrator must adjust the [order creation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).

<!-- finish -->
<!-- begin -->

## Create an Order from a Shopping List

Any time a customer creates a new shopping list, it can be accessed in the back-office. This is helpful if a customer needs assistance finding particular items or creating an order.

#### HINT
See a short demo on <a href="https://academy.oroinc.com/media-library/create-order-shopping-list#play=w7NXMifQZnI" target="_blank">creating orders from the shopping list</a> or keep reading for step-by-step guidance.

<iframe width="560" height="315" src="https://www.youtube.com/embed/w7NXMifQZnI" frameborder="0" allowfullscreen></iframe>

To create an order from a shopping list:

1. Navigate to **Sales > Shopping lists** in the main menu.
2. Open the selected shopping list from the grid.
3. Click **Create Order** in the top right corner of the page.
   ![Click the Create Order button on the top right](user/img/sales/orders/CreateOrderFormSL.png)
4. The Create Order form opens, prepopulated with the information from the shopping list:

   Amend or add new details to the order, as described in [the Create an Order from Scratch](#user-guide-sales-orders-create) topic.
   ![The Create Order form is prepopulated with the information from the shopping list](user/img/sales/orders/orders_create_fromshoppinglist1.png)

   #### WARNING
   When you modify the order content, order totals and shipping costs may change. Please, review the shipping method selection before saving the order to make sure that the shipping cost is acceptable.
5. Click **Save**.
   ![The new order just created](user/img/sales/orders/orders_create_fromshoppinglist2.png)

#### HINT
By default, an order has [internal status](statuses.md#doc-orders-statuses-internal) *Open* upon creation. If another status is required for new orders, an administrator must adjust the [order creation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).

<!-- finish -->
<!-- begin -->

## Create an Order from an RFQ

To create an order based on a request for a quote (RFQ):

1. Navigate to **Sales > Requests for Quote** in the main menu.
2. Open the selected RFQ from the grid.
3. Click **Create Order** in the top right corner of the RFQ page.
   ![Click Create Order on the top right](user/img/sales/orders/CreateOrderFromRFQ.png)

The Create Order form opens prepopulated with the information from the RFQ:

1. Amend or add new details to the order, as described in [the Create an Order from Scratch topic](#user-guide-sales-orders-create).

   #### WARNING
   When you modify the order content, order totals and shipping costs may change. Please, review the shipping method selection before saving the order to ensure that the shipping cost is acceptable.
2. Click **Save** when you have finished.

The new order is now created.

![The new order that is just created](user/img/sales/orders/orders_create_fromrfq2.png)

#### HINT
By default, an order has [internal status](statuses.md#doc-orders-statuses-internal) *Open* upon creation. If another status is required for new orders, an administrator must adjust the [order creation configuration settings](../../system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders).

<!-- finish -->
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
