<a id="user-guide-getting-started-search"></a>

# Search Functions Concept Guide

A search function on your website provides a seamless experience for your visitors. Giving customers the ability to find the information they are looking for quickly is a key ingredient for creating a user-friendly website.

Your website may have a vast database with numerous pages and information, making it harder for users to locate the required information. With this in mind, Oro has developed a helpful search utility to help customers query that database and find the material quickly.

#### NOTE
See a short demo on how OroCommerce’s advanced search features can enhance the B2B ecommerce experience for both sellers and buyers.

<iframe width="560" height="315" src="https://www.youtube.com/embed/SqKn5xKjs0g?si=q0x0dG2hNzDmhUi0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

You can find the search bar:

* in the header and menu of the storefront

![Search bar in the storefront](user/img/concept-guides/search/search-bar-storefront.png)
* in the header of the back-office and in its system configuration menu

![Search bar in the back-office](user/img/concept-guides/search/search-bar-back-office.png)

To find a record through the search bar, start typing the search key into the text field and select the most relevant suggestion from the dropdown list.

Several out-of-the-box functions enhance the effectiveness and speed of the search functionality.

**Storefront-specific**

* [Global Search Boost](../../../back-office/products/product-attributes/index.md#products-product-attributes-create-frontend-options) - The feature works with the searchable product attributes only. It is available in the OroCommerce Enterprise edition. It influences the relevancy ranking of your search results in the storefront and helps pull the necessary attribute to the top of the search result list. By default, the boost for SKU is set to 5, for names to 3, meaning that the searchable word is first searched among SKUs, then names, etc. The bigger the number, the higher the relevancy. With Search Boost, you can configure any search behavior required for your business, which allows you to have better control over search results.

![Global search boost in action](user/img/concept-guides/search/global-search-boost.png)
* [Search Autocomplete](../../../back-office/system/configuration/commerce/product/global-product-search.md#configuration-guide-commerce-configuration-product-search) - The intuitive feature is available as of OroCommerce v5.1.7. It generates predictions based on searches that you start to type. It shows up-to-date product information, such as SKU, name, price, and inventory status. You can set the number of products to be displayed in the storefront search result dropdown on the global, [organization](../../../back-office/system/user-management/organizations/org-configuration/commerce/product/organization-product-search.md#sys-users-organization-commerce-products-search), and [website](../../../back-office/system/websites/web-configuration/commerce/product/website-product-search.md#sys-websites-commerce-products-search) levels.

![Search autocomplete illustration](user/img/concept-guides/search/storefront-autocomplete.png)
* [Saved Search](../../../storefront/account/saved-search.md#my-account-saved-search) - The feature is available in the OroCommerce Enterprise edition. It enables customer users to save their search queries, view these saved search queries under the Saved Searches menu in the customer user account. You can also configure the registered customers to receive notifications when a new product falls under the search conditions and when products from the search query result are back in stock. The configuration is available on the [global](../../../back-office/system/configuration/commerce/search/saved-search.md#configuration-guide-commerce-configuration-saved-search), [organization](../../../back-office/system/user-management/organizations/org-configuration/commerce/search/organization-saved-search.md#organization-commerce-configuration-saved-search), and [website](../../../back-office/system/websites/web-configuration/commerce/search/website-saved-search.md#configuration-website-commerce-search-saved-search) levels.

![Saved search illustration](user/img/concept-guides/search/saved-search.png)
* [Fuzzy Search in the Storefront](../../../back-office/system/configuration/commerce/search/fuzzy-search.md#configuration-guide-commerce-configuration-fuzzy-search) - The feature is available in the OroCommerce Enterprise edition. Fuzzy searches help you find relevant results even when the search terms are misspelled. When enabled, it searches for the text that matches the term closely instead of exactly. You can set the number of errors in each word the application can ignore or set a threshold for the error-tolerant search usage. The configuration is available on the global and [website](../../../back-office/system/websites/web-configuration/commerce/search/website-fuzzy-search.md#configuration-website-commerce-search-fuzzy-search) levels.

![Fuzzy search with 2 errors illustration](user/img/concept-guides/search/fuzzy-search-storefront.png)
* [Search History](../../../back-office/system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-history) - If the feature is enabled, you can view a history of all searches performed by a customer user in the storefront under **Marketing > Search > Search History**. The grid includes information on all keywords entered by a user, the search result type (product autocomplete, product search, or empty), the number of products found (if applicable), the date and time of the search, the website where the search was performed, the localization used when the search was performed, and the name of the customer and customer user who performed the search (if applicable).

  The option also enables a [Search Terms report](../../../back-office/reports-segments/reports/search-report.md#user-guide-search-terms-report) that shows how frequently a specific search phrase was used, and whether the search query returned an empty result.

  The feature can be configured on all levels: globally, [per organization](../../../back-office/system/user-management/organizations/org-configuration/commerce/search/org-search-terms.md#organization-commerce-configuration-search-history), [website](../../../back-office/system/websites/web-configuration/commerce/search/website-search-terms.md#configuration-website-commerce-search-history), [customer group](../../../back-office/customers/customer-groups/customer-group-configuration/commerce/search/customer-group-search-terms-settings.md#user-guide-customer-groups-configuration-settings-search), and [customer](../../../back-office/customers/customers/customer-configuration/commerce/search/customer-search-settings.md#user-guide-customers-search-settings).

![Search history grid in the back-office](user/img/marketing/search/search-items-grid.png)

**Back-office-specific**

* **Search by an entity in the back-office** - When searching for a term in the back-office, the feature enables you to select the entity that most likely contains the searching record. The search result will then display the records that belong to this entity first.

![Difference between the regular search and search by entity](user/img/concept-guides/search/search-by-entity.png)

<a id="user-guide-getting-started-search-tag"></a>
* **Search by tag in the back-office** - The feature enables you to view all the records with a specific tag anywhere in the system. Select the *Tag* entity when searching for a term and click the tag when found. You will be presented with a page that looks similar to the search results and contains all the records with this tag.

![Difference between the regular search and search by entity](user/img/concept-guides/search/search-by-tag.png)
* [Quick Search](../../../back-office/system/configuration/quick-search.md#user-guide-system-configuration-quick-search) - The intelligent search feature is located in the configuration panel on the left (on all configuration levels). It helps you locate the specific configuration option instantly by keywords. It narrows down the query when you start typing the key letters and displays real-time search results.

![Difference between the regular search and search by entity](user/img/concept-guides/search/quick-search.png)
* [Fuzzy Search in the Back-Office](../../../back-office/system/configuration/system/general-setup/search.md#configuration-system-configuration-general-setup-sysconfig-search-global) - The feature is available in the OroCommerce Enterprise edition. It works similarly to the storefront fuzzy search functionality but searches for the misspelled terms in the back-office. The configuration is only available globally.
