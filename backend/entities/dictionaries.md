<a id="dev-entities-dictionaries"></a>

# Dictionaries

Dictionary entities store a predefined set of values of a particular type, along with their translations. Values within a dictionary can also have a priority or other data.

## Automatic Creation of REST API for Dictionaries

REST API resources for viewing dictionary values are created automatically and are accessible by the following URL: `/api/{dictionary_plural_alias}`. For example `/api/casestatuses`.

Please refer to [entity aliases](entity-aliases.md#entity-aliases) topic to better understand how the aliases are generated.

**Dictionary types supported out-of-the-box**

REST API resources are created automatically for the following types of dictionaries:

- Non-translatable dictionary
- Translatable dictionary (implements `Gedmo\Translatable\Entity\MappedSuperclass\AbstractTranslation`)
- Personal translatable dictionary (implements `Gedmo\Translatable\Entity\MappedSuperclass\AbstractPersonalTranslation`)
- Enum (Option set)

**Creating a custom dictionary type**

You may have a group of entities that qualify as a dictionary but are not part of the `dictionary` group in the entity configuration. To add their entities to the dictionary REST API, do two things.

1. Create a dictionary value list provider implementing the <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/EntityBundle/Provider/DictionaryValueListProviderInterface.php" target="_blank">DictionaryValueListProviderInterface</a> interface.
2. Register your provider service in the DI container by the following tag: `oro_entity.dictionary_value_list_provider`:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
# Resources/config/services.yml
services:

    acme_demo.dictionary_value_list_provider:
        class: Acme\Bundle\DemoBundle\Provider\AcmeDictionaryValueListProvider
        public: false
        arguments:
            - '@oro_entity_config.config_manager'
            - '@doctrine'
        tags:
            - { name: oro_entity.dictionary_value_list_provider, priority: 200 }
```

#### NOTE
You can specify a priority for the dictionary value list provider. The higher the priority number, the earlier the provider runs.

If more than one dictionary value list provider supports the same type of dictionary, only the one with the greater priority runs. The priority value is optional and defaults to 0.

<!-- Frontend -->
