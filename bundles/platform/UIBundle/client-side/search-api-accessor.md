<a id="bundle-docs-platform-ui-bundle-search-api-accessor"></a>

# SearchApiAccessor

**SearchApiAccessor** ⇐ [ApiAccessor](api-accessor.md#bundle-docs-platform-ui-bundle-apiaccessor). Provides access to the search API for autocomplete.
This class is by design to be initiated from the server configuration.

**Extends:** ApiAccessor

| Param                       | Type   | Description                                                                                                            |
|-----------------------------|--------|------------------------------------------------------------------------------------------------------------------------|
| options                     | Object | Options container Also check the options for [ApiAccessor](api-accessor.md#bundle-docs-platform-ui-bundle-apiaccessor) |
| options.search_handler_name | string | Name of the search handler to use                                                                                      |
| options.label_field_name    | string | Name of the property that will be used as a label                                                                      |
| options.value_field_name    | string | Optional. Name of the property that will be used as an identifier. By default = ‘id’                                   |

## searchApiAccessor.prepareUrlParameters()

**Kind**: instance method of SearchApiAccessor

## searchApiAccessor.formatResult(response) ⇒ Object

Formats response before it is sent out from this api accessor.
Converts it to form

```javascript
{
    results: [{id: '<value>', label: '<label>'}, ...],
    more: '<more>'
}
```

**Kind**: instance method of SearchApiAccessor

| Param    | Type   |
|----------|--------|
| response | Object |
