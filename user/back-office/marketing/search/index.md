# Search Management in the Back-Office

OroCommerce offers a variety of search-related features essential for optimizing your website’s search functionality that you manage under **Marketing > Search** in the main menu, such as:

* Search Terms
* Search History
* Search Synonyms

#### HINT
For more information on available configuration options for search, see our [Search Functions Concept Guide](../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search).

<a id="user-guide-search-search-terms"></a>

## Manage Search Terms

#### NOTE
Search Terms are available starting from OroCommerce version 5.1.8. By default, the feature is disabled and must be enabled in the [system configuration](../../system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-empty-search-results-global).

OroCommerce administrators can use the search terms functionality to dynamically respond to specific search phrases with tailored actions. When a designated search term is detected, the administrator can choose from the following responses:

* Automatically direct users to a predetermined page that best matches their search intent, ensuring they find the most relevant information or product.
* Add custom content blocks directly into the search results page. This can include promotional banners, important announcements, or additional information that enhances the user experience.
* Replace the default search results with a curated collection of products. This allows for highlighting specific products, improving product discoverability, and potentially increasing sales for targeted items.

### Create a Search Term

To create a new search term:

1. Navigate to **Marketing > Search > Search Terms** in the main menu and click **Create Search Term** on the top right.
2. Provide the following information in the **General** section:
   * **Owner** — The name of the business units whose users can manage the current search term.
   * **Phrases** — One or more search terms for which you want to trigger a specific action.
   * **Partial Match** — You can choose to trigger an action based on a fragment of the phrase(s) you specified in the field above (e.g., “tag” can trigger an action for “medical tag”). Please note that this is not a fuzzy search option, and deviation in spelling will prevent the action from being triggered.
3. In the **Action** section, choose what action you want to trigger for a search term in the **Action** dropdown: *Show search results page* or *Redirect to a different page*. The information to provide next will depend on the selected action.
   1. For the **Show search results page** action:
      * **Search Results > Product Collection**:
        * *Product Collection* – Choose a segment for the product collection.
        * *Additional Content Block* –  Optionally, you can add a content block in addition to the product collection segment.
      * **Search Results > Original Search Results**:
        * *Additional Content Block* –  Optionally, you can add a content block to the search results page.

   ![image](user/img/marketing/search/search-term-search-results.png)
   1. For the **Redirect to a different page** action, select what to display to users instead of the specified search term(s) in the **Target Type** dropdown:
      * *Content Node* – specify the [web catalog](../web-catalogs/index.md#user-guide-web-catalog) from which you want to choose the content node and the [content node](../web-catalogs/edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant) itself.
      * *Product* – select a specific product from the *Product* field dropdown
      * *Category* – select a master catalog category from the list in the *Category* field.
      * *Landing Page* – select a specific landing page from the *Page* field dropdown.
      * *System Page* – select a specific system page from the *System Page* field dropdown.
      * *URI* – specify a web address of the page or resource to which you want to redirect the user. This option supports URIs that include filters in the address (for example, when you use filters in the OroCommerce storefront to narrow down search results).

   > All target types, except URI, support the **301 Redirect** option. When enabled, this means that instead of forwarding users internally to a different page retaining the original URL, users will be redirected to a page with a new URL.
   ![image](user/img/marketing/search/search-term-redirect.png)

#### NOTE
If the product search produces an empty result and there is no custom page configured for that specific combination of a [search term](#user-guide-search-search-terms) and additional search criteria, you can configure an *Empty Search Results Page* in the system configuration on the [global](../../system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-empty-search-results-global), [organization](../../system/user-management/organizations/org-configuration/commerce/search/org-search-terms.md#configuration-guide-commerce-configuration-search-empty-page-results-org) and [website](../../system/websites/web-configuration/commerce/search/website-search-terms.md#configuration-guide-commerce-configuration-search-empty-page-results-website) levels.

1. In the **Restrictions** section, specify the target localization, website, and customer or customer group to which the search term configuration should apply. Keep in mind that only one field must be chosen for customers at a time, either a customer group or a customer.

   You also have the option to **Run Original Search** to check what a user sees without the search term configuration and what original search results you are substituting by adding the current search term configuration. You can view search results for each provided search term by clicking on the arrow next to the *Run Original Search* button.

   To apply content to more than one localization, website, and customer group or customer, click **Add** and set up additional conditions.
   ![image](user/img/marketing/search/search-term-original-search-check.png)

<a id="user-guide-search-search-history"></a>
1. Click **Save** on the top right.

You can view the list of all created search terms in the Search Terms [grid](../../getting-started/information-management/index.md#user-guide-data-management-basics).

![image](user/img/marketing/search/search-terms-grid.png)

## Manage Search History

Search History enables users to view a history of all searches performed in the storefront if [this option is enabled in the system configuration on the global, organization, or website level](../../system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-history). In particular, you can view a grid of all search terms, including the search term entered by the user, the type of search result (product autocomplete, product search, or empty), the number of products found (if applicable), the date and time of the search, the website where the search was performed, the localization used when the search was performed, and the name of the customer and customer user who performed the search (if applicable).

You can also [view a Search Terms report](../../reports-segments/reports/search-report.md#user-guide-search-terms-report) that displays the number of times a particular search term was used, the number of times that search term returned products, and the number of times it returned an empty result.

To view the search history, navigate to **Marketing > Search > Search History** in the main menu.

![Search history grid in the back-office](user/img/marketing/search/search-items-grid.png)

Here, you have the options to preview or delete search history items. Previewing items redirects you to a page in the storefront with a collection of products that match the search criteria.

<a id="user-guide-search-synonyms"></a>

## Create Storefront Search Synonyms

#### NOTE
This feature is available in the OroCommerce Enterprise Edition.

You can create a synonym group where a search for one word from this group in the OroCommerce storefront would return results for all the synonyms in this group. Synonym management is enabled [globally](../../system/configuration/commerce/search/search-synonyms.md#configuration-guide-commerce-search-synonyms) and [per website](../../system/websites/web-configuration/commerce/search/website-search-synonyms.md#configuration-website-commerce-search-synonyms) in the system configuration, and subsequently managed through **Marketing > Search > Search Synonyms** in the main menu.

### Create a Synonym Group

To create a new synonym group:

1. Navigate to **Marketing > Search > Search Synonyms** in the main menu.
2. Click **Create Search Synonym**.
3. Fill in the following details:
   * **Owner** — the owner of the synonym being created. This field is only displayed in the global organization.
   * **Websites** — a list of websites where the synonym is to be used. Hold ctrl to select more than one website.
   * **Synonyms** — a list of comma-separated synonyms, for example, good, excellent. Arrow notation can be used to define unidirectional synonyms: excellent => good.
4. Click **Save**.

![Illustration of how search synonyms configured in the back-office work in the storefront](user/img/marketing/search/synonym-search-back-office-storefront-example.png)

You can view the list of all created search synonyms in the Search Synonym [grid](../../getting-started/information-management/index.md#user-guide-data-management-basics).

**Related Content**:

* [Enable Search Synonyms Globally](../../system/configuration/commerce/search/search-synonyms.md#configuration-guide-commerce-search-synonyms)
* [Enable Search Synonyms per Website](../../system/websites/web-configuration/commerce/search/website-search-synonyms.md#configuration-website-commerce-search-synonyms)
* [Synonym Management (Dev Guide)](../../../../bundles/commerce/WebsiteElasticSearchBundle/synonym-management.md#bundle-docs-commerce-website-elasticsearch-bundle-synonyms)
* [Search (Terms) Report](../../reports-segments/reports/search-report.md#user-guide-search-terms-report)
* [Configure Search History Settings](../../system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-history)
* [Configure the Empty Search Results Page](../../system/configuration/commerce/search/search-terms.md#configuration-guide-commerce-configuration-search-empty-search-results-global)
