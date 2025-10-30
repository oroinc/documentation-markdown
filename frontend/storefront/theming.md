<a id="dev-doc-frontend-layouts-theming"></a>

# Themes

A **theme** is a collection of files that declares a visual
presentation for a group of pages. You can think of a **theme** as the skin for your application.

Files that the theme consists of are [layout updates](layouts/index.md#dev-doc-frontend-layouts-layout-updates),
**styles**, **scripts**, and anything else related to the look and feel of the page.

Out-of-the-box, OroCommerce comes with [one(default) theme: default](#dev-doc-frontend-layouts-theming).

We recommend creating your own theme if you want to customize an out-of-the-box OroCommerce storefront. To create your own theme, you have to choose the default theme as the parent for your own.

You can customize the core theme, but creating your own theme will enable you to switch to the core theme with a few clicks conveniently.

<a id="dev-doc-frontend-layouts-theming-definition"></a>

## Theme Definition

To define a new theme, it is enough to **create a theme configuration file** in the **theme folder**.

A **theme folder**

* must have a unique name
* must match the **[a-zA-Z][a-zA-Z0-9_-:]\*** pattern
* must be placed in the **Resources/views/layouts** folder of the bundle

An example of a theme folder is DemoBundle/Resources/views/layouts/first_theme/.

The theme folder name becomes the theme ID.

The **theme configuration file** should be placed in the theme folder and named **theme.yml**, for example,
DemoBundle/Resources/views/layouts/first_theme/theme.yml.

The **allowed options in the theme configuration** file are the following:

| Option            | Description                                                                                                                                 | Required   | Inherits   |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------|------------|
| label             | The label is displayed in<br/>the theme management UI.                                                                                      | yes        | no         |
| description       | The description is displayed<br/>in the theme selection UI.                                                                                 | no         | no         |
| parent            | Parent theme identifier                                                                                                                     | no         | no         |
| groups            | Group name or names for<br/>which it is applicable. Use<br/>`commerce` group for an<br/>OroCommerce application                             | no         | no         |
| logo              | The logo is displayed<br/>in the UI.                                                                                                        | no         | no         |
| logo_small        | The small logo is displayed<br/>on small screens in the UI<br/>and also in a burger menu.                                                   | no         | no         |
| rtl_support       | Defines whether Theme<br/>supports RTL and additional<br/>\*.rtl.cssfiles<br/>have to be build                                              | no         | no         |
| icon              | The icon is displayed<br/>in the UI.                                                                                                        | no         | no         |
| favicons_path     | The path to favicons                                                                                                                        | no         | no         |
| svg_icons_support | Defines whether Theme<br/>supports SVG icons. Default<br/>value will be inherited from<br/>the parent themes if any,<br/>otherwise - false. | no         | yes        |
| pdf_document      | Defines paths to Twig<br/>templates used to generate<br/>PDF documents (e.g. invoice)                                                       | no         | yes        |
| fonts             | Defines fonts for theme                                                                                                                     | no         | no         |
| configuration     | Defines theme configuration<br/>options that give theme<br/>developers more possibility<br/>for configurable storefront                     | no         | no         |

**Example:**

```yaml
#DemoBundle/Resources/views/layouts/first_theme/theme.yml
label:  First Theme
logo:   bundles/demo/themes/images/logo.png
parent: default
groups: [ commerce ]
rtl_support: true
config:
    pdf_document:
        invoice_default:
            content_template: '@@Acme/layouts/first_theme/twig/pdf_document/invoice_default/content.html.twig'
            header_template: '@@Acme/layouts/first_theme/twig/pdf_document/invoice_default/header.html.twig'
            footer_template: '@@Acme/layouts/first_theme/twig/pdf_document/invoice_default/footer.html.twig'
configuration:
    sections:
        header:
            label: Header
            options:
                header_menu:
                    label: Header Menu
                    type: checkbox
                    default: unchecked
                    previews:
                        checked: 'path/to/image/checked.png'
                        unchecked: 'path/to/image/unchecked.png'
```

The pdf_document option allows developers to override PDF templates per document type (e.g. invoice_default) within the theme, making it easier to customize branding and layout for downloadable documents.

#### SEE ALSO
[theme configuration](theme-configuration.md#dev-doc-frontend-theme-configuration) reference for more detailed information.

## Enable the Theme

Add the theme name to the following configuration in the `config/config.yml` file in an application, and remove themes that the application does not use:

```yaml
#config/config.yml
oro_layout:
    enabled_themes:
         - first_theme
```

## Activate the Theme

### From the Code

To set a default storefront theme on the code level, add the following
configuration to the `config/config.yml` file in an application:

```yaml
#config/config.yml
oro_layout:
    active_theme: first_theme
```

where `first_theme` is the theme folder name.

### From UI

To change the theme configuration from the back-office, refer to the [Theme Configuration](../../user/back-office/system/theme-configuration/index.md#back-office-theme-configuration) documentation. To enable the required theme configuration, refer to the theme system settings on the necessary level: [globally](../../user/back-office/system/configuration/commerce/design/theme-global.md#configuration-commerce-design-theme), [per organization](../../user/back-office/system/user-management/organizations/org-configuration/commerce/design/organization-theme.md#configuration-commerce-design-theme-theme-settings-organization) or [website](../../user/back-office/system/websites/web-configuration/commerce/design/website-theme.md#configuration-commerce-design-theme-theme-settings-website).

To get a complete configuration reference, run the `oro:layout:config:dump-reference` command, which dumps the reference structure for Resources/views/layouts/THEME_NAME/theme.yml:

```none
php bin/console oro:layout:config:dump-reference
```

<a id="dev-doc-frontend-layouts-theming-dir-stucture"></a>

## Theme Layouts Directory Structure

This is a typical theme directory structure, where AcmeDemoBundle is a bundle name:

```php
DemoBundle/
  Resources/
    public/                  # Files that will be copied to `public/bundles` folder in an application
      first_theme
        scss/
        js/
        images/
    views/
      layouts/
        first_theme/         # Theme name
          theme.yml          # Theme definition
          config/
            assets.yml       # SCSS configuration
            jsmodules.yml    # JS modules configuration
          layout_update1.yml # Layout updates applied for all the pages
          layout_update2.yml
          oro_shopping_list_frontend_view/ # Layout updates applied only for `oro_shopping_list_frontend_view` route
            layout_update.yml
          ...
```

<a id="dev-doc-frontend-layouts-theming-orocommerce-themes"></a>

## Built-in OroCommerce Themes

Out-of-the-box, the OroCommerce application comes with one predefined default storefront theme.

* **The Refreshing Teal theme** is a fully featured **default** theme that provides the complete look and feel for the OroCommerce storefront UI out-of-the-box. Also this theme is aimed to be *base for any* [customizations](how-to/index.md#storefront-customization-guide).

## Make the Theme Option Inherited

To set the theme option inherited on the code level, add the following
configuration to the `config/config.yml` file in an application:

```yaml
#config/config.yml
oro_layout:
    inherited_theme_options:
         - fonts
```

where `fonts` is the name of the theme option.

To make the theme config option inherited, add the following configuration:

```yaml
oro_layout:
    inherited_theme_options:
         - fonts
         - config.icons
```

## Retrieving Theme Options

To get the correct theme option value, use getThemeOption and getThemeConfigOption methods from OroComponentLayoutExtensionThemeModelThemeManager, service definition - oro_layout.theme_manager.

*src/Oro/Component/Layout/Extension/Theme/Model/ThemeManager.php*
```php
namespace Oro\Component\Layout\Extension\Theme\Model;

class ThemeManager implements ResetInterface
{
    public function getThemeOption(string $themeName, string $optionName, bool $inherited = true): mixed
    {
    }

    public function getThemeConfigOption(string $themeName, string $configOptionName, bool $inherited = true): mixed
    {
    }
}
```

#### NOTE
To retrieve the value of a theme option for the current theme only (excluding inherited values), pass false to the $inherited parameter.
