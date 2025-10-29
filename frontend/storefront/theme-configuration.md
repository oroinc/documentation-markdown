<a id="dev-doc-frontend-theme-configuration"></a>

# Theme Configuration

**Theme Configuration** is the feature that allows theme developers to make a storefront theme configurable by a store owner.

The theme developers can include a list of the supported configuration options and available values.

The store owners can apply the theme configuration settings on various levels.

## Theme Configuration Definition

To define theme configuration options, it is enough to add the **configuration** section in the theme configuration file, for example, DemoBundle/Resources/views/layouts/first_theme/theme.yml.

A **theme configuration**

* options are organized into **sections**
* section identifiers must be unique within the theme in which they are defined
* each section must have a **label** as well (required, cannot be empty)
* options must have **type** and **label** (required, cannot be empty)

The theme configuration has the following option types:

| Type                       | Description                                                                                                                                                            |
|----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| checkbox                   | A single input field with two static<br/>values: checked and unchecked.                                                                                                |
| select                     | A multi-purpose field is used to<br/>choose one or more defined options<br/>from a drop-down list.                                                                     |
| radio                      | A single radio button is used to<br/>choose one defined option from group.                                                                                             |
| menu_selector              | A single field is used to choose one<br/>menu name from a list. The menu names<br/>are provided dynamically.                                                           |
| content_block_selector     | A single field is used to choose one<br/>content block from a list. The block<br/>names are provided dynamically.<br/>Previews keys depend on content block<br/>alias. |
| content_widget_selector    | A single field is used to choose one<br/>content widget from a list. The names<br/>are provided dynamically. Previews<br/>keys depend on content widget names.         |
| product_page_template      | A single field is used to choose one<br/>page template from a list (static<br/>values: default, tabs, wide).                                                           |
| quick_access_button_config | A multi-purpose field is used to<br/>represent QuickAccessButton settings.<br/>Previews depend on type field values<br/>(menu, web_catalog_node).                      |
| css_background             | A multi field is used to<br/>represent CssBackgroundConfigBuilder<br/>settings.                                                                                        |
| css_border_radius          | A multi field is used to represent<br/>CssBorderRadiusConfigBuilder<br/>settings.                                                                                      |
| css_box_shadow             | A multi field is used to<br/>represent CssBoxShadowConfigBuilder<br/>settings.                                                                                         |
| css_color                  | A multi field is used to<br/>represent CssColorConfigBuilder<br/>settings.                                                                                             |
| css_font_size              | A multi field is used to<br/>represent CssFontSizeConfigBuilder<br/>settings.                                                                                          |
| css_gap                    | A multi field is used to<br/>represent CssGapConfigBuilder<br/>settings.                                                                                               |
| css_background             | A multi field is used to<br/>represent CssBackgroundConfigBuilder<br/>settings.                                                                                        |
| css_length                 | A multi field is used to<br/>represent CssLengthConfigBuilder<br/>settings.                                                                                            |
| css_line_height            | A multi field is used to<br/>represent CssLineHeightConfigBuilder<br/>settings.                                                                                        |
| css_min_height             | A multi field is used to<br/>represent CssMinHeightConfigBuilder<br/>settings.                                                                                         |
| css_outline                | A multi field is used to<br/>represent CssOutlineConfigBuilder<br/>settings.                                                                                           |
| css_padding                | A multi field is used to<br/>represent CssPaddingConfigBuilder<br/>settings.                                                                                           |
| integer                    | An input field looks like a text box<br/>and accepts only integer numbers.                                                                                             |
| number                     | An input field looks like a text box<br/>and accepts numbers. This type has<br/>options for the scale and rounding.                                                    |
| text                       | An input field represents the most<br/>basic text field.                                                                                                               |

The theme configuration has the following option parameters:

| Option   | Description                                                                               | Required   |
|----------|-------------------------------------------------------------------------------------------|------------|
| label    | The label is displayed in<br/>the admin panel for a option<br/>in theme configuration UI. | yes        |
| type     | The type of the option in<br/>theme configuration UI.                                     | yes        |
| default  | The value is displayed by<br/>default.                                                    | no         |
| values   | Available option values.                                                                  | no         |
| attr     | Attributes to be added to<br/>the form field HTML tag.                                    | no         |
| options  | Options to be added to the<br/>form field.                                                | no         |
| previews | Images that will illustrate<br/>UI changes if this option<br/>is selected.                | no         |

**Example:**

```yaml
#DemoBundle/Resources/views/layouts/first_theme/theme.yml
configuration:
    sections:
        header:
            label: Header
            options:
                header_menu:
                    label: Header Menu
                    type: checkbox
                    default: unchecked
                    options:
                        required: false
                    previews:
                        checked: 'path/to/image/checked.png'
                        unchecked: 'path/to/image/unchecked.png'
        general:
            label: General
            options:
                screen:
                    label: Screen
                    type: select
                    values:
                        integrated: Integrated
                        standalone: Standalone
                    previews: []
                filters_position:
                    label: Filters Position
                    type: radio
                    default: top
                    values:
                        top: top
                        sidebar: sidebar
                negative_number:
                    label: Negative Number
                    type: number
                    default: -2.35
                    options:
                        constraints: [] # overrides the default PositiveOrZero constraint
```

#### NOTE
Translation keys can be used for the **labels** section, and the **labels** and **values** options.
Also, if preview images are defined in the DemoBundle/Resources/public/images directory, make sure they are in the project’s public directory.

#### NOTE
For default previews and options when they don’t have images, the reserved preview key \_default can be used.

## Theme Configuration Validation

To validate theme configuration options, use the following command:

```none
bin/console oro:theme:configuration:validate
```

## How-To Guides

### Problem 1

*I want to forbid deleting entities that are stored in the theme configuration as a value of option.*

**Solution**:

> ```yaml
> services:
>     oro_cms.acl.voter.content_widget:
>         class: Oro\Bundle\ThemeBundle\Acl\Voter\ThemeConfigurationDependencyDeleteVoter
>         arguments:
>             - '@oro_entity.doctrine_helper'
>             - '@oro_theme.provider.theme_configuration'
>             - 'content_widget_selector'
>         calls:
>             - [setClassName, ['Oro\Bundle\CMSBundle\Entity\ContentWidget']]
>         tags:
>             - { name: security.voter }
> ```
