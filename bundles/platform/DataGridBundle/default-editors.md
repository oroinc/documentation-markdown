<a id="bundle-docs-platform-datagrid-default-editors"></a>

# Default Editors

A technical reference to how JS renders different field types when using [inline editing views](../../../backend/entities/customize-datagrids/backend/extensions/inline-editing.md#customize-datagrid-extensions-inline-editing).

## defaultEditors : `Object`

Maps frontend types to editor views:

* defaultEditors: Object
  * .string: function
  * .phone: function
  * .datetime: function
  * .date: function
  * .currency: function
  * .number: function
  * .integer: function
  * .decimal: function
  * .percent: function
  * .select: function

### defaultEditors.string: `function`

See [TextEditorView](../FormBundle/editor/text-editor-view.md#bundle-docs-platform-form-bundle-edit-text-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.phone:  `function`

Please see [TextEditorView](../FormBundle/editor/text-editor-view.md#bundle-docs-platform-form-bundle-edit-text-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.datetime: function

Please see [DatetimeEditorView](../FormBundle/editor/datetime-editor-view.md#bundle-docs-platform-form-bundle-edit-date-time-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.date: `function`

Please see [DateEditorView](../FormBundle/editor/date-editor-view.md#bundle-docs-platform-form-bundle-edit-date-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.currency : `function`

Please see [NumberEditorView](../FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.number: `function`

Please see [NumberEditorView](../FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.integer: `function`

Please see [NumberEditorView](../FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.decimal: `function`

Please see [NumberEditorView](../FormBundle/editor/number-editor-view.md#bundle-docs-platform-form-bundle-number-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.percent: `function`

Please see [PercentEditorView](../FormBundle/editor/percent-editor-view.md#bundle-docs-platform-form-bundle-percent-editor-view) for details.

**Kind**: static property of defaultEditors.

### defaultEditors.select: `function`

Please see [SelectEditorView](../FormBundle/editor/select-editor-view.md#bundle-docs-platform-form-bundle-edit-select-editor-view) for details.

**Kind**: static property of defaultEditors.
