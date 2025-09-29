# Search Index

| Filename   | `search.yml`                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Root Node  | search                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Options    | * The fully qualified class name the indexed entity<br/>  \* [alias]()<br/>  \* [fields]()<br/>  > * [name](#reference-format-search-fields-name)<br/>  > * [relation_fields]()<br/>  > * [relation_type]()<br/>  > * [target_fields]()<br/>  > * [target_type]()<br/>  * [label]()<br/>  * [mode]()<br/>  * [route]()<br/>    * [name](#reference-format-search-route-name)<br/>    * [parameters]()<br/>  * [search_template]()<br/>  * [title_fields]()  (deprecated since 2.0) |

The `search.yml` file is used to configure how your entities are indexed to make them usable by
the internal search engine of OroPlatform. A fully working example can look like this:

*src/Acme/DemoBundle/Resources/config/oro/search.yml*
```yaml
 search:
     Acme\DemoBundle\Entity\Product:
         alias: demo_product
         search_template: '@AcmeDemo/result.html.twig'
         label: Demo products
         route:
             name: acme_demo_search_product
             parameters:
                 id: id
         mode: normal
         title_fields: [name] # deprecated since 2.0
         fields:
             -
                 name: name
                 target_type: text
             -
                 name: description
                 target_type: text
                 target_fields: [description, another_index_name]  parameter.
             -
                 name: manufacturer
                 relation_type: many-to-one
                 relation_fields:
                     -
                         name: name
                         target_type: text
                         target_fields: [manufacturer, all_data]
                     -
                         name: id
                         target_type: integer
                         target_fields: [manufacturer]
             -
                 name: categories
                 relation_type: many-to-many
                 relation_fields:
                     -
                         name: name
                         target_type: text
                         target_fields: [all_data]
```

## `alias`

**type**: `string`

An alias used in the `from` keyword in [advanced search](../../../api/advanced-search.md#advanced-search-api).

<a id="reference-format-search-fields"></a>

## `fields`

**type**: `sequence`

The list of fields that will be added to the search index. Each entry must be a map that can use
the following keys to configure how the property value will be indexed:

<a id="reference-format-search-fields-name"></a>

### `name`

**type**: `string`

The name of the entity property. This option is required.

### `relation_fields`

**type**: `sequence`

When the field represents an association (i.e. a value is configured for [relation_type]()), this is
a list of fields from the target entity to index. For each entry all the options of the parent
[fields option](#reference-format-search-fields) apply.

### `relation_type`

**type**: `string`

When the property denotes an association with another entity, the type of association (one of
`one-to-one`, `many-to-many`, `one-to-many`, or `many-to-one`) must be configured with this
option.

### `target_fields`

**type**: `sequence`

The `target_fields` option list the named indexes to which the property value will be added.

For example, a contact may have the properties `firstName`, `lastName`, and `namePrefix` and
all three properties should be searched when the user is looking for a value in the virtual
`name` field (when using the advanced search API). In this case, all three properties will list
the `name` field in `target_fields`:

```yaml
search:
    Acme\ContactBunde\Entity\Contact:
        fields:
            - name: firstName
              target_type: text
              target_fields: [name]
            - name: lastName
              target_type: text
              target_fields: [name]
            - name: namePrefix
              target_type: text
              target_fields: [name]
```

If the `target_type` is `text`, the data will also be stored in the `all_data` field
implicitly.

If the `target_fields` option is not given, the data is added to a virtual field whose name is
the name as the field’s name (i.e. what is specified under the `name` key).

### `target_type`

**type**: `string`

The type of the virtual search field (possible values are `datetime`, `double`, `integer`,
and `text`). This option is required.

## `label`

**type**: `string`

A human readable label to identify the entity in the search results. The configured string will be
passed to the translator.

## `mode`

**type**: `string` **default**: normal

The entity behavior for inheritance. For possible values and what they mean, have a look at the
constants of the <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/SearchBundle/Query/Mode.php" target="_blank">Mode</a> class.

<a id="reference-format-search-route-name"></a>

## `route`

**type**: `map`

The route for which a URL is generated when linking from the search result to a concrete entity.
The available options are:

### `name`

**type**: `string`

The name of the route.

### `parameters`

**type**: `map`

The routing parameters, each key is the name of the routing parameter and the value is the name of
one of the configured [fields](#reference-format-search-fields).

## `search_template`

**type**: `string`

## `title_fields`

**type**: `sequence`

Note: Usage of this field is deprecated starting from 2.0. Register an EntityNameProvider instead.
The list of fields to build the title for the result set. The value used here denote to the
[configured fields](#reference-format-search-fields).

<!-- Frontend -->
