<a id="customize-datagrids-extensions-action"></a>

# Action Extension

This extension configures actions for the datagrid. Add action types and place their configuration under the `actions` node.

## Actions

type is a required option for the action configuration. To control access to an action, add the optional `acl_resource` node to it.

### Ajax

Ajax performs an ajax call by the given URL.

```yaml
action_name:
    type: ajax
    link: PROPERTY_WITH_URL # required
```

### Delete

Delete performs the DELETE ajax request by the given URL.

```yaml
action_name:
    type: delete
    link: PROPERTY_WITH_URL  # required
    confirmation: true|false # should confirmation window be shown
```

### Navigate

Navigate performs redirects by the given URL.

```yaml
action_name:
    type: navigate
    link: PROPERTY_WITH_URL  # required
```

**Related Articles**

* [Datagrids](../../../data-grids/index.md#data-grids)
* [Datagrid Configuration Reference](../../../../configuration/yaml/datagrids.md#reference-format-datagrids)
