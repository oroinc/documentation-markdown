<a id="customize-datagrid-extensions-pager"></a>

# Pager Extension

This extension provides pagination and passes the “pager” settings to the view layer.
Paging is currently implemented only for the ORM datasource, where it is always enabled.

## One Page Pagination

This feature renders all grid content on a single page (up to 1000 rows).

To activate it, use the “onePage” option:

```none
account-account-user-grid:
    options:
        toolbarOptions:
            pagination:
                onePage: true
    ...
```

**Related Articles**

* [Datagrids](../../../data-grids/index.md#data-grids)
* [Datagrid Configuration Reference](../../../../configuration/yaml/datagrids.md#reference-format-datagrids)
