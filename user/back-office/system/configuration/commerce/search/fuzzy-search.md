<a id="configuration-guide-commerce-configuration-fuzzy-search"></a>

# Configure Global Storefront Fuzzy Search Settings

#### IMPORTANT
The feature is available for the Enterprise edition only.

#### HINT
Fuzzy search is available starting from v5.0.1. To check which application version you are running, see the [system information](../../../system-information/index.md#system-information).

You can set up storefront error-tolerant (fuzzy) search in website search index requests to Elasticsearch. When enabled, it finds similar results for the passed request phrase word by word. Please be aware that this feature is not supported by the ORM search engine. For configuration options to set up fuzzy search in the back-office, see the [General Setup Configuration topic](../../system/general-setup/search.md#configuration-system-configuration-general-setup-sysconfig-search-global).

#### NOTE
You can also configure storefront fuzzy search [on the website configuration level](../../../websites/web-configuration/commerce/search/website-fuzzy-search.md#configuration-website-commerce-search-fuzzy-search).

To configure storefront fuzzy search settings:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Search** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Global fuzzy search configuration options for the storefront](user/img/system/config_commerce/search/fuzzy-search-global.png)

1. Configure the following options:
   * **Enable Fuzzy Search** — enables fuzzy search in the appropriate area. This option is disabled by default.
   * **Error Tolerance** — sets how many errors in each word the application ignores. Possible values are:
     * One Error (default) – one error per word is tolerated
     * Two errors – two errors per word are tolerated
     * Request based – tolerance depends on the length of the word. One error for short words (up to 5 characters) and two errors for long words (6+ characters).
   * **Tolerance Starts From** — sets a threshold for error-tolerant search usage. The default value is *4*, which means that the application uses the exact match search for words with 1-3 characters and an error-tolerant search for words with 4+ characters.
   * **Tolerance Exclusions** — allows setting regular expression for words that must not use error-tolerant search; the exact match search is used instead. This option is beneficial for SKUs, manufacturer IDs, and other identifiers that may have similar values and lead to false-positive results when the error-tolerant search is used.
