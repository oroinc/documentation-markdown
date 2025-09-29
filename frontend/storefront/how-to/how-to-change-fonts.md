<a id="dev-doc-frontend-storefront-css-fonts"></a>

# How to Change Fonts and Typography in the Storefront

#### NOTE
We assume that you are making all customizations in your custom `AppBundle` (placed in the folder `src/AppBundle`).

#### NOTE
You have to insert this code into your own **styles.scss** file as described in
the [CSS Files Structure](../css/index.md#dev-doc-frontend-css-theme-structure) article.

## Disable and Override Fonts

#### HINT
This feature is available starting from OroCommerce v4.2.8. To check which application version you are running, see the [system information](../../../user/back-office/system/system-information/index.md#system-information).

To disable all Oro fonts, override the `$theme-fonts` variable and set `map` to *empty*.

```scss
$theme-fonts: ();
```

To disable all Oro fonts and override with a font stack of your choice, override the `$theme-fonts` variable and set a new variable – `map`:

```scss
$theme-fonts: (
    'main': (
        'family': '...',
        'variants': (
            (
                'path': '..',
                'weight': normal,
                'style': normal
            ),
            (
                'path': '...',
                'weight': 700,
                'style': normal
            )
        ),
        'formats': ('woff', 'woff2')
    ),
    'secondary': (
        'family': '...',
        'variants': (
            (
                'path': '...',
                'weight': normal,
                'style': normal
            )
        ),
        'formats': ('woff', 'woff2')
    )
);
```

## Update Fonts

To update fonts, merge `$theme-fonts` with your `$theme-custom-fonts`.

#### NOTE
You have to put the font files in your bundle public folder beforehand, e.g., `Resources/public/default/fonts`.

```scss
$theme-custom-fonts: (
    'main': (
        'family': 'Lato',
        'variants': (
            (
                'path': '#{$global-url}/orofrontend/default/fonts/lato/lato-regular-webfont',
                'weight': 400,
                'style': normal
            ),
            (
                'path': '#{$global-url}/orofrontend/default/fonts/lato/lato-bold-webfont',
                'weight': 700,
                'style': normal
            )
        ),
        'formats': ('woff', 'woff2')
    ),
    'secondary': (
        'family': 'Roboto',
        'variants': (
            (
                'path': '#{$global-url}/orofrontend/default/fonts/roboto/roboto-regular-webfont',
                'weight': 700,
                'style': normal
            )
        ),
        'formats': ('woff', 'woff2')
    )
);

$theme-fonts: map_merge($theme-fonts, $theme-custom-fonts);
```

## Additional Tools for Overriding Fonts

To disable all Oro fonts without overriding them with yours:

1. Override `$theme-fonts: ();`
2. Call mixin `font-face()` or `use-font-face();`
   > ```scss
   > $theme-fonts: ();

   > // Using font-face
   > @include font-face($font-family, $file-path, $font-weight, $font-style);

   > // Using use-font-face
   > $your-fonts: (
   >     'main': (
   >         'family': '...',
   >         'variants': (
   >             (
   >                 'path': '..',
   >                 'weight': normal,
   >                 'style': normal
   >             ),
   >             (
   >                 'path': '...',
   >                 'weight': 700,
   >                 'style': normal
   >             )
   >         ),
   >         'formats': ('woff', 'woff2')
   >     ),
   >     'secondary': (
   >         'family': '...',
   >         'variants': (
   >             (
   >                 'path': '...',
   >                 'weight': normal,
   >                 'style': normal
   >             )
   >         ),
   >         'formats': ('woff', 'woff2')
   >     )
   > );

   > @include use-font-face($your-fonts);
   > ```

`@mixin use-font-face` call dynamically `font-face` with `$your-fonts`.

## Change Font Size

To change the font size and line height, override the following variables:

```scss
// Offsets;

// Font families
$base-font: get-font-name('main');

// Font sizes
$base-font-size: 14px;
$base-font-size--large: 16px;
$base-font-size--xs: 11px;
$base-font-size--s: 13px;
$base-font-size--m: 20px;
$base-font-size--l: 23px;
$base-font-size--xl: 26px;
$base-line-height: 1.35;
```

#### IMPORTANT
In all cases above, you have to run the following console commands to publish the changes:

```none
php bin/console cache:clear
php bin/console assets:install --symlink
php bin/console oro:assets:build
```

## Recommendations for Optimizing Fonts

You can apply several optimizations to speed up the delivery of fonts to the client and improve the user experience.

### Base Optimization with Preloading of Critical Fonts

To enable preloading of critical fonts, add a layout update (e.g., preload FontAwesome):

```yaml
- '@add':
    id: font-awesome
    parentId: head
    siblingId: styles
    prepend: true
    blockType: external_resource
    options:
        href: '=data["asset"].getUrl("/build/_static/_/node_modules/font-awesome/fonts/fontawesome-webfont.woff2")'
        rel: preload
        attr:
            'as': 'font'
            'type': 'font/woff2'
            'crossorigin': anonymous
```

For more information about preloading resources, see <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types/preload" target="_blank">MDN Link types: preload</a>.

### Additional Optimization

You can split the font into Unicode subsets. For example, you can use <a href="https://github.com/zachleat/glyphhanger" target="_blank">glyphhanger</a> to extract only those icons that are used on the frontend:

```bash
glyphhanger --whitelist=U+F002,U+F007,U+F00C-F00E --subset=fontawesome-webfont.ttf --formats=ttf
```

1. Convert `ttf` to `woff2` with <a href="https://github.com/bramstein/homebrew-webfonttools" target="_blank">Web Font Tools</a>:

```bash
woff2_compress ./fontawesome-webfont-subset.ttf
```

1. If the project still supports IE11, convert `ttf` to `woff2`:

```bash
sfnt2woff-zopfli ./fontawesome-webfont-subset.ttf
```

1. Upload the of the new fonts and configure `typography` by overriding the default `font-awesome` section `_typography.scss` in your custom `typography` config:

```scss
$theme-custom-fonts: (
    'font-awesome': (
        'family': 'FontAwesome',
        'variants': (
            (
                'path': '#{$global-url}/orofrontend/default/fonts/fontawesome/fontawesome-webfont-preload',
                'weight': normal,
                'style': normal
            )
        ),
        'formats': ('woff2', 'woff')
    ),
);

$theme-fonts: map_merge($theme-fonts, $theme-custom-fonts);
```

1. Create/Update path to the font in the preload link:

```yaml
- '@add':
    id: font-awesome
    parentId: head
    siblingId: styles
    prepend: true
    blockType: external_resource
    options:
        # new href value
        href: '=data["asset"].getUrl("/build/_static/bundles/orofrontend/default/fonts/fontawesome/fontawesome-webfont-subset.woff2")'
        rel: preload
        attr:
            'as': 'font'
            'type': 'font/woff2'
            'crossorigin': anonymous
```

### Text Fonts and Subsets

You can split text fonts into localization subsets:

```bash
glyphhanger --formats=ttf --LATIN --subset=lato.ttf
```

You can, therefore, preload the subset depending on the application’s current localization.

<!-- Frontend -->
