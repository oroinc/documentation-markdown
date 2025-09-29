# JavaScript

Javascript in OroCommerce has a modular architecture based on Chaplin and Backbone.

#### SEE ALSO
[JavaScript Frontend Architecture](../javascript/index.md#dev-doc-frontend-javascript) covers the client-side architecture of
OroPlatform-based applications including OroCommerce.

This section provides configuration reference for the Webpack library to enable a modular structure of JS components in Oro
applications.

## JS Modules Definition

JS modules configuration file should be placed in the
Resources/views/layouts/{theme_name}/config folder and named jsmodules.yml, for
example DemoBundle/Resources/views/layouts/base/config/jsmodules.yml.

Default entry point for Webpack build is oroui/js/app.
But you can change it by providing the same alias to the necessary entry point
or configuring the **entry** section in the jsmodules.yml file.

**Example:**

```yaml
# src/Acme/Bundle/DemoBundle/Resources/views/layouts/base/config/jsmodules.yml
entry:
    app:
        - oroui/js/app
        - oroui/js/app/services/app-ready-load-modules
shim:
    jquery:
        expose:
            - $
            - jQuery
    jquery.form:
        imports:
            - jQuery=jquery
map:
    '*':
        'jquery': 'oroui/js/jquery-extend'
    'oroui/js/jquery-extend':
        'jquery': 'jquery'
aliases:
    'jquery$': 'oroui/lib/jquery-1.10.2'
    'jquery-ui$': 'oroui/lib/jquery-ui.min'
    'oroui/js/app$': 'acmedemo/js/app'
```
