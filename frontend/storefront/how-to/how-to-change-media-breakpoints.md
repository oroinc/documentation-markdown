<a id="dev-doc-frontend-storefront-css-media-breakpoints"></a>

# How to Change Media Breakpoints in Storefront

To update media breakpoints, change the next breakpoints:

```scss
// Desktop Media Breakpoint;

$breakpoint-desktop: 1100px;
$breakpoint-tablet: $breakpoint-desktop - 1px;
$breakpoint-tablet-small: 992px;
$breakpoint-mobile-landscape: 640px;
$breakpoint-mobile: 414px;
$breakpoint-mobile-big: 767px;
```

To add, update media queries theme, a developer must create files with the `your-theme/settings/global-settings.scss` global-settings and update the list with custom breakpoints.

```scss
$custom-breakpoints: (
    'big-tablet': '(min-width: 1100px) and (max-width: 1299px)', //  add a new rule
    'desktop': '(min-width: 1300px)',                           // update an existing rule
);

$breakpoints: merge-breakpoints($breakpoints, $custom-breakpoints);
```

To disable a media query theme, a developer must set breakpoint to null

```scss
$custom-breakpoints: (
    'desktop': null                        // disable an existing rule
);

$breakpoints: merge-breakpoints($breakpoints, $custom-breakpoints);
```

#### NOTE
You have to put this code into your own **settings/global-settings.scss** file as described in
the [CSS Files Structure](../css/index.md#dev-doc-frontend-css-theme-structure) article.

<!-- Frontend -->
