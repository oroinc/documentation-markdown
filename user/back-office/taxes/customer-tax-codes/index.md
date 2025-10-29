<a id="user-guide-taxes-customer-tax-codes"></a>

# Manage Customer Tax Codes in the Back-Office

<!-- begin -->

#### HINT
This section is part of the [Tax Management](../../../concept-guides/administration/taxes/index.md#concept-guide-taxes) concept guide that provides a general understanding of the tax configuration and management in OroCommerce.

A customer tax code is a label assigned to a customer and indicates the tax obligations and exemptions a customer has. The customer tax obligations are considered when a customer (user) submits an order.

The sections below explain how to manage customer tax codes, using them to label customers and bind customers to dedicated tax rules.

## Create a Customer Tax Code

A customer tax code is a label for a group of customers that indicates the tax obligations and exemptions that a customer has. These tax obligations are considered when a customer submits an order.

To create a new customer tax code:

1. Navigate to **Taxes > Customer Tax Codes** in the main menu.
2. Click **Create Customer Tax Codes**.
3. Fill in **Owner**, **Code**, and **Description** with information about the customer tax code you are creating.
4. Click **Save and Close**.

## Manage Customer Tax Codes

To view all customer tax codes, navigate to **Taxes > Customer Tax Codes** in the main menu.

![The general page of all customer tax codes](user/img/taxes/customer_tax_codes.png)

#### NOTE
To handle a considerable volume of data, use the page switcher, increase *View Per Page*, or use filters to narrow down the list to just the codes you need.

In the customer tax codes list, you will find the information about the code (unique identifier), a detailed description, and the dates when the customer tax code was created and updated.

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> to open its details page, <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to edit, or  ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) to remove the customer tax code.

### View Customer Tax Code Details

To view customer tax code details:

1. Navigate to **Taxes > Customer Tax Codes** in the main menu.
2. Find the line with the necessary customer tax code and click it to open its details.
3. You can perform the following actions with a customer tax code:

> * View Change History — See the log of edits of this customer tax code by clicking the **Change History** link to the top right of the page.
>   ![The log of edits of the selected customer](user/img/taxes/CustomerTaxCodeChangeHistory.png)
> * View details of the customer who is linked to this customer tax code — Click the line with the customer account details.
> * <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** or ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** the selected customer tax code.

>   #### NOTE
>   You can edit the customer details to remove the link to this customer tax code, if necessary.

### Edit Customer Tax Code Details

To edit the customer tax code value and description:

1. Navigate to **Taxes > Customer Tax Codes** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details.
3. Update the **Code** and **Description** with new information about the customer tax code.
4. Click **Save and Close**.

## Link a Tax Code to a Customer or a Customer Group

### Customer

To link a tax code to a customer:

1. Navigate to the necessary customer and open it for editing (e.g., click **Customers > Customers** in the main menu, filter customers to find the one you need, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details).
2. In the **General** section, select the tax code that matches the customer’s tax obligations in the Tax Code list.

![Select the tax code that matches customer's tax obligations](user/img/taxes/link_tax_code_to_customer.png)
1. Click **Save and Close**.

A clickable tax code link is now available in the customer details.

![View the tax code link in the customer details](user/img/taxes/linked_tax_code.png)

### Customer Group

A tax code assigned to a customer group is by default applied to the customers in a group until they have the overriding tax association in their details.

To link a tax code to a customer group:

1. Navigate to the necessary customer group and open it for editing (e.g., click **Customers > Customer Groups** in the main menu, filter customer groups to find the one you need, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click  <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details).
2. In the **General** section, in the Tax Code list, select the tax code that matches the customer group’s tax obligations.
3. Click **Save and Close**.

![View the tax code link in the customer group details](user/img/taxes/linked_tax_code2.png)

A clickable tax code link is now available in the customer and customer group details.

## Link a Customer Tax Code to the Tax Rule

You can edit the association of the customer tax code with the tax when [editing the tax rule details](../tax-rules/index.md#tax-rules-edit) (see the respective topic for more information).

**Related Articles**

* [Taxes](../index.md#user-guide-taxes)
* [Product Tax Codes](../product-tax-codes/index.md#taxes-product-tax-code)
* [Tax Jurisdictions](../tax-jurisdictions/index.md#taxes-tax-jurisdiction)
* [Tax Rates](../taxes/index.md#user-guide-taxes-tax-rates)
* [Tax Rules](../tax-rules/index.md#tax-rules)

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
