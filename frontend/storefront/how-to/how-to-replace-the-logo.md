<a id="dev-doc-frontend-storefront-customization-replace-logo-and-favicon"></a>

# How to Replace a Logo and a Favicon in the Storefront

The following article describes how to replace logo and favicon images in your custom OroCommerce application. Please follow all the steps outlines below to replace the favicon and the logo.

This topic assumes that you have previously created a custom application, a bundle, and a storefront theme, as described in the [Storefront Customization](index.md#storefront-customization-guide) topic.

#### NOTE
This tutorial is suitable for both cases: when you have created your own custom storefront theme, and when you need to change an out-of-the-box one. However, creating your own theme is recommended as it enables managing your storefront appearance easily.

## Replace Favicons

1. Place new storefront favicon images into your bundle\`s public assets folder (e.g., `Resources/public/{your_theme_id}/favicons/`):

   The main favicon image:
   - Resources/public/default/favicons/favicon.ico

   Additional favicon images and a <a href="https://developers.google.com/web/fundamentals/web-app-manifest/" target="_blank">web app manifest file</a> with specified icons:

   #### NOTE
   For the detailed description of a purpose and role of additional favicons and the `manifest.json` file, check out an article on <a href="https://mobiforge.com/design-development/adding-favicons-in-a-multi-browser-multi-platform-world" target="_blank">Adding favicons in a multi-browser multi-platform world</a>.

   - Resources/public/default/favicons/apple-touch-icon-57x57.png
   - Resources/public/default/favicons/apple-touch-icon-60x60.png
   - Resources/public/default/favicons/apple-touch-icon-72x72.png
   - Resources/public/default/favicons/apple-touch-icon-76x76.png
   - Resources/public/default/favicons/apple-touch-icon-114x114.png
   - Resources/public/default/favicons/apple-touch-icon-144x144.png
   - Resources/public/default/favicons/apple-touch-icon-120x120.png
   - Resources/public/default/favicons/apple-touch-icon-152x152.png
   - Resources/public/default/favicons/apple-touch-icon-180x180.png
   - Resources/public/default/favicons/favicon-32x32.png
   - Resources/public/default/favicons/android-chrome-192x192.png
   - Resources/public/default/favicons/favicon-96x96.png
   - Resources/public/default/favicons/favicon-16x16.png
   - Resources/public/default/favicons/manifest.json
   - Resources/public/default/favicons/mstile-144x144.png

   Example of a `manifest.json` file:
   ```json
   {
       "name": "Acme Inc Storefront",
       "short_name": "Acme Store",
       "icons": [
           {
               "src": "{{ site.baseurl }}/bundles/app/default/favicons/favicon-32x32.png",
               "sizes": "32x32",
               "type": "image/png"
           },
           {
               "src": "{{ site.baseurl }}/bundles/app/default/favicons/android-chrome-192x192.png",
               "sizes": "192x192",
               "type": "image/png"
           }
       ],
       "start_url": "/",
       "display": "standalone"
   }
   ```
2. Create a [Layout Update](../layouts/index.md#dev-doc-frontend-layouts-layout-updates) file to replace other specific favicons in the storefront.

#### IMPORTANT
Please make sure to remove the default Oro favicons via the layout update, otherwise, they will be used instead of the new ones.
Also, please, make sure to change the option id: favicon_theme_icon. This option will change background color for the top bar on andriod devices.

*src/AppBundle/Resources/views/layouts/{your_theme_id}/favicon.yml*
```yaml
    layout:
        actions:
            - '@setOption':
                id: apple_57x57
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-57x57.png")'
            - '@setOption':
                id: apple_60x60
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-60x60.png")'
            - '@setOption':
                id: apple_72x72
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-72x72.png")'
            - '@setOption':
                id: apple_76x76
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-76x76.png")'
            - '@setOption':
                id: apple_114x114
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-114x114.png")'
            - '@setOption':
                id: apple_144x144
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-144x144.png")'
            - '@setOption':
                id: apple_120x120
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-120x120.png")'
            - '@setOption':
                id: apple_152x152
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-152x152.png")'
            - '@setOption':
                id: apple_180x180
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/apple-touch-icon-180x180.png")'
            - '@setOption':
                id: favicon_32x32
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/favicon-32x32.png")'
            - '@setOption':
                id: android_chrome_192x192
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/android-chrome-192x192.png")'
            - '@setOption':
                id: favicon_96x96
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/favicon-96x96.png")'
            - '@setOption':
                id: favicon_16x16
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/favicon-16x16.png")'
            - '@setOption':
                id: favicon_manifest
                optionName: href
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/manifest.json")'
            - '@setOption':
                id: msapplication_tileimage
                optionName: content
                optionValue: '=data["asset"].getUrl("bundles/app/default/favicons/mstile-144x144.png")'
            - '@setOption':
                id: favicon_theme_icon
                optionName: content
                optionValue: '#ed2d27'
            - '@remove':
                id: favicon_mask_icon
```

1. Rebuild the assets:

   Clear the cache to reload the Yaml configuration files:
   ```none
   php bin/console cache:clear
   ```

   Publish images to the public web folder:
   ```none
   php bin/console assets:install --symlink
   ```

## Replace a Logo

1. Place a new logo image to your bundle\`s public assets folder (e.g., `Resources/public/{your_theme_id}/images/logo.svg`).
2. Specify the main favicon image in your [theme configuration file](../theming.md#dev-doc-frontend-layouts-theming-definition):
   *src/{your_bundle_id}/Resources/views/layouts/{your_theme_id}/theme.yml*
   ```yaml
   logo: 'bundles/{your_theme_id}/images/logo/logo.svg'
   ```

#### BUSINESS TIP
## Business Tip

Manufacturing companies can use digital technologies to stay competitive. Discover how eCommerce and <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a> can propel the growth of your company.

<!-- Frontend -->
