# Mode Extension

This extension lets you work with the grid in different modes. Two modes are supported:

- **server** (default) — the backend performs all data manipulations, and the grid receives data via AJAX requests.
- **client** — the frontend performs all data manipulations, with no AJAX requests required. Client mode does not currently support filters.

## Configuration example

Oro renders and processes this grid in client mode:

```none
account-account-user-grid:
    options:
        mode: client
    ...
```

**Related Articles**

* [Datagrids](../../../data-grids/index.md#data-grids)
* [Datagrid Configuration Reference](../../../../configuration/yaml/datagrids.md#reference-format-datagrids)
