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
| product_page_template      | A single field is used to choose one<br/>page template from a list (static<br/>values: default, tabs, wide).                                                           |
| quick_access_button_config | A multi-purpose field is used to<br/>represent QuickAccessButton settings.<br/>Previews depend on type field values<br/>(menu, web_catalog_node).                      |
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
