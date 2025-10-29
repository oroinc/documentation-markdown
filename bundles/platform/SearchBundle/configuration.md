<a id="db-search-configuration"></a>

# Configuration

#### HINT
See the [Search Index](../../../backend/architecture/tech-stack/search/index.md#search-index-overview) documentation to get a more high-level understanding of the search index concept in the Oro application.

OroSearchBundle provides options that you can use to customize the
search functionality.

## System Configuration

All configuration data is placed in the configuration under the alias
`oro_search`. Let us look at the configuration example:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/app.yml*
```yaml
oro_search:
    engine_dsn: "orm:"
    engine_parameters:
        force_refresh: true
        language_optimization: true
        relevance_optimization: true
        log_queries: false
        #    item_container_template: '@My/Search/itemContainer.html.twig'
```

Description of parameters:

- **engine_dsn**, default “orm” (converted to container parameter
  *oro_search.engine*) - specifies the search engine name used to perform
  search and indexation (see section [Search Engine Configuration](#search-engine-configuration));
- **engine_parameters** (converted to the container parameter
  *oro_search.engine_parameters*) - additional parameters of the search engine used for initialization (e.g., IP, port, credentials, etc.);
- **log_queries**, default false (converted to container parameter
  *oro_search.log_queries*) - a flag that defines whether it is necessary to log
  search queries to the database;
- **item_container_template**, default
  “@OroSearch/Datagrid/itemContainer.html.twig” (converted to
  container parameter *oro_search.twig.item_container_template*) -
  template used to render an entity row in search results;
- **entities_config** (converted to container parameter
  *oro_search.entities_config*) - entity search configuration that can be
  used to override the default entity search configuration (see section
  [Entity Configuration](#db-search-configuration-entity-configuration)).

## Configuration Merging

All configurations merge in the boot bundles order. The application collects
configurations of all nodes with the same name and merges them into one
configuration. Merging uses simple rules:

- if the node value is scalar, the value will be replaced
- if the node value is an array:
  - by default, the value will be replaced
  - for node ‘fields’, this array will be appended by values from the
    second configuration.

After this step, the application knows about all entity search configurations from the search.yml files and has only one configuration for each entity.

**Example**

*src/Acme/Bundle/DemoBundle/Resources/config/oro/search.yml*
```yaml
    Acme\Bundle\DemoBundle\Entity\Question:
        alias: acme_demo_question                                   # Alias for 'from' keyword in advanced search
        route:
            name: acme_demo_question_view                           # Route name to generate url link to the entity record
            parameters:                                             # Array with parameters for route
                id: id
        search_template: '@AcmeDemo/Question/searchResult.html.twig' # Template to use in search result page for this entity type
        fields:
            -
                name: subject                                       # Name of field in entity
                target_type: text                                   # Type of virtual search field. Supported target types:
                target_fields:
                    - subject
            -
                name: description
                target_type: text
                target_fields:
                    - description
```

*src/Acme/Bundle/DemoBundle/Resources/config/oro/search.yml*
```yaml
    Acme\Bundle\DemoBundle\Entity\Question:
        alias: acme_demo_question                                   # Alias for 'from' keyword in advanced search
        fields:
            -
                name: priority
                relation_type: many-to-one                           # Indicate that this field is relation field to another table.
                relation_fields:                                     # Supported: one-to-one, many-to-many, one-to-many, many-to-one.
                    -
                        name: label                                 # related entity field name to index
                        target_type: text                           # related entity field name type
                        target_fields:                              # target fields to store field index
                            - priorityLabel
```

Result:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/search.yml*
```yaml
    Acme\Bundle\DemoBundle\Entity\Question:
        alias: acme_demo_question                                   # Alias for 'from' keyword in advanced search
        route:
            name: acme_demo_question_view                           # Route name to generate url link to the entity record
            parameters:                                             # Array with parameters for route
                id: id
        search_template: '@AcmeDemo/Question/searchResult.html.twig' # Template to use in search result page for this entity type
        fields:
            -
                name: subject                                       # Name of field in entity
                target_type: text                                   # Type of virtual search field. Supported target types:
                target_fields:
                    - subject
            -
                name: description
                target_type: text
                target_fields:
                    - description
            -
                name: priority
                relation_type: many-to-one                           # Indicate that this field is relation field to another table.
                relation_fields:                                     # Supported: one-to-one, many-to-many, one-to-many, many-to-one.
                    -
                        name: label                                 # related entity field name to index
                        target_type: text                           # related entity field name type
                        target_fields:                              # target fields to store field index
                            - priorityLabel
```

<a id="db-search-configuration-entity-configuration"></a>

## Entity Configuration

After inserting, updating, or deleting entity records, the search index must be updated. The search index consists of data from entities by mapping parameters. Entity search configuration maps fields to the virtual search fields in the search index.

Entity search configuration can be stored in the main `config.yml` file (in `oro_search` config section) or in the `search.yml` files in the config directory of the bundle.

Configuration is an array that contains info about the bundle name, entity name, and the array of fields. Fields array contains the array of field names and field types. Data from all text fields will be stored in the **all_text** virtual field. Additionally, all the fields will be stored in the `fieldName` virtual fields if the `target_fields` parameter is not set.

Example:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/search.yml*
```yaml
    Acme\Bundle\DemoBundle\Entity\Question:
        alias: acme_demo_question                                   # Alias for 'from' keyword in advanced search
        route:
            name: acme_demo_question_view                           # Route name to generate url link to the entity record
            parameters:                                             # Array with parameters for route
                id: id
        search_template: '@AcmeDemo/Question/searchResult.html.twig' # Template to use in search result page for this entity type
        fields:
            -
                name: subject                                       # Name of field in entity
                target_type: text                                   # Type of virtual search field. Supported target types:
                target_fields:
                    - subject
            -
                name: description
                target_type: text
                target_fields:
                    - description
            -
                name: priority
                relation_type: many-to-one                           # Indicate that this field is relation field to another table.
                relation_fields:                                     # Supported: one-to-one, many-to-many, one-to-many, many-to-one.
                    -
                        name: label                                 # related entity field name to index
                        target_type: text                           # related entity field name type
                        target_fields:                              # target fields to store field index
                            - priorityLabel
```

## Search Engine Configuration

The search bundle provides the ability to use different search engines through the common interface.

The used search engine is defined in the configuration under the `oro_search.engine` key. To make the engine work, at least one bundle must have s file with the *Resources/config/oro/search_engine/<engine_name>.yml* name that contains the configuration of search engine services that will be added to a container services.

To make the engine work, two services must be defined in the engine configuration:

> - search service *oro_search.search.engine* must implement *Oro\\Bundle\\SearchBundle\\Engine\\EngineInterface*.
> - indexer service *oro_search.search.engine.indexer* must implement *Oro\\Bundle\\SearchBundle\\Engine\\IndexerInterface*.

To make implementation easier, there are abstract classes *Oro\\Bundle\\SearchBundle\\Engine\\AbstractEngine* and *Oro\\Bundle\\SearchBundle\\Engine\\AbstractIndexer* that provide useful functionality (such as logging, queuing, etc.).

Suppose the search engine requires additional parameters (credentials, index configuration, etc.). In that case, they can be passed through the configuration using the *oro_search.engine_parameters* key so these parameters can be injected into search services.

Also, engine configuration can override existing services to support some specific use cases of the search engine (e.g., ORM engine overrides index listener to support single flush).

<a id="db-search-configuration-datagrid"></a>

## Datagrid Configuration

The SearchBundle supplies a datasource that can be used interchangeably with the default ORM datasource. This datasource feeds pure search index data, bypassing the default DBMS, thus allowing pure index storage layer-driven datagrids to be built.

The following is an example of a DatagridBundle’s configuration entry in the `Resources/config/oro/datagrids.yml` file that builds a simple user datagrid using search index data only. Keep in mind that the frontend datagrid is configured in the Resources/views/layouts/<theme>/config/datagrids.yml file.

*src/Acme/Bundle/DemoBundle/Resources/config/oro/datagrids.yml*
```yaml
    acme-demo-search-question-grid:
        source:
            type: search
            query:
                select:
                    - text.subject
                    - text.description
                from:
                    - acme_demo_question
        columns:
            subject:
                label: acme.demo.question.subject.label
                data_name: subject
            description:
                label: acme.demo.question.description.label
                data_name: description
        sorters:
            columns:
                subject:
                    data_name: subject
                    type: string
                description:
                    data_name: description
                    type: string
            default:
                name: ASC
        filters:
            columns:
                quick_search:
                    label: 'Quick search'
                    type: string
                    data_name: all_text
                subject:
                    type: string
                    data_name: subject
                description:
                    type: string
                    data_name: description
        properties:
            id: ~
            subject: ~
            description: ~
        actions: [ ]
```
