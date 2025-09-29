# Rich Text Form Type

Rich Text editor is based on <a href="https://www.tinymce.com/" target="_blank">TinyMCE</a>.

## HTML Purifier

Rich Text editor uses <a href="http://htmlpurifier.org/docs" target="_blank">HTML Purifier</a> which helps to prevent XSS attacks.
List of allowed HTML tags you can find <a href="https://github.com/oroinc/platform/blob/4.2/src/Oro/Bundle/FormBundle/Resources/config/oro/app.yml" target="_blank">in the app.yml file</a>.

The following is an example of how to allow own HTML tags:

*src/Acme/Bundle/DemoBundle/Resources/config/oro/app.yml*
```yaml
 oro_form:
     html_purifier_modes:
         default:
             allowed_html_elements:
                 div:
                     attributes:
                         - data-url
                         - data-src
                         - data-value
```

<!-- Frontend -->
