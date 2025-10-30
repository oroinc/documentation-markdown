<a id="bundle-docs-platform-ui-bundle-input-widgets"></a>

# Input Widgets

An input widget is a widget used for form elements, such as datepicker, uniform, select2, or others.

An **input widget** is used to provide a common API for all input widgets.
By using this API, you provide the ability to change the input widget to any other or remove it without changing the code that interacts with the widget.

**InputWidgetManager** is used to register input widgets and create a widget for applicable inputs.

**$.fn.inputWidget** - is a jQuery API for InputWidgetManager or InputWidget.

**Example of usage:**

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

Your can see more examples in code:

* InputWidgetManager and $.fn.inputWidget with examples in comments: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/input-widget-manager.js" target="_blank">oroui/js/input-widget-manager.js</a>
* AbstractInputWidget: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/views/input-widget/abstract.js" target="_blank">oroui/js/app/views/input-widget/abstract</a>
* UniformSelectInputWidget: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/views/input-widget/uniform-select.js" target="_blank">oroui/js/app/views/input-widget/uniform-select</a>
* UniformFileInputWidget: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/views/input-widget/uniform-file.js" target="_blank">oroui/js/app/views/input-widget/uniform-file</a>
* Register UniformSelectInputWidget and UniformFileInputWidget in InputWidgetManager: <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/modules/input-widgets.js" target="_blank">oroui/js/app/modules/input-widgets</a>

<!-- Frontend -->
