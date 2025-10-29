<a id="dev-doc-frontend-storefront-css-media-breakpoints"></a>

# How to Change Media Breakpoints in Storefront

To update media breakpoints, change the next breakpoints:

```scss
$site-width: 1920px !default;

// @Notice! Named Breakpoints have been chosen due to its names are used in configuration for menu, GrapesJS, Viewport manager, etc.
$breakpoint-desktop: 1366px !default;
$breakpoint-desktop-big: 1600px !default;
$breakpoint-desktop-small: 1280px !default;
$breakpoint-tablet: $breakpoint-desktop-small - 1px !default;
$breakpoint-tablet-small: 992px !default;
$breakpoint-mobile-big: 767px !default;
$breakpoint-mobile-landscape: 640px !default;
// iPhone 15 Pro Max (430 * 932)
$breakpoint-mobile: 430px !default;
```

To add, update media queries theme, a developer must create files with the `your-theme/settings/global-settings.scss` global-settings and update the list with custom breakpoints.

```scss
$custom-breakpoints: (
    'big-tablet': '(min-width: 1100px) and (max-width: 1299px)', //  add a new rule
    'desktop': '(min-width: 1440px)',                            // update an existing rule
);

$breakpoints: merge-breakpoints($breakpoints, $custom-breakpoints);
```

To disable a media query theme, a developer must set breakpoint to null

```scss
$custom-breakpoints: (
    'desktop': null // disable an existing rule
);

$breakpoints: merge-breakpoints($breakpoints, $custom-breakpoints);
```

#### NOTE
You have to put this code into your own **settings/global-settings.scss** file as described in
the [CSS Files Structure](../css/index.md#dev-doc-frontend-css-theme-structure) article.

<!-- Frontend -->
