<a id="configuration-website-commerce-search-synonyms"></a>

# Configure Synonym Search Settings per Website

In OroCommerce Enterprise Edition, you can [create a synonym group](../../../../../marketing/search/index.md#user-guide-search-synonyms) where a search for one word from this group in the OroCommerce storefront would return results for all the synonyms in this group. Synonym management is enabled [globally](../../../../configuration/commerce/search/search-synonyms.md#configuration-guide-commerce-search-synonyms) and per website in the system configuration, and subsequently managed through **Marketing > Search > Search Synonyms** in the main menu.

![Configuration option on the website level to enable the use of synonyms in the storefront search](user/img/system/websites/web_configuration/synonyms-website-config.png)

To enable synonyms per website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> more actions menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Search > Search Synonyms** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

1. Clear the **Use Organization** checkbox.
2. Select the **Enable Search Synonyms** checkbox to add the ability to search for synonyms during the full-text search in the storefront.
3. Click **Save Settings**.

<!-- Enabling synonyms in the application triggers the creation of the *Search Synonyms** menu under **Marketing > Search**. -->

**Related Content**

* [Create Storefront Search Synonyms](../../../../../marketing/search/index.md#user-guide-search-synonyms)
* [Synonym Management (Dev Guide)](../../../../../../../bundles/commerce/WebsiteElasticSearchBundle/synonym-management.md#bundle-docs-commerce-website-elasticsearch-bundle-synonyms)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
