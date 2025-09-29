<a id="user-guide-customers"></a>

# Manage Customers in the Back-Office

#### HINT
This section is part of the [Customer Management](../../../concept-guides/customers/index.md#concept-guide-customers) topic that provides the general understanding of accounts, contacts, customers and customer hierarchy available in Oro applications.

[Customers](../../../glossary.md#term-Customer) represent companies who buy products using the storefront. **Customer users** are actual people who act on behalf of companies (i.e. customers) and have a limited set of permissions which depend on their role and function in the customer organization. You can manage customer users and roles in the back-office, or you can delegate this function to the customer who will access user and role management in the storefront.

In the Customer section, you can manage the customers who represent a group of buyers related to the same business organization.

Navigate to **Customers > Customers** in the main menu.

<!-- .. image:: /user/img/customers/customers/Customers.png
.. :alt: The list of all customers available in the system -->

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer to perform the following actions:

* <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** customer details. Alternatively, click on the item to open its details page.
* <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** customer details.
* <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** existing customers.

On the customer details page, you get access to the aggregated information about customer users activities and eCommerce operations, such as requests for quotes, quotes, sales orders, and shopping lists.

<!-- .. image:: /user/img/customers/customers/customers_details.png
.. :alt: The details page of the selected customer -->

You can also quickly get to the [customer organization structure](#user-guide-customers-customers-organize), [an address book](address-book.md#user-guide-getting-started-address-book) with a preview on the map, [customer users](../customer-users/index.md#user-guide-customers-customer-users), [price lists](../customer-groups/index.md#user-guide-customers-customer-groups-pricelist) enabled for the customer, and overview of [requests for quote](../../sales/rfq/index.md#user-guide-sales-requests-for-quote), [sales orders](../../sales/orders/index.md#user-guide-sales-orders), [quotes](../../sales/quotes/index.md#user-guide-sales-quotes) created by and for customer users, and available [shopping lists](../../sales/shopping-lists/index.md#user-guide-sales-shopping-lists). Finally, you can get to a summary of activity from every operation triggered by the customer users.

<a id="user-guide-customers-customers-organize"></a>

## Customer Organization Structure

You can create a hierarchy of business units or customer divisions by providing a parent company when editing the company details.

![Selecting a company for the parent customer](user/img/customers/customers/CustomersCreateParent_cust.png)

Navigate to the parent company page by clicking on the company name next to the Parent Customer.

![Click on the company name next to the parent customer to get to the parent company page](user/img/customers/customers/CustomersViewParent_cust.png)

All the subsidiary departments and divisions are displayed in the Subsidiaries section of the customer’s parent category. From this section, you can reach any child customer’s view page by clicking the <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** icon.

![Subsidiaries section of the customer's parent category](user/img/customers/customers/subsidiaries.png)

* [Create a Customer](create.md)
* [Create an Address](address-book.md)
* [Export Customers](export.md)
* [Import Customers](import.md)
* [Configure Price List per Customer](customer-price-lists.md)
* [Add All Products Page to Frontend Menus per Customer](customer-all-products-menus.md)
* [Customize Frontend Menus per Customer](customer-frontend-menus.md)
* [Configure Product Data Export per Customer](customer-settings.md)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
