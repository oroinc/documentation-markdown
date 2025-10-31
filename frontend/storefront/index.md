<!-- meta: description = Practical guides on developing and customizing the OroCommerce storefront design for the frontend developers -->

<a id="dev-doc-frontend-storefront"></a>

# Storefront Customization

This documentation provides instruction on how to customize OroCommerce storefront looks and feel with themes. Developing and customizing the OroCommerce back-office design is out of the scope of this guide and covered by [the Back-Office Design Customization Guide](../back-office/index.md#dev-doc-frontend-back-office-theming).

![image](user/img/storefront/strefront_landing.png)

The OroCommerce storefront design architecture has some differences from the back-office:
: - It is not using the SPA approach for the SEO optimization, but the Javascript Framework is the same;
  - Themes are built on top of the OroLayouts framework which is much more flexible than the placeholders approach used for back-office themes;
  - You can also customize it with themes, but as the architecture is different, you cannot reuse the same theme for OroCommerce storefront and back-office.

#### BUSINESS TIP
# Business Tip

The manufacturing industry is one of the key sectors fully embracing digitization. Here is how you can enable <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a> with eCommerce.

<h2>Table of Contents</h2>

* [Quick Start](quick-start.md)
* [Themes](theming.md)
* [Stylesheets (SCSS)](css/index.md)
* [JavaScript](javascript.md)
* [Layout](layouts/index.md)
* [Theme Configuration](theme-configuration.md)
* [Templates (Twig)](templates.md)
* [Image Resizing and Watermarks](images.md)
* [Customization How-To Guides](how-to/index.md)
* [OroCommerce Render Caching](render-cache.md)
* [Frontend Developer Tools](debugging.md)
* [Preload Critical Assets](preload-critical-assets.md)
* [Icons (SVG)](svg-icons.md)
* [Optimize Assets Build](optimize-build.md)
