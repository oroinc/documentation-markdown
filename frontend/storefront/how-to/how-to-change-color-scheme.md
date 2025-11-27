<a id="dev-doc-frontend-storefront-css-color-scheme"></a>

# How to Change the Color Scheme of the Storefront

#### NOTE
We assume that you are making all customizations in your custom `AcmeDemoBundle` (placed in the `src/Acme/Bundle/DemoBundle` folder).

#### NOTE
You have to put this code into your own **styles.scss** file as described in
the [CSS Files Structure](../css/index.md#dev-doc-frontend-css-theme-structure) article.

To change the color scheme:

1. Create your own list of colors and merge it with `$color-palette` using the `map_merge($map1, $map2)` SASS function.
   : This way, your color scheme will rewrite or extend the already existing $color-palette.
     ```scss
     $theme-color-palette: (
         'primary': (
             'main': #37435c,
         ),
         'secondary': (
             'main': #fcb91d,
         ),
         'additional': (
             'ultra': #fff
         )
     ) !default;
     <br/>
     $color-palette: map_merge($color-palette, $theme-color-palette);
     ```
2. To get the color you need, use the `get-color($palette, $key);` function.
   > ```scss
   > .input {
   >     color: get-color('secondary', 'main');
   > }
   > ```
3. Run the following console commands to publish the changes:
   > ```none
   > php bin/console cache:clear
   > php bin/console assets:install --symlink
   > php bin/console oro:assets:build
   > ```
