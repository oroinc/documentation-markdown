<a id="customize-datagrid-extensions-inline-editing"></a>

# Inline Editing

## Enable Inline Editing on a Grid

To enable inline editing on a grid, do the following:

- Go to the datagrid yml
- Add the following lines into the datagrid configuration

```yaml
datagrids:
    {grid-uid}:
        # <grid configuration> goes here
        inline_editing:
            enable: true
        save_api_accessor:
            http_method: PATCH
            route: oro_account_update
```

- Open the corresponding page, all the columns for which the frontend type supports inline editing will become editable

## Datagrid Configuration Details

```yaml
datagrids:
    {grid-uid}:
        inline_editing:
            enable: true
            acl_resource: custom_acl_resource
            entity_name: Oro\Bundle\UserBundle\Entity\User
            behaviour: enable_all
            plugin: orodatagrid/js/app/plugins/grid/inline-editing-plugin
            default_editors: orodatagrid/js/default-editors
            cell_editor:
                component: orodatagrid/js/app/components/cell-popup-editor-component
                component_options:
                    {key}: {value}
            save_api_accessor:
                # api accessor options
                {key}: {value}
```

| Options name      | Default value                                                              | Description                                                                                                                                                                                                                       |
|-------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| enable            | false                                                                      | Marks or unmarks this column as editable. The behavior depends on main inline_editing.behavior: enable_all - false will disable editing this cell. enable_selected - true will enable editing this cell.                          |
| acl_resource      |                                                                            | Enables inline editing if access granted to specified resource. By default is checked EDIT permission to specified entity                                                                                                         |
| entity_name       |                                                                            | Entity class name for saving data. By default it tries to get value from extended_entity_name                                                                                                                                     |
| behavior          | enable_all                                                                 | Specifies the way to enable the inline editing. Possible values: enable_all - (default). this will enable inline editing where possible. enable_selected - disable by default, enable only on configured cells                    |
| plugin            | `orodatagrid/js/app/plugins/grid/inline-editing-plugin`                    | Specifies the plugin realization                                                                                                                                                                                                  |
| default_editors   | `orodatagrid/js/default-editors`                                           | Specifies default editors for front-end types                                                                                                                                                                                     |
| cell_editor       | `{component: 'orodatagrid/js/app/components/cell-popup-editor-component'}` | Specifies default cell_editor_component and their options                                                                                                                                                                         |
| save_api_accessor | `{class: 'oroui/js/tools/api-accessor'}`                                   | Required. Describes the way to send update request. Please see [documentation](../../../../../bundles/platform/UIBundle/client-side/api-accessor.md#bundle-docs-platform-ui-bundle-apiaccessor) for `oroui/js/tools/api-accessor` |

**Sample usage of the save_api_accessor with full options provided**

```yaml
save_api_accessor:
    route: oro_opportunity_task_update # for example this route uses following mask
        # to generate url /api/opportunity/{opportunity_id}/tasks/{id}
    http_method: POST
    headers:
        Api-Secret: ANS2DFN33KASD4F6OEV7M8
    default_route_parameters:
        opportunity_id: 23
    action: patch
    query_parameter_names: [action]
```

Result of the combined options: `/api/opportunity/23/tasks/{id}?action=patch`

Please note that `{id}` will be taken from the current row in the grid.

## Column Configuration Options

```yaml
datagrids:
    {grid-uid}:
        # <grid configuration> goes here
        columns:
            {column-name}:
                inline_editing:
                    enable: true
                    save_api_accessor:
                        # see main save_api_accessor, additonally supports field_name option
                        # which allows to override field name that sent to server
                        # {<field_name>: <new_value>}
                    editor:
                        component: my-bundle/js/app/components/cell-editor-component
                        component_options:
                            {key}: {value}
                        view: my-bundle/js/app/views/my-cell-editor-view
                        view_options:
                            {key}: {value}
                    autocomplete_api_accessor:
                        # configure autocomplete api accessor
                        # for example
                        # class: oroui/js/tools/search-api-accessor
```

| Options name              | Default value   | Description                                                                                                                                                                                                                                         |
|---------------------------|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| enable                    |                 | Marks or unmarks this column as editable. The behavior depends on main inline_editing.behavior: `enable_all` - false will disable editing this cell. `enable_selected` - true will enable editing this cell.                                        |
| save_api_accessor         |                 | Allows to override default api accessor for the whole grid. Please see [documentation for oroui/js/tools/api-accessor](../../../../../bundles/platform/UIBundle/client-side/api-accessor.md#bundle-docs-platform-ui-bundle-apiaccessor) for details |
| editor.component          |                 | Allows to override component used to display view and specified in `datagrid.{grid-uid}.inline_editing.cell_editor.component`                                                                                                                       |
| editor.component_options  | {}              | Specifies options to pass into the cell editor component                                                                                                                                                                                            |
| editor.view               |                 | Defines view that used to render cell-editor. By default, this view is selected using `datagrid.{grid-uid}.inline_editing.default_editors` file.                                                                                                    |
| editor.view_options       | {}              | Specifies options to pass into the cell editor view                                                                                                                                                                                                 |
| autocomplete_api_accessor |                 | Allow use autocomplete to fill select2 edit form                                                                                                                                                                                                    |

## Frontend Special Types

frontend_type: select - simple choice from provided values

Example:

```yaml
datagrids:
    {grid-uid}:
        # <grid configuration> goes here
        columns:
            {column-name}:
                frontend_type: select
                inline_editing:
                    enable: true
                    editor:
                        view: oroform/js/app/views/editor/select-editor-view
                    autocomplete_api_accessor:
                        class: oroui/js/tools/search-api-accessor
                choices: # can be used service as data provider @service->getDataMethod
                    {key}: {value}
```

frontend_type: multi-select - simple choice from provided values allow choose few values

Example:

```yaml
datagrids:
    {grid-uid}:
        # <grid configuration> goes here
        columns:
            {column-name}:
                frontend_type: multi-select
                inline_editing:
                    enable: true
                    editor:
                        view: oroform/js/app/views/editor/multi-select-editor-view
                    autocomplete_api_accessor:
                        class: oroui/js/tools/search-api-accessor
                choices: # can be used service as data provider @service->getDataMethod
                    {key}: {value}
```

frontend_type: relation - select2 type with autocomplete search function

Example:

```yaml
datagrids:
    {grid-uid}:
        # <grid configuration> goes here
        columns:
            {column-name}:
                frontend_type: relation
                inline_editing:
                    enable: true
                    editor:
                        view: oroform/js/app/views/editor/related-id-relation-editor-view
                    autocomplete_api_accessor:
                        class: oroui/js/tools/search-api-accessor
```

frontend_type: multi-relation - select2 type with autocomplete search function and allow multiple choices

Example:

```yaml
datagrids:
    {grid-uid}:
        # <grid configuration> goes here
        columns:
            {column-name}:
                frontend_type: multi-relation
                inline_editing:
                    enable: true
                    editor:
                        view: oroform/js/app/views/editor/multi-relation-editor-view
                    autocomplete_api_accessor:
                        class: oroui/js/tools/search-api-accessor
```

## Mapping Default Frontend Type and Editor

| Frontend type   | Editor view                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| string          | [TextEditorView](../../../../../bundles/platform/FormBundle/editor/text-editor-view.md#bundle-docs-platform-form-bundle-edit-text-editor-view)                                       |
| phone           | [TextEditorView](../../../../../bundles/platform/FormBundle/editor/text-editor-view.md#bundle-docs-platform-form-bundle-edit-text-editor-view)                                       |
| datetime        | [DatetimeEditorView](../../../../../bundles/platform/FormBundle/editor/datetime-editor-view.md#bundle-docs-platform-form-bundle-edit-date-time-editor-view)                          |
| date            | [DateEditorView](../../../../../bundles/platform/FormBundle/editor/date-editor-view.md#bundle-docs-platform-form-bundle-edit-date-editor-view)                                       |
| currency        | [NumberEditorView](../../../../../bundles/platform/FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view)                                      |
| number          | [NumberEditorView](../../../../../bundles/platform/FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view)                                      |
| integer         | [NumberEditorView](../../../../../bundles/platform/FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view)                                      |
| decimal         | [NumberEditorView](../../../../../bundles/platform/FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view)                                      |
| percent         | [PercentEditorView](../../../../../bundles/platform/FormBundle/editor/percent-editor-view.md#bundle-docs-platform-form-bundle-percent-editor-view)                                   |
| select          | [SelectEditorView](../../../../../bundles/platform/FormBundle/editor/select-editor-view.md#bundle-docs-platform-form-bundle-edit-select-editor-view)                                 |
| multi-select    | [MultiSelectEditorView](../../../../../bundles/platform/FormBundle/editor/multi-select-editor-view.md#bundle-docs-platform-form-bundle-multi-select-editor-view)                     |
| relation        | [RelatedIdRelationEditorView](../../../../../bundles/platform/FormBundle/editor/related-id-relation-editor-view.md#bundle-docs-platform-form-bundle-related-id-relation-editor-view) |
| multi-relation  | [MultiRelationEditorView](../../../../../bundles/platform/FormBundle/editor/multi-relation-editor-view.md#bundle-docs-platform-form-bundle-multi-relation-editor-view)               |

Taken from [default-editors](../../../../../bundles/platform/DataGridBundle/default-editors.md#bundle-docs-platform-datagrid-default-editors).

## Supported Editors

| Editor                                                                                                                                                                               | Description                                                                       |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| [TextEditorView](../../../../../bundles/platform/FormBundle/editor/text-editor-view.md#bundle-docs-platform-form-bundle-edit-text-editor-view)                                       | Editing text/phone cells                                                          |
| [NumberEditorView](../../../../../bundles/platform/FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view)                                      | Editing number/integer/decimal/currency cells                                     |
| [PercentEditorView](../../../../../bundles/platform/FormBundle/editor/percent-editor-view.md#bundle-docs-platform-form-bundle-percent-editor-view)                                   | Editing percent  cells                                                            |
| [DateEditorView](../../../../../bundles/platform/FormBundle/editor/date-editor-view.md#bundle-docs-platform-form-bundle-edit-date-editor-view)                                       | Editing date cells                                                                |
| [DatetimeEditorView](../../../../../bundles/platform/FormBundle/editor/datetime-editor-view.md#bundle-docs-platform-form-bundle-edit-date-time-editor-view)                          | Editing datetime cells                                                            |
| [SelectEditorView](../../../../../bundles/platform/FormBundle/editor/select-editor-view.md#bundle-docs-platform-form-bundle-edit-select-editor-view)                                 | Editing select cells (predefined choices)                                         |
| [RelatedIdSelectEditorView](../../../../../bundles/platform/FormBundle/editor/related-id-select-editor-view.md#bundle-docs-platform-form-bundle-related-id-select-editor-view)       | Editing cells which already contain label (and no value) using predefined choices |
| [RelatedIdRelationEditorView](../../../../../bundles/platform/FormBundle/editor/related-id-relation-editor-view.md#bundle-docs-platform-form-bundle-related-id-relation-editor-view) | Editing cells which already contain label (and no value) using search api         |
| [MultiRelationEditorView](../../../../../bundles/platform/FormBundle/editor/multi-relation-editor-view.md#bundle-docs-platform-form-bundle-multi-relation-editor-view)               | Editing cells with specific format, for many to one relations                     |
| [MultiSelectEditorView](../../../../../bundles/platform/FormBundle/editor/multi-select-editor-view.md#bundle-docs-platform-form-bundle-multi-select-editor-view)                     | Editing cells with specific format, for multiselect field                         |

## Supported Search API’s for `related-id-relation-editor-view`

Please find the list of supported search APIs in the [Search APIs section](../../../../../bundles/platform/FormBundle/search-apis.md#bundle-docs-platform-form-bundle-search-apis).

<!-- Frontend -->
