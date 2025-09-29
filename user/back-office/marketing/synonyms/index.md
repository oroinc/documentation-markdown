<a id="user-guide-search-synonyms"></a>

# Create Storefront Search Synonyms

#### HINT
The feature is available starting from OroCommerce Enterprise v5.0.6. To check which application version you are running, see the [system information](../../system/system-information/index.md#system-information).

In OroCommerce Enterprise Edition, you can create a synonym group where a search for one word from this group in the OroCommerce storefront would return results for all the synonyms in this group. Synonym management is enabled [globally](../../system/configuration/commerce/search/search-synonyms.md#configuration-guide-commerce-search-synonyms) and [per website](../../system/websites/web-configuration/commerce/search/website-search-synonyms.md#configuration-website-commerce-search-synonyms) in the system configuration, and subsequently managed through **Marketing > Search > Search Synonyms** in the main menu.

To create a new synonym group:

1. Navigate to **Marketing > Search > Search Synonyms** in the main menu.
2. Click **Create Search Synonym**.
3. Fill in the following details:
   * Owner — the owner of the synonym being created. This field is only displayed in the global organization.
   * Websites — a list of websites where the synonym is to be used. Hold ctrl to select more than one website.
   * Synonyms — a list of comma-separated synonyms, for example, good, excellent. Arrow notation can be used to define unidirectional synonyms: excellent => good.
4. Click **Save**.

![Illustration of how search synonyms configured in the back-office work in the storefront](user/img/marketing/search/synonym-search-back-office-storefront-example.png)

**Related Content**:

* [Enable Search Synonyms Globally](../../system/configuration/commerce/search/search-synonyms.md#configuration-guide-commerce-search-synonyms)
* [Enable Search Synonyms per Website](../../system/websites/web-configuration/commerce/search/website-search-synonyms.md#configuration-website-commerce-search-synonyms)
* [Synonym Management (Dev Guide)](../../../../bundles/commerce/WebsiteElasticSearchBundle/synonym-management.md#bundle-docs-commerce-website-elasticsearch-bundle-synonyms)
