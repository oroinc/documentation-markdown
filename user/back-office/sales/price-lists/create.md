<a id="user-guide-pricing-create-pricelist"></a>

# Create a Price List

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/configuring-pricelists" target="_blank">how to configure price lists for customers and customer groups in OroCommerce</a>, or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/KYR1M6gykio" frameborder="0" allowfullscreen></iframe>

To create a new price list:

1. Navigate to **Sales > Price Lists** using the main menu.
   ![The list of all price lists available in the system](user/img/sales/pricelist/PriceLists.png)
2. Click **Create Price List**. The following page opens:
   ![The create price list page](user/img/sales/pricelist/PriceListsCreate.png)
3. In the **General** section, provide the following information:
   1. **Name** — Type in the price list name.
   2. **Currencies** — Select one or more currencies you would like to enable for the prices in the price list.

   #### NOTE
   You should provide the price in every currency explicitly. There is no automatic conversion.

   1. **Active** — Set the option to enable the price list. Keep the price list inactive while drafting the prices. Deactivate the price list to temporarily disable the prices it contains.
   2. **Schedule** — Add a timetable for price list activation and deactivation.

      Click *Choose a date* to open a calendar and pick the date.
      ![Scheduling a date to activate the price list](user/img/sales/pricelist/PriceListsCreate_general_schedule.png)

      Click *time* and select the activation or deactivation time from the list. Alternatively, type it in and press **Enter**.
      ![Scheduling time to activate the price list](user/img/sales/pricelist/PriceListsCreate_general_schedule_time.png)

      Click **+ Add** below the timetable to add another time slot. Add as many slots as you need.
4. In the **Product Assignment** section, enter criteria to filter the products and add them to the price list. See [Automated Rule-Based Price Management](auto.md#user-guide-pricing-price-list-auto) for more information.

   #### NOTE
   Optionally, in addition to rule-based product assignment, you can add a product price to the price list manually in one of the following ways:
   * While editing a product (in the **Product Prices** section).
     ![Adding the prices for the medical tag product to the Default PL manually when editing the product details](user/img/sales/pricelist/prices_for_product.png)
   * Click **+ Add Product Price** when viewing the price list details.
     ![Adding product price in the popup dialog that opens when clicking the Add Product Price button](user/img/sales/pricelist/prices_for_price_list.png)

   You can override the existing rule-based price. A manual entry has a higher priority.
5. In the **Price Calculation Rules** section, specify rules for price calculation based on the price attributes (e.g., MSRP) and other product details. You may use conditions to apply the rule to the subset or the filtered products. See [Automated Rule-Based Price Management](auto.md#user-guide-pricing-price-list-auto) for more information.
6. Click **Save**.
