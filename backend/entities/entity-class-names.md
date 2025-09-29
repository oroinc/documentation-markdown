<a id="dev-entities-entity-class-name-provider"></a>

# Entity Class Name Provider

This service aims to provide human-readable representation in **English** of an entity class name. OroPlatform uses this provider to generate a description of REST API resources that are generated on the fly. See <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/EntityBundle/Routing/DictionaryEntityApiDocHandler.php" target="_blank">DictionaryEntityApiDocHandler</a> for details.

**Interface of an entity class name provider**

The <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/EntityBundle/Provider/ChainEntityClassNameProvider.php" target="_blank">entity class name provider</a> service is a “chain” service. It works by asking a set of prioritized providers to get a human-readable representation of an entity class name. Each child service must implement <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/EntityBundle/Provider/EntityClassNameProviderInterface.php" target="_blank">EntityClassNameProviderInterface</a>. This interface declares the following methods:

- *getEntityClassName* - returns a human-readable representation for an entity class.
- *getEntityClassPluralName* - returns a human-readable representation in plural for an entity class.

**Create custom entity class name provider**

To create own provider just create a class implementing <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/EntityBundle/Provider/EntityClassNameProviderInterface.php" target="_blank">EntityClassNameProviderInterface</a> and register it in DI container with the tag **oro_entity.class_name_provider**. You can also use the existing <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/EntityBundle/Provider/AbstractEntityClassNameProvider.php" target="_blank">abstract provider</a> as a superclass for your provider.

```php
use Oro\Bundle\EntityBundle\Provider\AbstractEntityClassNameProvider;
use Oro\Bundle\EntityBundle\Provider\EntityClassNameProviderInterface;

class AcmeClassNameProvider extends AbstractEntityClassNameProvider implements EntityClassNameProviderInterface
{
    /**
     * {@inheritdoc}
     */
    public function getEntityClassName($entityClass)
    {
        // add your implementation here
    }

    /**
     * {@inheritdoc}
     */
    public function getEntityClassPluralName($entityClass)
    {
        // add your implementation here
    }
}
```

```yaml
entity_class_name_provider.acme:
    class: Acme\Bundle\TestBundle\Provider\AcmeClassNameProvider
    public: false
    tags:
        - { name: oro_entity.name_provider, priority: 100 }
```

You can specify the priority to move the provider up or down the provider’s chain. The bigger the priority number is, the earlier the provider will be executed. The priority value is optional and defaults to 0.

<!-- Frontend -->
