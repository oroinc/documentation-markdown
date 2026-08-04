<a id="customize-datagrid-extensions-toolbar"></a>

# Toolbar Extension

Toolbar options:

```none
[
    'hide'       => false,
    'pageSize'   => [
        'hide'  => false,
        'items' => [10, 25, 50, 100],
        'default_per_page' => 25,
    ],
    'pagination' => [
        'hide' => false,
    ]
];
```

- hide — hides the toolbar. Accepts true or false.
- pageSize — an array that can include:
  - hide — shows or hides the items-per-page selector
  - items — items per page
  - default_per_page — default items per page
- pagination — shows or hides the pagination block and turns off the paginator extension.

**Related Articles**

* [Datagrids](../../../data-grids/index.md#data-grids)
* [Datagrid Configuration Reference](../../../../configuration/yaml/datagrids.md#reference-format-datagrids)
