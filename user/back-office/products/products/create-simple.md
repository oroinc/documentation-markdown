<a id="products-products-create-simple-product"></a>

# Create a Simple Product

#### HINT
This section is part of the [Product Management](../../../concept-guides/product-management/index.md#concept-guides-product-management) topic that provides a general understanding of the product concept in OroCommerce.

See a short demo on <a href="https://academy.oroinc.com/media-library/create-simple-product" target="_blank">how to create a simple product</a>, or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/I0dHJ87IpzE" frameborder="0" allowfullscreen></iframe>

To add a new [simple product](../../../glossary.md#term-Simple-Product) and make it available in the master catalog (for internal product management) and for purchase in the storefront:

1. Navigate to **Products > Products** in the main menu.
2. Click **Create Product**.
3. Select the **Simple** product type.
4. Select the [product family](../product-families/index.md#products-product-families) to define the product options and details that will be filled in the following steps.
5. Place the product under the necessary category in the master catalog by clicking on the category. Use the search to limit the list of categories.
6. Click **Continue**.

The product details page appears.
<br/>
1. In the **General** section:
   1. Enter the product SKU and name.
   2. Enter a URL slug that is used to build a human-readable URL for the product page in the storefront.
   3. Select the product status: *Enabled* or *Disabled*. When disabled, the product is not included in the catalog and is considered to be a draft.
   4. Specify whether the product should be featured or not by selecting *Yes* or *No* respectively.
   5. Specify whether the product is a new arrival. When set to *Yes*, the product is highlighted in the storefront.
      ![A simple product creation page](user/img/products/products/create_product.png)
   6. For **Brand**, select a [brand](../product-brands/index.md#user-guide-product-brands) from the list. Use <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to view the list of all available brands. To create a new brand, click **+**.
   7. Configure units of quantity:
      * In the **Unit Of Quantity** list, select the main [product unit](product-units/index.md#user-guide-products-product-units-in-use) that is shown by default when you view the product details in the storefront. Available options: *each*, *item*, *kilogram*, *piece*, *set*.
      * In the **Precision** field, set the acceptable precision (number of digits after the decimal point) for the quantity that a user may order or add into the shopping list. Items and sets are usually whole numbers, and units like kilograms may get precision of 2 to allow buying a custom volume (e.g., 0.5 kg).
      * Click **+ Add** to add more than one unit of quantity.
        ![The detailed setting of the additional units field](user/img/products/products/ProductsCreate_Units.png)

        For every additional unit, provide precision and conversion rate compared to the main unit of quantity.

        Select the **Sell** checkbox to enable selling the product in these units. Unless **Sell** is selected, the unit is considered a draft.

        You can delete the unnecessary unit of quantity by clicking the <i class="fas fa-times" aria-hidden="true"></i> **Delete** icon next to it.
   8. In the **Tax Code** list, select the [product tax code](../../taxes/product-tax-codes/index.md#taxes-product-tax-code) that defines the percentage of tax that can be included in the purchase order during the checkout.

      The tax calculation process depends on the tax jurisdiction that you decided to use in OroCommerce and other tax calculation options.
2. In the **Short Description** section, provide a short but meaningful default description that best positions the product for your target audience and will appear in the catalog listing. Move from tab to tab to localize the description by setting the required fallback option. You can select whether to fall back to the default value, parent localization, or a custom value from the dropdown. When selecting the custom value, provide the localized version of the short description in the text field.
   > ![Localization fallback option for the short description of the simple product](user/img/products/products/localize_short_descriptions_product.png)
3. In the **Description** section, provide a long default product description that will appear on the product view page. Move from tab to tab to localize the description by setting the required fallback option. From the dropdown, you can select whether to fall back to the default value, parent localization, or a custom value. When selecting the custom value, provide the localized version of the long description in the WYSIWYG field. For more details on WYSIWYG management, see the [WYSIWYG Editor](../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) topic.
4. In the **Image** section, add a new image to the product by clicking **+Add Image** and then **Choose Image**. You can either upload a new image or select the required one from the list of available [digital assets](../../marketing/digital-assets/index.md#digital-assets) records.

> Then, select whether to show the image as *main* (the image is used in the product details view), *listing* (the image is shown in the catalog listing), or *additional* (additional product pictures). All three categories can be selected at the same time. To remove the image, click the <i class="fas fa-times" aria-hidden="true"></i> **Delete** icon next to it.
1. In the **Design** section, select the [page template](page-templates.md#user-guide-page-templates) from the drop-down.

> ![The list of available page templates in the dropdown of the Page Template field](user/img/products/products/SimpleProductDesign.png)
1. In the **SEO** section, provide the following information:

> * **Meta Keywords** — Enter the meta keywords for the product. A meta keyword is a specific type of meta tag that appears in the HTML code of a web page and helps tell search engines what the page’s topic is.
> * **Meta Title** — Enter the meta title for the product. A meta title is seen by search engine users and helps a search engine index the page.
> * **Meta Description** — Enter the meta description for the product. A meta description summarizes a page content. Search engines show a meta description in search results if they see the searched phrase in the description.

<a id="create-simple-product-inventory"></a>
1. In the **Inventory** section, provide the following information:

> <!-- start_inventory -->

> | Field                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
> |-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | **Inventory Status**          | This setting enables you to define and modify status information for the stock of the product.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
> | **Managed Inventory**         | This setting defines the method for [inventory](../../inventory/index.md#user-guide-inventory) management. With *Use category defaults*, the product’s **Manage Inventory** inherits the setting selected for the product’s parent category. With *Use system config*, the product uses the system configuration setting. Selecting *Yes* enables interactive updates based on the product inventory information from the **Inventory > Warehouses** section. Selecting *No* disables connection to the inventory, and uses the static **Inventory Status** value. |
> | **Highlight Low Inventory**   | This option defines if low inventory for products is displayed in the storefront.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
> | **Inventory Threshold**       | A minimum quantity of the product treated as In stock. When a product quantity drops below this value, the product inventory status becomes Out Of Stock.                                                                                                                                                                                                                                                                                                                                                                                                          |
> | **Low Inventory Threshold**   | The minimum stock level defined for the product. Reaching the defined level will trigger a warning message to the buyer in the storefront.                                                                                                                                                                                                                                                                                                                                                                                                                         |
> | **Backorders**                | A flag that indicates whether OroCommerce accepts backorders (EE feature). When set to *Yes*, buyers and salespeople can order products in quantities not currently available in the warehouses. The remaining portion of the order will be sustained until the product is back in stock.                                                                                                                                                                                                                                                                          |
> | **Decrement Inventory**       | A flag that indicates whether OroCommerce decrements inventory upon order. A product quantity can become negative when both **Decrement Inventory** and **Backorders** are enabled.                                                                                                                                                                                                                                                                                                                                                                                |
> | **Minimum Quantity to Order** | A minimum quantity that a buyer or salesperson can claim in the RFQ, customer order, quote, or a shopping list.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
> | **Maximum Quantity to Order** | A maximum quantity that a buyer or salesperson can claim in the RFQ, customer order, [quote](../../sales/quotes/index.md#user-guide-sales-quotes), or a shopping list.                                                                                                                                                                                                                                                                                                                                                                                             |
> | **Is Upcoming**               | This option informs a customer that the product of the selected category is not in stock currently but will be available later. When set to *Yes*, an additional **Availability Date** is displayed. To remove the upcoming products label, set the option to *No* or customize the required behavior in the [system configuration](../../system/configuration/commerce/inventory/product-options.md#upcoming-products-config).                                                                                                                                    |
> | **Availability Date**         | The date which indicates the exact date and time since the selected product will be available in stock.                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
> <!-- finish_inventory -->![The detailed settings of the inventory section](user/img/products/products/simple_product_inventory.png)
1. Add fixed product prices in the **Product Price** section. Note that fixed prices override the automatically generated [price lists](../../../concept-guides/pricing/index.md#user-guide-pricing).

   Click **+Add**, select a price list, and specify quantity, units, price value, and currency.
   ![The product prices setting](user/img/products/products/SimpleProductPrices.png)
2. In the **Shipping Options** section, click **+Add Options** and provide unit, weight, and weight measuring unit, dimensions (width, height, depth), and dimensions measuring unit and freight class.
3. Review translation rules for a product name, URL slug, long description, and short description.

   To enter translation manually, click <i class="fas fa-language" aria-hidden="true"></i>, clear the **Use <parent translation>** checkbox next to the required language, and provide your translation version.
   ![Provide the relevant translation](user/img/products/products/ProductsCreateTranslation.png)
4. Click **Save**.

<a id="products-related-items"></a>

## Add Related Items

Once the core product information is saved, you may add related products and up-sell products to display them in the **Related Items** section in the product details in the back-office, and in the **Related Products** and **Up-sell Products** blocks next to the product details in the storefront.

<a id="products-related-products"></a>

To add related products to the product information:

1. Navigate to the **Products > Products** using the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click the <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** icon to preview its details.
3. Navigate to the **Related Items** section and click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Quick Edit** link in the section header.

   The **Related Items** page appears with the **Related Products** tab open by default.
4. Click **Select Related Products**.
5. In the **Select Related Products For** dialog:
   1. Select the **Is Related** checkboxes next to the products to mark them as related. Use a filter to limit the number of listed products and find the necessary items.
   2. Click **Select Products**.

   This will close the dialog and update the related items list with the products you have selected.

   #### NOTE
   To delete a related item, click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete**  next to it.
6. Once you add the related items, click **Save and Close**.

Now, you can configure related products [globally](../../system/configuration/commerce/catalog/global-related-products.md#sys-commerce-catalog-relate-products), per [organization](../../system/user-management/organizations/org-configuration/commerce/catalog/organization-related-products.md#sys-users-organization-commerce-catalog-related-products), and per [website](../../system/websites/web-configuration/commerce/catalog/website-related-products.md#sys-websites-commerce-catalog-related-products) in the system configuration.

<a id="products-upsell-items"></a>

To add up-sell items to the product information:

1. Navigate to the **Products > Products** using the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click the <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** icon to preview its details.
3. Navigate to the **Related Items** section and click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Quick Edit** link in the section header.

   The Related Items page appears.
4. Click the **Up-sell Products** tab.
5. Click **Select Up-Sell Items**.
6. In the **Select Up-Sell Items For** dialog:
   1. Select the **Is Related** checkboxes next to the products to mark them as related. Use a filter to limit the number of listed products and find the necessary items.
   2. Click **Select Products**.

   This will close the dialog and update the related items list with the products you have selected.

   #### NOTE
   To delete a related item, click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete**  next to it.
7. Once you add the related items, click **Save and Close**.

Now, you can configure up-sell products [globally](../../system/configuration/commerce/catalog/global-related-products.md#sys-commerce-catalog-relate-products), per [organization](../../system/user-management/organizations/org-configuration/commerce/catalog/organization-related-products.md#sys-users-organization-commerce-catalog-related-products), and per [website](../../system/websites/web-configuration/commerce/catalog/website-related-products.md#sys-websites-commerce-catalog-related-products) in the system configuration.

<!-- stop_product_create_simple -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
