<a id="frontend-rtl-support"></a>

# Right to Left UI Support

#### HINT
This feature is available starting from OroCommerce v4.2.3. To check which application version you are running, see the [system information](../user/back-office/system/system-information/index.md#system-information).

Oro provides support for Right to Left User Interface development.

To enable it, make sure you:

- Enabled RTL support for selected localization.
- Marked a theme as RTL ready.
- Checked if custom markup and styles with JS need additional improvements.

## Enable RTL

The localization entity now has a check box **Enable RTL Mode**, which need to be selected.

![Enabled RTL support for a Localization](img/frontend/rtl-support/localization-configuration.png)

## Configure Theme

Layout and back-office themes configuration have option `rtl_support` that has to be enabled.
It affects the styles build process. An additional style file is created with the rtl annex in naming (`*.rtl.css`).

* [Layout theming definition](storefront/theming.md#dev-doc-frontend-layouts-theming-definition)
* <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/ThemeBundle#adding-a-theme-using-configyml" target="_blank">Admin theme configuration</a>

Out-of-the-box, the `default` Layout theme and `oro` back-office theme have RTL support enabled.

But not all declared style inputs need to be processed with RTLCSS processor.
Often third-party libraries support RTL out-of-the-box and their styles already account for text direction (`[dir="rtl"]`).

### Auto RTL for Layout Theme

The following is a whitelist of style inputs (auto_rtl_inputs) that have to be processed.

By default, all styles from Oro bundles are auto processed:

*src/Acme/NewBundle/Resources/views/layouts/custom/config/assets.yml*
```yaml
 auto_rtl_inputs:
     - 'bundles/oro*/**'
```

This list needs to be extended with a specific <a href="https://www.npmjs.com/package/wildcard" target="_blank">wildcard file mask</a> to enable auto processing for a custom style.
See [Load Style Files from the Bundle](../bundles/platform/AssetBundle/index.md#bundle-docs-platform-asset-bundle-load-css-from-bundle) for more information.

### Auto RTL for Back-Office Theme

The approach for the back-office theme is different. All style groups defined in `assets.yml` are automatically processed with the RTLCSS processor,
with the exeption of groups with the output file name ending with `...-rtl-ready.css`. Such groups will be omitted by the RTLCSS processor.
Styles that support RTL should be added to the `css_rtl_ready` group which has a specified output value `css/oro-rtl-ready.css`.

*src/Acme/NewBundle/Resources/config/oro/assets.yml*
```yaml
 css_rtl_ready:
     inputs:
         - "~third-party-library/that-already-supports-rtl.css"
```

See [Load Style Files from the Bundle](../bundles/platform/AssetBundle/index.md#bundle-docs-platform-asset-bundle-load-css-from-bundle) for more information.

## Develop

### Markup

For layout development, use the `is_rtl_mode_enabled` value in context to pass an option to the block:

```yaml
- '@setOption':
    id: root
    optionName: dir
    optionValue: '=context["is_rtl_mode_enabled"] ? "rtl" : ""'
```

To write templates for the back-office, use the `oro_is_rtl_mode()` twig function.

```twig
<html {{ oro_is_rtl_mode() ? 'dir="rtl"' : ''}}>
```

To force the “Left-To-Right” direction of the text (e.g., for phone, email, etc), wrap the value in the `<bdo dir="ltr"></bdo>` tag

```twig
<bdo dir="ltr">1-(800)-555-5555</bdo>
```

### Styles

Styles are written in the standard way for the LTR version. During the building process, styles of the themes that have the `rtl_support` option enabled are post-processed with an additional <a href="https://rtlcss.com" target="_blank">RTLCSS</a> processor.

As a result, an additional `[name].rtl.css` file is created for each output file of the theme.

#### NOTE
Since it is a post-processing process, and RTL dist styles are created purely on the basis of CSS files created for LTR, there is no way to use any SCSS syntax for creating RTL. There is another approach to write distinctive styles for RTL. RTLCSS defines a special notation written within the comments (see <a href="https://rtlcss.com/learn/getting-started/why-rtlcss/" target="_blank">RTLCSS documentation</a> for more information).

### JavaScript

In case the functionality needs to be changed on the JavaScript level, use `_.isRTL()` mixing in the underscore:

```javascript
import _ from 'underscore';

// ...

el.style[`margin-${_.isRTL() ? 'left' : 'right'}`] = `${offset}px`;
```

## Build Command

Use the standard building process with [php bin/console oro:assets:build](../bundles/platform/AssetBundle/commands.md#bundle-docs-platform-asset-bundle-commands). Add option `--skip-rtl` that turns off building RTL styles for development purpose to speed up build in case RTL styles are not needed at that particular moment.

<!-- Frontend -->
