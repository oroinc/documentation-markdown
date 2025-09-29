<a id="bundle-docs-platform-ui-bundle-hidden-initialization-view"></a>

# HiddenInitializationView ⇐ BaseView

* **Extends:** BaseView
* **Kind**: global class

## new HiddenInitializationView()

View allows to hide part of the DOM tree until all page components are initialized.

Usage sample:

#### NOTE
Keep in mind that all div’s attributes are required for valid work.

```html
<div class="invisible"
        data-page-component-module="oroui/js/app/components/view-component"
        data-page-component-options="{'view': 'oroui/js/app/views/hidden-initialization-view'}"
        data-layout="separate">
    <!-- write anything here -->
</div>
```
