<a id="dev-entities-fallback"></a>

# Entity Fallback Values

You can set up an entity field to fallback to a different entity’s field value.
To set up such a field, add it to the entity as a property (or create a migration for adding it),
and add a @ConfigField annotation and Doctrine association to <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Entity/EntityFieldFallbackValue.php" target="_blank">EntityFieldFallbackValue</a> (or array configuration in migration) like the following configuration:

```php
/**
 * @var EntityFieldFallbackValue
 *
 * @ORM\OneToOne(targetEntity="Oro\Bundle\EntityBundle\Entity\EntityFieldFallbackValue", cascade={"All"})
 * @ORM\JoinColumn(name="some_field_name_fallback_id", referencedColumnName="id", onDelete="SET NULL")
 * @ConfigField(
 *     defaultValues={
 *          "fallback": {
 *              "fallbackList": {
 *                  "someFallbackId" : {
 *                      "fieldName": "someFieldName"
 *                  },
 *                  "systemConfig": {
 *                      "configName": "oro_entity.some_configuration_name"
 *                  }
 *              }
 *          }
 *     }
 * )
 */
protected $someFieldName;
```

An example of adding field by migration:

```php
$someTable = $schema->getTable('oro_some_table');
$fallbackTable = $schema->getTable('oro_entity_fallback_value');
$this->extendExtension->addManyToOneRelation(
    $schema,
    $someTable,
    'someFieldName',
    $fallbackTable,
    'id',
    [
        'extend' => [
            'owner' => ExtendScope::OWNER_CUSTOM,
            'cascade' => ['all'],
        ],
        'form' => [
            'is_enabled' => false,
        ],
        'view' => [
            'is_displayable' => false,
        ],
        'datagrid' => [
            'is_visible' => DatagridScope::IS_VISIBLE_FALSE,
        ],
        'fallback' => [
            'fallbackList' => [
                'someFallbackId' => ['fieldName' => 'someFieldName'],
                'systemConfig' => ['configName' => 'oro_entity.some_configuration_name'],
            ],
        ],
    ]
);
```

The fallbackType specifies the type of the field value - it is only mandatory if there is no defined system configuration fallback
(which should have the data_type in the form definition in system_configuration.yml, like:

```yaml
system_configuration:
    (...)
    fields:
        oro_entity.some_configuration_name:
            data_type: boolean
            type: choice
```

Possible values for the fallbackType can be found in <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Fallback/EntityFallbackResolver.php" target="_blank">EntityFallbackResolver</a>::$allowedTypes.

The fallbackList contains a list of possible fallback entities. The **systemConfig** fallback is a predefined id for falling
back to a system configuration <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/ConfigBundle/Entity/ConfigValue.php" target="_blank">ConfigValue</a> value, for which the `configName` fallback configuration is mandatory (which refers to the form type name defined in `system_configuration.yml`). There is a predefined fallback provider for `systemConfig` at <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Fallback/Provider/SystemConfigFallbackProvider.php" target="_blank">SystemConfigFallbackProvider</a>.

If a field, configured as fallback field, has a null value (no EntityFieldFallbackValue set at all), the resolver will try to automatically read
the fallback value from the defined fallbackList, in the order of definition - ie. from the example above, first try the
someFallbackId, then the systemConfig fallback.

To fallback to a new entity field, you need to create a new fallback provider, extending <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Fallback/Provider/AbstractEntityFallbackProvider.php" target="_blank">AbstractEntityFallbackProvider</a>, with a service definition in `Resources/config/fallbacks.yml` like:

```yaml
oro_entity.fallback.provider.system_config_provider:
    class: Oro\Bundle\EntityBundle\Fallback\Provider\SystemConfigFallbackProvider
    parent: oro_entity.fallback.provider.abstract_provider
    arguments:
        - "@oro_config.manager"
    tags:
        - { name: oro_entity.fallback_provider, id: systemConfig }
```

We extend the parent `oro_entity.fallback.provider.abstract_provider` service, inject some dependencies, and tag it with
oro_entity.fallback_provider as tag name, and systemConfig as id (this id will go into the @ConfigField fallbackList configuration as fallback name
The provider will then need to implement getFallbackHolderEntity which defines how to access the parent fallback entity, getFallbackLabel used for translating the fallback name,
and optionally the function isFallbackSupported which can add some conditions whether the fallback should appear as option on the ui for a specific instance.

Next we need to render the field in the main object’s class type, by embedding the <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Form/Type/EntityFieldFallbackValueType.php" target="_blank">EntityFieldFallbackValueType</a> in the main form type,:

```php
$builder->add('someFieldName', EntityFieldFallbackValueType::class);
```

This type defines 3 fields: scalarValue (which will hold the entity’s own value, if no fallback is wanted),
useFallback (checkbox for ui to select/deselect fallback possibility) and fallback (which by default will render a dropdown with fallback list,
and which will map to the fallback field of <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Entity/EntityFieldFallbackValue.php" target="_blank">EntityFieldFallbackValue</a> holding the fallback id (like systemConfig).
The options and types of those 3 fields can be overridden with value_options, fallback_options, use_fallback_options, value_type and fallback_type.
Internally, the submitted own value will be saved in scalarValue, if it is scalar, or arrayValue, if it’s an array.

## Examples

**Example of fallback widget**

![Example of fallback widget](img/backend/entities/fallback_example.png)

**EntityFieldFallbackValue table content**

![Fallback table content](img/backend/entities/fallback_table.png)

If the fallback column contains a value, it means the entity uses the fallback value.
If it is null and scalar_value or array_value column contains data, it means that the entity has its own value

The bundle also exposes a twig function to get the fallback compatible value of a field, which internally uses the
<a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/EntityBundle/Fallback/EntityFallbackResolver.php" target="_blank">EntityFallbackResolver</a>.

```twig
{{ oro_entity_fallback_value(entity, 'someFieldName') }}
```

<!-- Frontend -->
