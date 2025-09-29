<a id="quote-create-from-scratch"></a>

# Create a Quote From Scratch

#### HINT
This section is part of the [RFQ and Quote Management](../../../../concept-guides/rfq-quotes/index.md#concept-guide-rfq-quotes) topic that provides the general understanding of the RFQ and quote concepts in OroCommerce.

To create a new quote from scratch:

1. Navigate to **Sales > Quotes** in the main menu.
   ![The list of all quotes available in the system](user/img/sales/quotes/Quotes.png)
2. Click **Create Quote**.
   ![The create quote page details](user/img/sales/quotes/create_quote_general.png)

1. In the **General** section:
   1. Select a **Customer** and **Customer User** to create a quote for.
   2. Enter the quote expiration information in the **Valid Until** date and time boxes.
   3. Optionally, enter a **PO Number** for the customer reference.
   4. If necessary, set the **Do Not Ship Later Than** date, to limit the order validity based on the information from the customer.
   5. Select an order fulfilment officer in the **Assigned To** box.
   6. Select the assigned customer user that will receive the order delivery in the **Assigned Customer** box.
   7. Select a **Website** to make this quote visible only on the specified website.
2. In the **Line Items** section:
   ![The details of the Line Items section](user/img/sales/quotes/create_quote_line_items.png)
   1. Add products as quote line items.

      Use Select Product and Free-form entry link to switch between the following product entry modes:

      **Select a Product**: Select the product using search (v) or from the product list (=).
      <!-- image for Select Product mode -->

      **Free-Form Entry**: Type in the SKU and/or Product Name.
      <!-- image for Select Product mode -->
      <!-- image Sample offer. -->
   2. Fill in the offer:
      1. Provide quantity and select a product unit measurement.

      1. Check **or more** to allow the customer to increase the quantity in the order.
      2. Type in the unit price and select a currency.

      To offer alternative quantity and prices, use **+ Add Offer**.
      <!-- image Add Offer -->

      Add notes to the quote line, if necessary: click **Add notes** in the Seller Notes section.
      <!-- image Notes -->

      #### NOTE
      To delete any quote line, click **Delete** on the right of the line item information group.

      <!-- image Delete? -->

   Add more products, if necessary, by clicking **+ Add Products** below the existing product lines.
   <!-- image Add Product -->
3. In the **Shipping Address** section, enter the shipping address, organization name and name of the person the future order should be shipped to.

   #### NOTE
   Keep in mind that the shipping address you enter when creating a quote will be the only option available for the customer on the checkout.
4. In the **Shipping Information** section, configure the recommended shipping options for the customer:
   ![Shipping options under the Shipping Information section of the quote](user/img/sales/quotes/CreateQioteShipping.png)
   1. In the **Shipping Method** list, select the recommended (default) shipping method that will be pre-selected when the customer gets to the shipping configuration on the checkout.

   <!-- .. note:: When none of the methods are selected, the customer can use any of the listed methods. -->
   <!-- .. note:: Once you change the existing settings, the previous configuration will be saved for your information in the previously Selected Shipping Method log above the list of the shipping methods. -->
   <!-- b) If necessary, select the preferred shipping method from the **Default Shipping Method** list. The customer will be able to change the option to any other available shipping method. -->
   1. Optionally, enter the **Overridden Shipping Cost Amount, USD** - a custom shipping cost that will be used instead of the one dynamically generated based on the shipping method selection.
   2. To enforce using only the default Shipping method selected earlier, enable the **Shipping Method Locked** flag. When the shipping method is locked, the buyer does not see any other payment options but the default one.
   3. Tick the **Allow Unlisted Shipping Methods** box to allow using the shipping method that is already selected as a default one, even if it is disabled by the shipping rule configuration.
5. Optionally, select a **Payment Term** as an available payment method.

   #### NOTE
   Be aware that although opportunity relation can be displayed on the quote page, it is not possible to manage it. When there is no opportunity relation available for a quote, inactive **Opportunity** field is displayed. More information on the relationship between opportunities and quotes is available in the relevant [OroCommerce Opportunity Flow](../../opportunities/flows.md#mc-sales-opportunities-quote) topic.
6. Click **Save**.
