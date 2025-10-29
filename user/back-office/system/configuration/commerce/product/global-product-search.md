<a id="configuration-guide-commerce-configuration-product-search"></a>

# Configure Global Settings for Product Search

#### NOTE
The Product Search feature can be configured on the global, [organization](../../../user-management/organizations/org-configuration/commerce/product/organization-product-search.md#sys-users-organization-commerce-products-search), and [website](../../../websites/web-configuration/commerce/product/website-product-search.md#sys-websites-commerce-products-search) levels.

To configure the product search settings globally:

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Product Search** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Product search configuration options on global level](user/img/system/config_commerce/product/product-search-config.png)
3. Customize any of the options by proceeding through the following steps:
   1. Clear the **Use Default** checkbox next to the option.
   2. Enable the required checkbox or enter the necessary file size and type information.
4. In the **Product Fulltext Search** section, configure the following options:
   * **Number of Products in Search Autocomplete** — Maximum number of products shown in the storefront autocomplete dropdown.
   * **Number of Categories in Search Autocomplete** — Maximum number of categories shown in the storefront autocomplete dropdown.
     ![Illustration of 4 products and 2 categories in the autocomplete search field](user/img/concept-guides/search/storefront-autocomplete.png)
   * **Allow Partial Product Search** — When enabled, the customer can find a product in the global search and on quick order form using a substring inside a word. This means that even if users do not have the exact product name or spelling memorized, they can still find what they need. Enabling this option may have a performance impact on search behaviour. This is due to the system’s need to process and match substrings within product names or descriptions, potentially requiring additional computational resources.
     ![Partial Product Search illustration](user/img/concept-guides/search/partial-product-search.png)
5. Click **Save Settings**.

**Related Topics**

* [Search Functions Concept Guide](../../../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search).
