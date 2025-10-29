<a id="user-guide-sales-shopping-lists"></a>

# Manage Shopping Lists in the Back-Office

[Shopping lists](../../../glossary.md#term-Shopping-List) are similar to shopping carts in most online stores. However, shopping lists have additional features. These include the ability to:

* Manage multiple shopping lists simultaneously.
* Request quotes from a shopping list.
* Submit orders from a shopping list.
* Create as many shopping lists as needed.

Via the back-office, you can access any shopping list created and saved by the customers in the OroCommerce storefront.

#### IMPORTANT
See a short demo on <a href="https://academy.oroinc.com/media-library/create-order-shopping-list#play=w7NXMifQZnI" target="_blank">creating orders from the shopping list</a>.

<iframe width="560" height="315" src="https://www.youtube.com/embed/w7NXMifQZnI" frameborder="0" allowfullscreen></iframe>

## View Shopping List Details

To view a specific shopping list in the back-office:

1. Navigate to **Sales > Shopping Lists** in the main menu.
   ![Shopping lists grid](user/img/sales/shopping_lists/SL_grid.png)
2. Find the required shopping list and click on it to open its details page.
3. In the **General** section, you can find the shopping list ID, the customer user who has created the shopping list, and the comments, if any.
4. In the **Shopping List Line Items** section, you can review the details of line items added to the shopping list (products, quantity, unit) and notes to the line items, if any.
   ![The shopping list details specified in the Shopping List Line Items section](user/img/sales/shopping_lists/ShoppingListsViewPageLineItems.png)

   You can perform the following actions to the items by hovering over the more options menu:
   * <i class="fa fa-eye fa-lg" aria-hidden="true"></i> View complete details of the product that is added to the shopping list.
   * <i class="fa fa-edit fa-lg" aria-hidden="true"></i> Modify details of the product added as a line item to the shopping list.
   * ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) remove the line item from the shopping list.

   #### NOTE
   To handle a significant volume of data, use page switcher, increase *View Per Page*, or use filters to narrow down the list to the information you need.
5. The **Totals** section displays the aggregated amounts, like subtotal, tax, discount, and the total amount due for payment of the items in the shopping list. OroCommerce automatically recalculates these amounts when new items are edited in, added to, or removed from the shopping list.
6. The **Sales Orders** section displays all orders converted from this shopping list. Click a required order to get redirected to the order details page.
   ![The shopping list orders details specified in the Sales Orders section](user/img/sales/shopping_lists/sl_sales_orders.png)
7. The **Marketing Activity** section shows any marketing activity associated with the shopping list.

## Manage Shopping Lists

From the shopping list view page, you can perform the following actions for the shopping list:

![The actions you can perform from the shopping list view page](user/img/sales/shopping_lists/ShoppingListsViewPage.png)

**1. Duplicate List**

> > Click the **Duplicate List** button to create a copy of the shopping list. You can now modify it or convert it into order. The name of the copied list will include the time and date of duplicating the list.
> ![A sample of the duplicated shopping list](user/img/sales/shopping_lists/SLDplicateName.png)

**2. Add line Item**

> Click **Add Line Item** to open a popup dialog that prompts to add details of the new item:

> * *Owner*: Choose a user as the product owner.
> * *Product*: Choose the product from the list, or click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> and select the item from the list of all products.
> * *Quantity*: Enter the number of product units to be purchased.
> * *Unit*: Select whether the product quantity is specified for items, sets, or kilograms. More units may be available depending on your system customization.
> * *Notes*: Enter additional information for the product, if necessary.

> ![Adding a line item via the popup dialog](user/img/sales/shopping_lists/SLAddLineItem.png)

**3. Create Order**

> See [Create an order from the shopping list](../orders/create.md#user-guide-sales-orders-create-from-shopping-lists) for detailed guidance.

#### BUSINESS TIP
## Business Tip

Betting big on the growing digital commerce trend? Discover more about the <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">business to business marketplace</a>, its features, and how you can benefit from it.

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
<!-- Frontend -->
