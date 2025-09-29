<a id="bundle-docs-platform-form-bundle-edit-select-editor-view"></a>

# SelectEditorView ⇐ TextEditorView

Select cell content editor. The cell value should be a value field.
The grid will render a corresponding label from the options.choices map.
The editor will use the same mapping

Column configuration examples:

```yaml
datagrids:
  {grid-uid}:
    inline_editing:
      enable: true
    # <grid configuration> goes here
    columns:
      # Sample 1. Mapped by frontend type
      {column-name-1}:
        frontend_type: select
        choices: # required
          key-1: First
          key-2: Second
      # Sample 2. Full configuration
      {column-name-2}:
        choices: # required
          key-1: First
          key-2: Second
        inline_editing:
          editor:
            view: oroform/js/app/views/editor/select-editor-view
            view_options:
              placeholder: '<placeholder>'
              css_class_name: '<class-name>'
          validation_rules:
            NotBlank: ~
          save_api_accessor:
              route: '<route>'
              query_parameter_names:
                 - '<parameter1>'
                 - '<parameter2>'
```

## Options in YML

| Column Option Name                                 | Description                                                                                                                                |
|----------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| choices                                            | Key-value set of available choices                                                                                                         |
| inline_editing.editor.view_options.placeholder     | Optional. Placeholder translation key for an empty element                                                                                 |
| inline_editing.editor.view_options.key_type        | Optional. Specifies type of value that should be sent to server. Currently string/boolean/number key types are supported.                  |
| inline_editing.editor.view_options.placeholder_raw | Optional. Raw placeholder value                                                                                                            |
| inline_editing.editor.view_options.css_class_name  | Optional. Additional css class name for editor view DOM element                                                                            |
| inline_editing.validation_rules                    | Optional. Validation rules. See [JS Validation](../js-validation.md#bundle-docs-platform-form-bundle-js-validation-server-side-validation) |
| inline_editing.save_api_accessor                   | Optional. Sets accessor module, route, parameters etc.                                                                                     |

## Constructor Parameters

**Extends:** TextEditorView

| Param                   | Type   | Description                                                                                                                       |
|-------------------------|--------|-----------------------------------------------------------------------------------------------------------------------------------|
| options                 | Object | Options container                                                                                                                 |
| options.model           | Object | Current row model                                                                                                                 |
| options.fieldName       | string | Field name to edit in model                                                                                                       |
| options.className       | string | CSS class name for editor element                                                                                                 |
| options.placeholder     | string | Placeholder translation key for an empty element                                                                                  |
| options.placeholder_raw | string | Raw placeholder value. It overrides placeholder translation key                                                                   |
| options.validationRules | Object | Validation rules.  See [JS Validation](../js-validation.md#bundle-docs-platform-form-bundle-js-validation-server-side-validation) |
| options.choices         | Object | Key-value set of available choices                                                                                                |
* SelectEditorView ⇐ [TextEditorView](text-editor-view.md#bundle-docs-platform-form-bundle-edit-text-editor-view)
  * .getSelect2Options() ⇒ Object
  * .getSelect2Data() ⇒ Object
  * .onFocusout(e)
  * .isFocused() ⇒ boolean
  * .getServerUpdateData() ⇒ Object

## selectEditorView.getSelect2Options() ⇒ Object

Prepares and returns Select2 options

**Kind**: instance method of SelectEditorView

## selectEditorView.getSelect2Data() ⇒ Object

Returns Select2 data from corresponding element

**Kind**: instance method of SelectEditorView

## selectEditorView.onFocusout(e)

Handles focusout event

**Kind**: instance method of SelectEditorView

| Param   | Type         |
|---------|--------------|
| e       | jQuery.Event |

## selectEditorView.isFocused() ⇒ boolean

Returns true if element is focused

**Kind**: instance method of SelectEditorView

## selectEditorView.getServerUpdateData() ⇒ Object

Returns data which should be sent to the server

**Kind**: instance method of SelectEditorView
