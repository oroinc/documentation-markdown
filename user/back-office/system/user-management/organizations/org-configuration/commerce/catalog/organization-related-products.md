<a id="sys-users-organization-commerce-catalog-related-products"></a>

# Configure Related Items Settings per Organization

In the Related Items section, you can configure the settings for related, up-sell, and similar products for a particular organization. These settings may apply [globally](../../../../../configuration/commerce/catalog/global-related-products.md#sys-commerce-catalog-relate-products-main), per organization,  and per [website](../../../../../websites/web-configuration/commerce/catalog/website-related-products.md#sys-websites-commerce-catalog-related-products).

#### NOTE
Before configuring the related items settings, add the required related and up-sell products to the desired products as described in the [Add Related Items](../../../../../../products/products/create-simple.md#products-related-items) topic. Similar products are displayed automatically following the similar product calculation algorithm.

To update the related product settings per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.
3. Select **Commerce > Catalog > Related Items** in the menu to the left.
4. Clear the **Use System** checkbox to customize the organization-wide settings.
5. In the **Related Products** section, the following options are available:
   * **Enable Related Products** — Toggles managing related products on/off. Enabled by default.
   * **Assign in Both Directions** — When enabled, the products become mutually related. For example, when you add a lightning bulb as a related product for a standing lamp, the relation works both ways and the lamp automatically becomes related item of the lightning bulb. This option is disabled by default.
   * **Maximum Number Of Assigned Items** — A limit of related products that may be added to any product.
   * **Maximum Items** — A limit of related products that are shown to a buyer.

     #### NOTE
     Some related products may be hidden by the visibility settings. If the list of related products still exceeds the limit, only the specified number of items (top of the list) will be shown.
   * **Minimum Items** — The minimum number of related products that may be shown to the buyer. If the actual number of products is less than this value, the related products section is hidden in the storefront for the product.
   * **Show Add Button** — Enables a buyer to order a related product from the related products section in the main product details. When the option is disabled, a buyer needs to open the related product details page before they can add it to the shopping list.
   * **Use Slider On Mobile** — When enabled, one related product is displayed below the main product information. Other related products are accessible using the horizontal slider. Click < and > to slide through the related products.

<a id="sys-users-organization-commerce-catalog-upsell-products"></a>
1. In the **Up-Sell Products** section, the following options are available:
   * **Enable Up-Sell Products** — Toggles managing up-sell products on/off. Enabled by default.
   * **Maximum Number Of Assigned Items** — A limit of related items that may be added to any product.
   * **Maximum Items** — A limit of up-sell products that are shown to the buyer.

     #### NOTE
     Some related items may be hidden by the visibility settings. If the list of up-sell products still exceeds the limit, only the specified number of items (top of the list) will be shown.
   * **Minimum Items** — The minimum number of up-sell products that may be shown to the buyer. If the actual number of products is less than this value, the up-sell products section is hidden in the storefront for the product.
   * **Show Add Button** — Enables a buyer to order the product from the up-sell products section in the main product details. When disabled, a buyer needs to open the up-sell product details page before they can add it to the shopping list.
   * **Use Slider On Mobile** — When the option is enabled, one up-sell product is displayed below the main product information. Other up-sell products are accessible using the horizontal slider. Click < and > to slide through the up-sell products.

<a id="sys-users-organization-commerce-catalog-similar-products"></a>

#### NOTE
**Similar Products** and **Similar Products in Shopping Lists** are available for the OroCommerce Enterprise edition if Elasticsearch is used as the search engine.

1. In the **Similar Products** section, the following options are available:
   * **Enable Similar Products** — Toggles managing similar products on/off. Enabled by default.
   * **Maximum Items** — A limit of similar products that are shown to a buyer.

     #### NOTE
     Some similar products may be hidden by the visibility settings. If the list of similar products still exceeds the limit, only the specified number of items (top of the list) will be shown.
   * **Minimum Items** — The minimum number of similar products that may be shown to the buyer. If the actual number of products is less than this value, the similar products section is hidden in the storefront for the product.
   * **Show Add Button** — Enables a buyer to order a similar product from the similar products section in the main product details. When the option is disabled, a buyer needs to open the similar product details page before they can add it to the shopping list.
   * **Use Slider On Mobile** — When enabled, one similar product is displayed below the main product information. Other similar products are accessible using the horizontal slider. Click < and > to slide through the similar products.
   * **Product Name Boost** — A boost factor for the product name, the boost is applied for each matched word. Leave the field empty to disable the boost.
   * **Category Boost** — A boost factor for the product category. Leave the field empty to disable the boost.
   * **Parent Category Boost** — A boost factor for the parent of a product category. Leave the field empty to disable the boost.
   * **Second Level Parent Category Boost** — A boost factor for the second level parent of a product category. Leave the field empty to disable the boost.
2. In the **Similar Products in Shopping Lists** (available as of OroCommerce version 5.1.9), the options are:
   * **Enable Similar Products in Shopping Lists** – Enabling this option add a block of Similar Products to the shopping list page.
   * **Maximum Items** — A limit of similar products that are shown to a buyer on the shopping list page.
   * **Minimum Items** — The minimum number of similar products that may be shown to the buyer on the shopping list page..
   * **Show Add Button** — Enables a buyer to order a similar product directly from the shopping list page.
   * **Use Slider On Mobile** — When enabled, one similar product is displayed below the main product information. Other similar products are accessible using the horizontal slider. Click < and > to slide through the similar products.
   * **Product Name Boost** — A boost factor for the product name, the boost is applied for each matched word. Leave the field empty to disable the boost.
   * **Category Boost** — A boost factor for the product category. Leave the field empty to disable the boost.
   * **Parent Category Boost** — A boost factor for the parent of a product category. Leave the field empty to disable the boost.
   * **Second Level Parent Category Boost** — A boost factor for the second level parent of a product category. Leave the field empty to disable the boost.

   ![Illustration of the Similar Products block on the shopping list page](user/img/system/config_commerce/catalog/sl-similar-products.png)
3. Click **Save**.

#### BUSINESS TIP
# Business Tip

How can technological advancements help your manufacturing company? Read our guide with four <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation examples in manufacturing</a>.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
