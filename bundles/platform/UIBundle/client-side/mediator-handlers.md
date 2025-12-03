<a id="bundle-docs-platform-ui-bundle-mediator-handlers"></a>

# Mediator Handlers

OroUIBundle provides a set of mediator handlers.
Following the Chaplin architecture, it is recommended to execute actions indirectly using mediator.execute() in all components.

## Application

| Handler Name    | Description                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------|
| retrieveOption  | Returns an application’s initialization option by its name                                              |
| retrievePath    | Removes the root prefix from a given path and returns the meaningful part                               |
| combineRouteUrl | Combines path and query parts to generate a URL                                                         |
| combineFullUrl  | Combines path and query parts into a full URL including root prefix                                     |
| changeURL       | Changes the URL using Backbone.history.navigate with route and options, without dispatching a new route |

#### SEE ALSO
See the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/application.js" target="_blank">oroui/js/app/application</a> module for details.

## Page Controller

| Handler Name   | Description                                                                                                          |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| isInAction     | Detects whether the controller is currently in an action (between ‘page:beforeChange’ and ‘page:afterChange’ events) |
| redirectTo     | Performs a redirect to a new location; accepts an object with location info and navigation options                   |
| refreshPage    | Reloads the current page with optional navigation options                                                            |
| submitPage     | Submits a form action via the model’s save method; accepts an options object with data                               |

#### SEE ALSO
See the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/controllers/page-controller.js" target="_blank">oroui/js/app/controllers/page-controller</a> module for details.

## Messenger

| Handler Name     | Description                        |
|------------------|------------------------------------|
| addMessage       | messenger.addMessage               |
| showMessage      | messenger.notificationMessage      |
| showFlashMessage | messenger.notificationFlashMessage |
| showErrorMessage | messenger.showErrorMessage         |

#### SEE ALSO
See the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/messenger.js" target="_blank">oroui/js/messenger</a> module for details.

## Widgets (Widget Manager)

| Handler Name            | Method                                 | Description                                           |
|-------------------------|----------------------------------------|-------------------------------------------------------|
| widgets:getByIdAsync    | widgetManager.getWidgetInstance        | Asynchronously fetches a widget instance by its ID    |
| widgets:getByAliasAsync | widgetManager.getWidgetInstanceByAlias | Asynchronously fetches a widget instance by its alias |

#### SEE ALSO
See the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/UIBundle/Resources/public/js/widget/widget-manager.js" target="_blank">oroui/js/widget-manager</a> module for details.

## PageLoadingMaskView

| Handler Name   | Description               |
|----------------|---------------------------|
| showLoading    | Displays the loading mask |
| hideLoading    | Hides the loading mask    |

## Layout

| Handler Name   | Description                                                      |
|----------------|------------------------------------------------------------------|
| layout:init    | Initializes widgets and plugins inside the container             |
| layout:dispose | Removes widgets and plugins from child elements of the container |
<!-- Frontend -->
