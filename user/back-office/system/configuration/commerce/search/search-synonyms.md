<a id="configuration-guide-commerce-search-synonyms"></a>

# Configure Global Synonym Search Settings

#### HINT
The feature is available starting from OroCommerce Enterprise v5.0.6. To check which application version you are running, see the [system information](../../../system-information/index.md#system-information).

In OroCommerce Enterprise Edition, you can [create a synonym group](../../../../marketing/synonyms/index.md#user-guide-search-synonyms) where a search for one word from this group in the OroCommerce storefront would return results for all the synonyms in this group. Synonym management is enabled globally and [per website](../../../websites/web-configuration/commerce/search/website-search-synonyms.md#configuration-website-commerce-search-synonyms) in the system configuration, and subsequently managed through **Marketing > Search > Search Synonyms** in the main menu.

To enable search synonyms globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Search > Search Synonyms** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

1. Сlear the **Use Default** checkbox.
2. Select the **Enable Search Synonyms** checkbox to add the ability to search for synonyms during the full-text search in the storefront.
3. Click **Save Settings**.

![Search synonyms global configuration option](user/img/system/config_commerce/search/search-synonyms-config.png)

Once search synonyms configuration option has been enabled, the feature is added to the main menu under **Marketing > Search > Search Synonyms**.

![Illustration of how enabling the search synonym configuration option triggers the creation of the Search Synonyms menu under Marketing.](user/img/system/config_commerce/search/search-synonyms-config-enables-menu.png)

**Related Content**

* [Create Storefront Search Synonyms](../../../../marketing/synonyms/index.md#user-guide-search-synonyms)
* [Synonym Management (Dev Guide)](../../../../../../bundles/commerce/WebsiteElasticSearchBundle/synonym-management.md#bundle-docs-commerce-website-elasticsearch-bundle-synonyms)
