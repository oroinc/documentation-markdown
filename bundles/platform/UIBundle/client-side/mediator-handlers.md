<a id="bundle-docs-platform-ui-bundle-mediator-handlers"></a>

# Mediator Handlers

OroUIBundle declares some mediator handlers. It’s preferable to use indirect method execution with mediator.execute() in all components which follows Chaplin architecture.

## Application

| Handler Name    | Description                                                                                                 |
|-----------------|-------------------------------------------------------------------------------------------------------------|
| retrieveOption  | Returns application’s initialization option by its name                                                     |
| retrievePath    | Removes root prefix from passed path and returns meaningful part of path                                    |
| combineRouteUrl | Accepts path and query parts and combines url                                                               |
| combineFullUrl  | Accepts path and query parts and combines full url (with root prefix)                                       |
| changeURL       | Accepts route and options for Backbone.history.navigate, allows to change url without dispatching new route |

#### SEE ALSO
See <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/application.js" target="_blank">oroui/js/app/application</a> module for details.

## Page Controller

| Handler Name   | Description                                                                                                            |
|----------------|------------------------------------------------------------------------------------------------------------------------|
| isInAction     | Allows to detect if controller is in action (period of time between ‘page:beforeChange’ and ‘page:afterChange’ events) |
| redirectTo     | Perform redirect to a new location, accepts two parameters: object with location information and navigation options    |
| refreshPage    | Reloads current page, accepts navigation options                                                                       |
| submitPage     | Performs submit form action via save call for a model, accepts options object with packed in data                      |

#### SEE ALSO
See <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/UIBundle/Resources/public/js/app/controllers/page-controller.js" target="_blank">oroui/js/app/controllers/page-controller</a> module for details

## Messenger

| Handler Name     | Description                        |
|------------------|------------------------------------|
| addMessage       | messenger.addMessage               |
| showMessage      | messenger.notificationMessage      |
| showFlashMessage | messenger.notificationFlashMessage |
| showErrorMessage | messenger.showErrorMessage         |

#### SEE ALSO
See <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/UIBundle/Resources/public/js/messenger.js" target="_blank">oroui/js/messenger</a> module for details

## Widgets (Widget Manager)

| Handler Name            | Method                                 | Description                                         |
|-------------------------|----------------------------------------|-----------------------------------------------------|
| widgets:getByIdAsync    | widgetManager.getWidgetInstance        | Asynchronously fetches widget instance by widget id |
| widgets:getByAliasAsync | widgetManager.getWidgetInstanceByAlias | Asynchronously fetches widget instance its alias    |

#### SEE ALSO
See <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/UIBundle/Resources/public/js/widget/widget-manager.js" target="_blank">oroui/js/widget-manager</a> module for details

## PageLoadingMaskView

| Handler Name   | Description        |
|----------------|--------------------|
| showLoading    | Shows loading mask |
| hideLoading    | Hides loading mask |

## Layout

| Handler Name   | Description                                                           |
|----------------|-----------------------------------------------------------------------|
| layout:init    | Initializes proper widgets and plugins in the container               |
| layout:dispose | Removes some plugins and widgets from child elements of the container |
<!-- Frontend -->
