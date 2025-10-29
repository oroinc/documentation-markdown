<a id="bundle-docs-commerce-multi-website-bundle"></a>

# OroMultiWebsiteBundle

#### NOTE
This bundle is only available in the Enterprise edition.

The OroMultiWebsiteBundle feature allows for the management of multiple websites in a single storefront.

## Create a Website

A MultiWebsiteBundle allows you to create several websites that share the same OroCommerce Management Console and expose a subset of the information available in the system (e.g., a dedicated web catalog with localized products).

In OroCommerce, websites may be exposed via different domains or reside in the sub-folders of the same domain (e.g., the two websites that target the United States and the United Kingdom may be available at *https://us-store.com* and *https://uk-store.com*, respectively, or they may be reachable via *https://store.com/us* and *https://store.com/uk*).

For websites with dedicated domains, you may use the default OroCommerce installation, where all websites are installed into the web folder of the OroCommerce instance. However, you can move or copy the website to the subdirectory to support websites with the shared domain (e.g., *https://store.com/us* and *https://store.com/uk*).

To prepare files for the website located in the sub-directory (e.g /uk):

1. Copy index.php from *public* directory into the new location (e.g. public/uk/) and modify it to update the relative paths (e.g. adding extra  */..* prefix to the path).

   For example:
   ```php
   require_once __DIR__.'/../vendor/autoload_runtime.php';
   ```

   should be changed to
   ```php
   require_once __DIR__.'/../../vendor/autoload_runtime.php';
   ```
2. Add WEBSITE_PATH environment variable before return fn() => new AppKernel(‘dev’, true);. This parameter value should be the new website folder name.
   ```php
   ...
   $_ENV['WEBSITE_PATH'] = '/<yoursitename>';

   return fn() => new AppKernel('dev', true);
   ...
   ```

   where <yoursitename> is *uk* in our example.

When you use the [http://localhost](http://localhost)/<yoursitename>/index_dev.php address, the asset files (styles.css, app.js, etc.) are taken from the root folder on the domain instead of the dedicated website sub-folder.

Once your files are ready to service requests to the website, create and configure the websites in the OroCommerce back-office. For more information, see [Configure Websites in Back-Office](../../../user/back-office/system/websites/index.md#user-guide-system-websites) and [Multiple Websites Concept Guide](../../../user/concept-guides/business-models/websites/index.md#website-management-concept-guide).

## Related Documentation

* [Email Templates](email-templates.md)

<!-- Frontend -->
