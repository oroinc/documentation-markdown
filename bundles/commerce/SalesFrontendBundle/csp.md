<a id="bundle-docs-commerce-sales-frontend-bundle-csp"></a>

# Content Security Policy (CSP)

<a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> automatically configures <a href="https://www.w3.org/TR/CSP/" target="_blank">CSP</a> headers to allow embedding of the OroCommerce application into an iframe of the Sales Frontend application.

CSP is automatically configured for the following URLs:

* `%oro_sales_frontend.routing_prefix%/*`

where `%oro_sales_frontend.routing_prefix%` is `/admin/sales-frontend` by default.

#### NOTE
Routing prefix can be changed via the bundle configuration, see more in the [Routing Prefix](routing-prefix.md#bundle-docs-commerce-sales-frontend-bundle-routing-prefix) configuration.

CSP is configured by `\Oro\Bundle\SalesFrontendBundle\EventListener\Kernel\SetContentSecurityPolicyOnResponseListener` which by default sets the following directive into the `Content-Security-Policy` header:

* frame-ancestors `self`

The allowed frame ancestors (i.e., the Sales Frontend application hosts) are configured automatically as per the `oro_sales_frontend.app_base_urls` bundle configuration setting. Example of the CSP header that would be sent to browser when the Sales Frontend host is https://example.com:

```text
Content-Security-Policy: frame-ancestors 'self' https://example.com
```

#### NOTE
As per the W3C <a href="https://www.w3.org/TR/CSP/" target="_blank">CSP</a> document, the `frame-ancestors` directive replaces the `X-Frame-Options` header.

<!-- Frontend -->
