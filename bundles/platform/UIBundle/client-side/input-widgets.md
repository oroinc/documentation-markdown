<a id="bundle-docs-platform-ui-bundle-input-widgets"></a>

# Input Widgets

An **input widget** is a widget used for form elements, such as datepicker, uniform, select2, or others.
It provides a unified API for all input widgets, allowing developers to change or remove widgets without modifying the code that interacts with them.

**InputWidgetManager** is used to register input widgets and create a widget for applicable inputs.

**$.fn.inputWidget** is a jQuery API that works with both InputWidgetManager and individual input widgets.

## Example Usage

```javascript
//Create new input widget

var AbstractInputWidget = require('oroui/js/app/views/input-widget/abstract');
var UniformSelectInputWidget = AbstractInputWidget.extend({
    widgetFunctionName: 'uniform',
    refreshOptions: 'update',
    containerClassSuffix: 'select',

    dispose: function() {
        if (this.disposed) {
            return;
        }
        this.$el.uniform.restore();
        UniformSelectInputWidget.__super__.dispose.apply(this, arguments);
    },

    findContainer: function() {
        return this.$el.parent('.selector');
    }
});

//Register widget in InputWidgetManager

var InputWidgetManager = require('oroui/js/input-widget-manager');
InputWidgetManager.addWidget('uniform-select', {
    selector: 'select:not(.no-uniform)',
    Widget: UniformSelectInputWidget
});

//Create widgets for all apllicable inputs

$(':input').inputWidget('create');

/**
* Call function from InputWidget or jQuery.
* See available functions in AbstractInputWidget.overrideJqueryMethods
* Example: will be executed InputWidget.val function, if widget and function exists, or $.val function.
*/
$(':input').inputWidget('val', newValue);
```

## Additional References

You can find more examples in the codebase:

* InputWidgetManager and $.fn.inputWidget with usage examples in comments: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/input-widget-manager.js" target="_blank">oroui/js/input-widget-manager.js</a>
* AbstractInputWidget: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/views/input-widget/abstract.js" target="_blank">oroui/js/app/views/input-widget/abstract</a>
* UniformSelectInputWidget: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/views/input-widget/uniform-select.js" target="_blank">oroui/js/app/views/input-widget/uniform-select</a>
* UniformFileInputWidget: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/views/input-widget/uniform-file.js" target="_blank">oroui/js/app/views/input-widget/uniform-file</a>
* Registration of UniformSelectInputWidget and UniformFileInputWidget in InputWidgetManager: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/modules/input-widgets.js" target="_blank">oroui/js/app/modules/input-widgets</a>

<!-- Frontend -->
