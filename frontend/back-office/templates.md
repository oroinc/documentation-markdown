# Templates (Twig)

OroPlatform-based application uses the Twig templating engine to render the content.

See the detailed documentation in:
: - <a href="https://symfony.com/doc/5.4/templating.html" target="_blank">Creating and Using Templates article in a Symfony Documentation</a>
  - <a href="https://twig.symfony.com/" target="_blank">Twig official documentation</a>

#### SEE ALSO
[Front-rendered Underscore.js Templates](../javascript/index.md#frontend-architecture-js-templates)

## Find Twig Templates

To find the Twig template file and Twig block that is used for rendering
specific block of a content, you can use <a href="https://github.com/oroinc/twig-inspector/blob/master/Bundle/Resources/doc/usage.md" target="_blank">Twig Inspector</a>. The inspector enables
you to navigate instantly from a Browser to the Twig template that opens automatically in a PhpStorm.

## Override Twig Templates

You can override one of the platform templates by adding a template
to the same path under `templates/bundles`.
For example, to override the `Grid/widget/widget.html.twig` template
from the DataGridBundle, create a new template file located at
`templates/bundles/OroDataGridBundle/Grid/widget/widget.html.twig`.

<!-- Frontend -->
