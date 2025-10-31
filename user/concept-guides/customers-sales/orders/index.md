<a id="concept-guide-orders"></a>

# Order Management Concept Guide

The B2B e-commerce industry is growing fast, with B2B wholesalers and manufacturers rapidly increasing their online presence. Rapid market growth prompts high customer expectations; customers now want the same quick and smooth buying experiences they have when ordering through most B2C websites. However, the basic order management features offered by B2C websites do not always match the B2B business cycle and, therefore, need to be more sophisticated and advanced to not only meet the B2B customer expectations but exceed them.

One of the essential capabilities of a B2B eCommerce platform is to facilitate a buyer and seller’s detailed interaction effectively. This includes buyers submitting detailed orders, requesting quotes, and asking for specific quantities and prices from the seller, who then needs to be able to answer with detailed proposals.

OroCommerce order management system centralizes all back-office data, supports order approval and quotation, in addition to providing effortless and smooth checkout experience for customers in the storefront. This gives merchants total control of their sales order cycle and enables them to keep real-time track of orders, inventory, customers, fulfillment, create order-based [reports](../../../back-office/reports-segments/reports/custom-reports.md#user-guide-business-intelligence-reports-use-custom-reports) for marketing purposes, and much more.

In this concept guide, we are going to explore how OroCommerce facilitates both sides of this relationship through the storefront and back-office.

#### NOTE
Before you proceed, you may want to check out short demos from our media library:

* <a href="https://youtu.be/0c9L_urjgng" target="_blank">Set Up Your Website Storefront – Buyer’s Perspective</a>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/0c9L_urjgng" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
* <a href="https://www.youtube.com/watch?v=9O4p1vpxPSI" target="_blank">Exploring Storefront Possibilities as a Company Administrator</a>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/9O4p1vpxPSI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Order-to-Cash Lifecycle

Any order to cash cycle starts with customers in the OroCommerce storefront. They browse the website, decide on the items to buy, check if they can negotiate the given price and create a request for a quote, or build a shopping list straight away and place a new order. All this information on customer activity in the storefront (i.e., shopping lists, orders, RFQs, and quotes) is synced in real-time to the OroCommerce back-office, where it is processed by assigned sales representatives or managers.

Sales reps can not only view buyer order-related activities but also assist in fulfilling the orders for their buyers. It means that a customer’s assigned sales rep can create orders for their customer from scratch or from their existing shopping list, add discounts to orders, track order shipping, capture payments, and view customer payment history.

Once a customer or their assigned sales rep place an order, OroCommerce immediately updates the [inventory](../../../back-office/inventory/index.md#user-guide-inventory) in the [warehouse(s)](../../../back-office/inventory/create.md#user-guide-inventory-warehouse-create) and synchronizes product quantities. All items in orders are linked to the products’ respective warehouses, which is extremely helpful, especially if the business has more than one warehouse to store their goods (applicable to OroCommerce Enterprise Edition).

#### HINT
OroCommerce Community Edition comes with one [warehouse](../../../back-office/inventory/create.md#user-guide-inventory-warehouse-create) out-of-the-box. Creating multiple warehouses is an Enterprise edition feature.

![Order management flow](user/img/concept-guides/orders/front-flow.png)

### Creation

Orders can be placed both by customers through the storefront (SF), and by their sales reps through the back-office (BO).
In the storefront, an order starts from a shopping list.

#### Shopping Lists

Buyers in B2B tend to work on numerous and varied projects that need different products for different business units within the organization, at the same time. It means that there is often a necessity to have more than one shopping cart for different needs. OroCommerce’s shopping lists are enhanced B2C shopping carts explicitly built for B2B interactions and enable buyers to work with multiple shopping lists at the same time, when necessary.

#### HINT
OroCommerce enables sellers to control how many shopping lists to make available. For some businesses, setting up several shopping lists is not essential, and they can absolutely work with one. One of the common use cases is when a seller configures the website to have one shopping list for unsigned-in buyers. Once they sign in, they get access to the multiple shopping lists functionality.

![image](user/img/concept-guides/orders/un-signed-in.png)

OroCommerce’s shopping lists provide you with a multitude of possibilities that include:

* Adding items to multiple shopping lists simultaneously
* Requesting quotes from a shopping list
* Submitting orders from a shopping list
* Duplicating shopping lists
* Moving all or selected items to a new or existing shopping list using mass actions.

With OroCommerce, online merchants do not need to choose between guest checkouts and customer accounts. You can enable both to ensure a quality shopping experience. Enabling [guest shopping lists for the storefront](../../../back-office/system/configuration/commerce/sales/global-shopping-list.md#configuration-shopping-list), you do not disrupt the checkout process, which is especially important for first-time customers. Unlike registered customers, [guest users](../../administration/guests/index.md#sys-conf-commerce-guest) are only limited to one shopping list, but it should be enough for occasional buyers. It is also a good incentive for a guest user to register an account with an OroCommerce webstore to get access to their customer [account](../../../storefront/account/index.md#my-account) and multiple shopping lists.

#### HINT
Check out a Commerce Storefront guide on [shopping lists for unregistered users](../../../storefront/account/shopping-lists/guests.md#frontstore-guide-shopping-lists-guest), and a Concept Guide on [guest functions](../../administration/guests/index.md#sys-conf-commerce-guest).

Registered customers have their dedicated customer account where the RFQ, quotes, and order history are kept. Registered customers also have the advantage of being able to [duplicate their existing shopping lists](../../../storefront/account/shopping-lists/registered.md#frontstore-guide-shopping-lists-registered) and [reorder items](../../../storefront/orders/reorder.md#frontstore-guide-orders-reorder) from previously placed orders.

#### HINT
Check out a Commerce Storefront guide on [shopping lists for registered users](../../../storefront/account/shopping-lists/registered.md#frontstore-guide-shopping-lists-registered).

Information from all existing shopping lists in the storefront is automatically synced to the OroCommerce [back-office](../../../back-office/sales/shopping-lists/index.md#user-guide-sales-shopping-lists) and can be seen by the sales rep. Should you require help from your sales representative, they can assist you with the order, add/remove line items from it, as well as successfully create an order for you.

#### Quick Order Form

In addition to creating orders from shopping lists, buyers can use a [quick order form](../../../storefront/quick-order-form.md#frontstore-guide-orders-quick-order) when they have large orders, need to submit an order quickly, and have all necessary information at hand.

![image](user/img/storefront/orders/QuickOrderFormSKU.png)

Both registered users and guests can speed up the ordering process by copying and pasting the exact SKUs they need or by uploading them in a .csv, .xls, or .odf file. Once the required products are selected, buyers can instantly request a quote, create an order, or add the items to shopping lists.

With the Quick Order form, buyers can also view item availability as they order. When customers enter an item name or SKU on the Quick Order form, they instantly see if the product is available. Out of stock products are indicated by zero amounts in the price column. This means buyers know right away the stock status of products and can easily remove unavailable goods before submitting their order.

#### Orders

Sales reps can create orders on behalf of the customer in multiple ways in their OroCommerce back-office:

* [A new order created for customers in the back-office](../../../back-office/sales/orders/create.md#user-guide-sales-orders-create)

  While many customers use the online store to create orders, they can also come from other avenues such as phone calls, emails, contact us requests, or other sales channels. An Oro application makes it easy to create an order for customers in the back-office. When creating or editing an order, you can add new customers or new customer users on the go, configure shipping options, add discounts, and more.
  ![image](user/img/sales/orders/orders_create_general.png)
* [An order converted from a customer RFQ](../../../back-office/sales/orders/create.md#user-guide-sales-orders-create-from-rfq)

  Organizations issue [RFQs](../../../back-office/sales/rfq/index.md#user-guide-sales-requests-for-quote) when they are looking to receive competitive offers from different merchants for the items or services that they want to purchase. In an RFQ, customers ask vendors to provide the prices and delivery times for the item quantities that they specify, inquire whether there are any extra charges, such as shipping costs, or any discounts for big orders or early payment of the merchant’s invoice. When customers and merchants agree on the terms of the sale, sales reps can convert a customer RFQ into an order from their OroCommerce back-office.
  ![image](user/img/sales/orders/CreateOrderFromRFQ.png)

  #### HINT
  If a sales rep is talking on the phone to a customer who wants to get pricing or information on an order, a sales rep can build a [quote](../../../back-office/sales/quotes/create/create-from-rfq.md#quote-create-from-rfq) with all the necessary information and pricing from the customer RFQ, and then send it to the customer for consideration or approval.

  The difference between an RFQ and a quote is that an RFQ is submitted by buyers who are looking to get better pricing than is currently listed on the website. RFQs are submitted through the storefront and never created in the back-office, while Quotes can be created in response to a customer RFQ.

  RFQs have two workflows in place for buyer and sales rep communication: [RFQ Management Flow](../../../back-office/system/workflows/system-workflows/rfq-backoffice.md#system-workflows-rfq-backoffice-workflow) for back-office processes and [RFQ Submission Flow](../../../back-office/system/workflows/system-workflows/rfq-frontoffice.md#system-workflows-rfq-frontoffice-workflow) for the storefront ones. These workflows control the interactions between the storefront and the back-office customers and need to be activated for smooth RFQ submission and processing experience. When both RFQ workflows are inactive, customers in the storefront can still submit RFQs, sales managers can see and create quotes and orders from them, but no [steps or transitions](../../../back-office/system/workflows/steps-transitions.md#user-guide-system-workflow-management-steps-transitions) are available to control the interactions between the storefront and the back-office.

> ![image](user/img/system/workflows/rfq/backoffice/rfq_management_flow_2.png)
* [An order converted from a shopping list](../../../back-office/sales/orders/create.md#user-guide-sales-orders-create-from-shopping-lists)

  Any time a customer creates a new shopping list in the OroCommerce storefront, it can be accessed in the back-office. This way, when a customer needs assistance finding particular items, or with creating an order, their sales rep can help them through their OroCommerce back-office.
  ![image](user/img/sales/orders/CreateOrderFormSL.png)
* **Orders imported from an ERP**

  With minor dev assistance, OroCommerce provides the possibility to import orders from a third-party application, such an external ERP. You can also import old or archived orders processed before moving from your old platform to OroCommerce, and display them to customers in their OroCommerce storefront account.

#### Reorder

Reorder based on past purchases saves time and eliminates the effort required to search for products again.
Registered buyers can reorder any of the previously purchased products in one click through the [Order History](../../../storefront/account/order-history.md#my-account-order-history) section of your storefront customer account.
Once they click **Reorder**, OroCommerce copies all of the original order details and triggers a new checkout. At the checkout page, customers can easily edit their personal information, where necessary.

![image](user/img/storefront/orders/reorder_2.png)

### Processing

#### Order Details

Sales reps can see all order operation from their OroCommerce back-office, such as internal order statuses, shipping methods and dates, payment methods, terms and statuses, order totals, and more.
If an order is created from an RFQ, quote, or another order, sales reps can access the corresponding record via a link from the **Source Document** field. If the order is created from scratch in the back-office or the quick order form in the storefront, this field remains blank.

As OroCommerce Enterprise Edition supports multiple [warehouses](../../../back-office/inventory/create.md#user-guide-inventory-warehouse-create), orders in this application edition show information on the warehouse that the goods are shipped from.

![image](user/img/sales/orders/order_details_general.png)

#### Shipping Tracking

When a customer user submits an order, they provide the shipping address and, optionally, the **Do Not Ship Later Than** date. Based on this information and selected shipping method, buyers can see the shipping cost estimate. Once a sales rep adds the shipping service and a tracking number to the order, the buyer can track the delivery (if this option is provided by the shipping company).

#### HINT
Check out a Concept Guide topic  on [Shipping Configuration](../../administration/shipping-configuration/index.md#user-guide-shipping) and all shipping integrations available out-of-the-box.

![image](user/img/sales/orders/ShippingTrackingOrders.png)

#### Discounts

You can view discounts applied to a specific order under the dedicated Promotions and Discounts section on the order page. This section is divided into All Promotions and All Special Discounts. Within All Promotions, you can view promotions and coupon codes. Within All Special Discounts, you can view special discounts added manually. When items in the order qualify for multiple discounts, several promotions or coupon codes can be added to it. The only limitation of this capability is that you cannot use two coupon codes for one order if they are part of the same promotion.

#### HINT
Check out a [Manage Discounts in Orders](../../../back-office/marketing/promotions/promotions/manage-discounts-in-orders.md#user-guide-sales-orders-promotions) topic for the steps on adding and managing discounts in orders, and a concept guide on [Promotion Management](../../catalog-promotions/promotions/index.md#concept-guides-promotion-management).

![image](user/img/marketing/promotions/PromotionsInOrdersNew.png)

#### HINT
There are a number of order-related configuration options that you can use to manage orders in the application, for example:

* **Automatic Order Cancellation**

  You can set all orders with selected internal statuses to be automatically canceled past their **Do Not Ship Later Than** date. See the [Order Automation](../../../back-office/system/configuration/commerce/orders/global-order-automation.md#configuration-commerce-orders) topic for configuration steps.
* **Backorders**

  #### NOTE
  The feature is available for the Enterprise edition applications.

  You can let buyers order products in the quantities that are not currently available in the warehouses. The remaining portion of the order will be sustained until the product gets back in stock. See [Product Inventory Options](../../../back-office/system/configuration/commerce/inventory/product-options.md#configuration-guide-commerce-configuration-inventory-product-options) for configuration steps.

Please see the [Commerce Configuration topic](../../../back-office/system/configuration/commerce/index.md#configuration-guide-commerce-configuration) to find more useful order and inventory related configuration options.

### Payment Capture and History

OroCommerce supports integration with many payment services, and payment history is always displayed on every order details page. Payment history displays the payment method selected to pay for the  order, the amount charged or to be charged, and the current payment status.

A payment status shows whether the order is already paid in full, the payment for the order is authorized, the transaction has been successfully processed, etc.

Depending on the [payment method](../../../back-office/system/integrations/payment-integration/index.md#sys-integrations-manage-integrations-payment-methods) enabled for the storefront and used by the buyer, payments can be validated and captured in various ways.

For instance, when the order is paid for by using a credit or a debit card, the payment status depends on the **payment action** selected for the credit/debit card payment method when configuring a [payment integration](../../../back-office/system/integrations/payment-integration/index.md#sys-integrations-manage-integrations-payment-methods). If such payment action is set to **pre-authorization** or **final authorization**, the order payment status will stay in the **payment authorized** status until the sales manager manually captures payment (i.e., clicks **capture**) in the OroCommerce back-office to complete the transaction. When the payment is captured, the payment status changes to **paid in full**.

#### NOTE
Payment Status is based on the payment transaction status and is not linked to [the status of an actual order](../../../back-office/sales/orders/statuses.md#doc-orders-statuses-internal) (i.e., open, shipped, archived, etc.) in any way.

There are several types of payment transactions that can be displayed on the order page, for example:

* Authorize
* Charge
* Validate
* Capture
* Purchase

![Capturing payment](user/img/concept-guides/orders/payment-capture.png)

## Order-Based Reports

Analytics and reporting show you precisely what is going on in your business, which makes them crucial to any online retailer. Extracting and examining data correctly enables them to make well-informed decisions around a number of things, like relevant product assortment and performance, stock ordering, promotions, and so on. OroCommerce provides you with an out-of-the-box reporting engine to help generate the right reports for your online store using the data from orders and order line items.

As an illustration, we are going to generate a sales per product report to see how many times products have been purchased. This kind of report helps identify the best (and worst) selling products so that you can determine a suitable plan of action. If a product is selling well, for example, you could consider ordering more of it, and if a product is not in demand, then you would want to know sooner rather than later and run promotions before the season ends.

To create this report, we need to extract information from the *Order Line Item* entity, as we are going to calculate how many products have been ordered. For this, we need to add at least 3 columns to the new custom report: product name, product SKU, and product SKU with function *count*.

These need to be grouped by their values, i.e., product name and product SKU. Additionally, you can add any field conditions, such as the time period you are collecting the data from.

![An example of a product performance report](user/img/concept-guides/orders/product-performance-report.png)

The generated report shows the products’ sku and name and the number of times these products have been purchased. You can export the product performance report grid into a .cvs or .xlsx file, if necessary.

![Product performance report grid](user/img/concept-guides/orders/product-performance-report-grid.png)

#### HINT
Check out a User Guide topic on [Reports](../../../back-office/reports-segments/reports/index.md#user-guide-reports) for more information on the available out-of-the-box reports and how to build the custom ones.

#### BUSINESS TIP
## Business Tip

Do you want to drive <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a> by utilizing advanced technologies? Find relevant examples and best practices in our article.

**Related Sources**

* <a href="https://youtu.be/0c9L_urjgng" target="_blank">Set Up Your Website Storefront – Buyer’s Perspective</a>
* <a href="https://www.youtube.com/watch?v=9O4p1vpxPSI" target="_blank">Exploring Storefront Possibilities as a Company Administrator</a>
* [Orders (User Guide)](../../../back-office/sales/orders/index.md#user-guide-sales-orders) and [Orders (Storefront Guide)](../../../storefront/orders/index.md#frontstore-guide-orders)
* [Shopping Lists (User Guide)](../../../back-office/sales/shopping-lists/index.md#user-guide-sales-shopping-lists) and [Shopping Lists (Storefront Guide)](../../../storefront/account/shopping-lists/index.md#frontstore-guide-shopping-lists)
* [RFQs (User Guide)](../../../back-office/sales/rfq/index.md#user-guide-sales-requests-for-quote) and [RFQs (Storefront Guide)](../../../storefront/account/rfq/index.md#frontstore-guide-rfq)
* [Quotes (User Guide)](../../../back-office/sales/quotes/index.md#user-guide-sales-quotes) and [Quotes (Storefront Guide)](../../../storefront/quotes/index.md#frontstore-guide-quotes)
* [Customer Storefront Account](../../../storefront/account/index.md#my-account)
* [Guest Functions](../../administration/guests/index.md#sys-conf-commerce-guest)
* [Checkout (Storefront Guide)](../../../storefront/checkout/index.md#frontstore-guide-orders-checkout)
