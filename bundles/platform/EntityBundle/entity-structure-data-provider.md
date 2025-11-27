<a id="bundle-docs-platform-entity-bundle-entity-structure-data-provider"></a>

# EntityStructureDataProvider

**EntityStructureDataProvider**:

> - provides access over EntityStructuresCollection to [EntityStructure API](../../../backend/entities/entity-structure-data-provider.md#dev-entities-structure-data-provider).
> - shares the same instance of EntityStructuresCollection between providers
> - contains a pack of helper methods to filter and navigate across entity relations

## Get the EntityStructureDataProvider instance

Static method createDataProvider of EntityStructureDataProvider allows to get the provider’s instance:

```javascript
var EntityStructureDataProvider = require('oroentity/js/app/services/entity-structure-data-provider');

    // ...
    initialize: function(options) {
        var providerOptions = {
            rootEntity: 'Oro\\Bundle\\UserBundle\\Entity\\User'
        };
        EntityStructureDataProvider
            .createDataProvider(providerOptions, this)
            .then(function(provider) {
                this.provider = provider;
            }.bind(this));
    }
```

The signature for createDataProvider method is the following:

```javascript
/**
 * Creates instance of data provider and returns it with the promise object
 *
 * @param {Object=} options
 * @param {string} [options.rootEntity] class name of root entity
 * @param {string} [options.filterPreset] name of filter preset
 * @param {Object.<string, boolean>} [options.optionsFilter] acceptable entity's and fields' options
 *  example:
 *      {auditable: true, configurable: true, unidirectional: false}
 * @param {[Object|string]} [options.exclude]
 *  examples:
 *      ['relationType'] - will exclude all entries that has 'relationType' key (means relational fields)
 *      [{type: 'date'}] - will exclude all entries that has property "type" equals to "date"
 * @param {[Object|string]} [options.include]
 *  examples:
 *      ['relationType'] - will include all entries that has 'relationType' key (means relational fields)
 *      [{type: 'date'}] - will include all entries that has property "type" equals to "date"
 * @param {fieldsFilterer} [options.fieldsFilterer]
 * @param {RegistryApplicant} applicant
 * @return {Promise.<EntityStructureDataProvider>}
 */
createDataProvider: function(options, applicant) { ... }
```

Where the first argument is the options for the provider:

- rootEntity class name of the entity where navigation by fields and relations starts from
- optionsFilter, exclude and include rules allow to define constraints for the entities and the fields that the provider returns
- fieldsFilterer custom filter function
- filterPreset name of the preconfigured filter

And the second argument is the applicant (who the structure is requested for). It allows to define life cycles of shared EntityStructuresCollection instance in registry (see [registry](../../../frontend/javascript/registry.md#dev-doc-frontend-registry) for details).

The method works asynchronously, it returns provider instance within promise.
The promise assures the instance EntityStructuresCollection of the provider already contains
fetched data from the server and the provider is ready to use.

## Define Filter’s Preset

It is common for several providers to use the same filter configuration.
For such cases, you can define filter preset:

```javascript
EntityStructureDataProvider.defineFilterPreset('workflow', {
    optionsFilter: {unidirectional: false, configurable: true},
    exclude: [
        {relationType: 'manyToMany'},
        {relationType: 'oneToMany'}
    ]
});
```

Once the preset is defined, its name can be used to configure the provider:

```javascript
EntityStructureDataProvider
    .createDataProvider({
        filterPreset: 'workflow',
        include: [{type: 'date'}, {type: 'datetime'}]
    }, applicant)
```

The direct definition of fieldsFilterer, optionsFilter, exclude and include options have higher priority over the defined onr in used filterPreset. This allows to customize filter configuration for a certain provider.

See other methods documentation in <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/EntityBundle/Resources/public/js/app/services/entity-structure-data-provider.js" target="_blank">entity-structure-data-provider.js</a>.

<!-- Frontend -->
