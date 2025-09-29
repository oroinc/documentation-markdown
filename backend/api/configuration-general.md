<a id="web-api-configuration-general"></a>

# General Configuration

The following general configuration options can be changed via Resources/config/oro/app.yml in any bundle
or config/config.yml of your application.

```yaml
oro_api:

    # The prefix of REST API URLs.
    # The default value is "/api/".
    rest_api_prefix: '/api/'

    # The regular expression pattern to which REST API URLs are matched.
    # The default value is "^/api/(?!(rest|doc)($|/.*))".
    rest_api_pattern: '^/api/(?!(rest|doc)($|/.*))'

    # The default page size. It is used when the page size is not specified in a request explicitly.
    # The default value is 10.
    default_page_size: 10

    # The maximum number of primary entities that can be retrieved by a request.
    # The default value is -1 that means unlimited.
    max_entities: -1

    # The maximum number of related entities that can be retrieved by a request.
    # The default value is 100.
    max_related_entities: 100

    # The maximum number of entities that can be deleted by one request.
    # The default value is 100.
    max_delete_entities: 100
```

To change the maximum number of entities that can be retrieved by a request for a specific API resource
use the `max_result` option in Resources/config/oro/api.yml. For details see
[entities](configuration.md#web-api-entities-config) and [actions](configuration.md#web-api-actions-config) configuration sections.

Also see [How To](how-to.md#max-number-of-entities-to-be-deleted) to learn how to change the maximum number of entities
that can be deleted by one request for a specific API resource.
