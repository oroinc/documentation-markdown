# Testing

#### HINT
See the [Search Index](../../../backend/architecture/tech-stack/search/index.md#search-index-overview) documentation to get a more high-level understanding of the search index concept in the Oro application.

Trait <a href="https://github.com/oroinc/orocommerce/tree/6.1/src/OroBundle/WebsiteSearchBundle/Tests/Functional/WebsiteSearchExtensionTrait.php" target="_blank">WebsiteSearchExtensionTrait</a> contains methods which help reindex data in test if required.

Example of usage:

```php
/**
 * @dbIsolationPerTest
 */
class ReindexRequiredTest extends FrontendWebTestCase
{
    use WebsiteSearchExtensionTrait;

        #[\Override]
        protected function setUp(): void
        {
            ...

            $this->reindexProductData(); // if we need re-index product data in every test
        }

        public function testExampleReindexData()
        {
            $this->reindexProductData(); // if we need re-index product data in specific test
            ...
        }
}
```

<!-- Frontend -->
