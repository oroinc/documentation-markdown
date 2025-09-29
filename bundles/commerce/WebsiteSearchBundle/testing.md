# Testing

Trait <a href="https://github.com/oroinc/orocommerce/tree/4.2/src/Oro/Bundle/WebsiteSearchBundle/Tests/Functional/WebsiteSearchExtensionTrait.php" target="_blank">WebsiteSearchExtensionTrait</a> сontains methods which help reindex data in test if required.

Example of usage:

```php
/**
 * @dbIsolationPerTest
 */
class ReindexRequiredTest extends FrontendWebTestCase
{
    use WebsiteSearchExtensionTrait;

     /** {@inheritdoc} */
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
