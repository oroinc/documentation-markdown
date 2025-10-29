<a id="user-guide-customer-groups"></a>

# Manage Customer Groups in the Back-Office

#### HINT
This section is part of the [Customer Management](../../../concept-guides/customers-sales/customers/index.md#concept-guide-customers) topic that provides a general understanding of accounts, contacts, customers and customer hierarchy available in Oro applications.

In the Customer Group section, you can organize customers into groups and share the price lists, payment and tax-related settings between several customers.

On a customer group details page, you can:

* <i class="fas fa-cog" aria-hidden="true"></i> **Edit Storefront Menu**
* <i class="fas fa-cog" aria-hidden="true"></i> **Configure** customer group settings.
* <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** customer group details.
* ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** existing customer groups.
* **Add a note**
* **Create a new customer**. Alternatively, use a quick action button under the **Customers** menu to create a new customer directly from the customer group page. The form for data input can be displayed in a new browser tab, a popup dialog window, or replace the current page, [depending on its system configuration](../../system/configuration/system/general-setup/display.md#doc-configuration-display-settings-quick-actions).

![Displaying the quick action buttons on the customer group view page](user/img/customers/customer_groups/quick-buttons-customer-group.png)

<a id="user-guide-customer-groups-create"></a>

## Create a Customer Group

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-customer-groups" target="_blank">how to create customer groups in OroCommerce</a>, or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/DbyVljBIHbA" frameborder="0" allowfullscreen></iframe>

To create a new customer group:

1. Navigate to **Customers > Customer Groups** in the main menu.
2. Click **Create Customer Group**.
3. Fill in the customer **Name**.
4. Select **Tax Code** that will label the customer group taxation schema.
5. In the **Additional** section, select a Payment term to be used as a payment option available to the customer users during the checkout.
6. In the **Customers** section, check the customers to add them to the customer group.
7. In the **Price Lists** section, add the price lists and configure the fallback option, as described in the [Price List Management for a Customer Group](#user-guide-customers-customer-groups-pricelist) section.
8. Click **Save** in the top right corner.

<a id="user-guide-customers-customer-groups-pricelist"></a>

## Manage Price Lists for a Customer Group

To configure the price list priority and controlled merge for the customer group:

1. Navigate to **Customers > Customer Groups** in the main menu.
2. Find the necessary customer group in the list, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu in the line and click  <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing the customer group details.
3. In the **Price Lists** section, you can build an aggregated price list for every website you have configured in OroCommerce. Use tabs to switch between the websites, e.g., Default, US, Australia, etc. in the example below.
   ![Choose a price list for the selected website](user/img/customers/customer_groups/CustomerGroupsPrices.png)

   To form an aggregated price list:
   > 1. Set up the fallback option to provide the price source if the price is not available in the directly configured price lists.
   > 2. Select the price list to enable it for the customer group.

   >    #### NOTE
   >    You can add more than one price list:
   >    * Click **+ Add Price List**.
   >    * Select the additional price list from the list.
   >    * Set the numeric priority. OroCommerce searches for the product price in the higher priority price lists first.
   >    * Enable price lists merge, if necessary. When the merge is enabled, the unit prices may be merged from the lower priority price lists, when they are missing in the higher priority ones.
4. Click **Save** once you are happy with the price list set up.

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

* [Configure Price List per Customer Group](customer-group-price-lists.md)
* [Add All Products Page to Storefront Menus per Customer Group](customer-group-all-products-menus.md)
* [Customize Storefront Menus per Customer Group](customer-group-frontend-menus.md)
* [Configure Settings per Customer Group](customer-group-configuration/index.md)
