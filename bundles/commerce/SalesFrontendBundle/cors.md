<a id="bundle-docs-commerce-sales-frontend-bundle-cors"></a>

# Cross-Origin Resource Sharing (CORS)

<a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> automatically configures <a href="https://www.w3.org/TR/cors/" target="_blank">CORS</a> headers to allow cross-origin requests to the OroCommerce application made from the Sales Frontend application.

CORS is automatically configured for the following URLs:

* `%oro_sales_frontend.routing_prefix%/oauth2/check-token`
* `%oro_sales_frontend.routing_prefix%/oauth2/refresh-token`
* `%oro_sales_frontend.routing_prefix%/user/login`
* `%oro_sales_frontend.routing_prefix%/user/logout`

where `%oro_sales_frontend.routing_prefix%` is `/admin/sales-frontend` by default.

#### NOTE
Routing prefix can be changed via the bundle configuration, see more in [Routing Prefix](routing-prefix.md#bundle-docs-commerce-sales-frontend-bundle-routing-prefix) configuration.

CORS is configured by `\Oro\Bundle\SalesFrontendBundle\EventListener\Kernel\SetCrossOriginResourceSharingPolicyListener` that by default sets the following:

* Allowed origins: the Sales Frontend application hosts (configured automatically as per the `oro_sales_frontend.app_base_urls` bundle configuration setting).
* Allowed methods: `GET`, `POST`
* Allowed credentials: `true`
* Allowed headers: `all`
* Exposed headers: `none`
* Max age: `600 seconds`

#### NOTE
You can customize methods, headers and max age via corresponding setter methods in `SetCrossOriginResourceSharingPolicyListener`

## Back-Office Web API

<a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> automatically configures <a href="https://www.w3.org/TR/cors/" target="_blank">CORS</a> for [Back-office Web API](../../../backend/api/index.md#web-api) to ensure that the Sales Frontend application can communicate with it:

* Allowed origins: the Sales Frontend application hosts (configured automatically as per the `oro_sales_frontend.app_base_urls` bundle configuration setting).
* Allowed credentials: `true`

Other CORS settings of the [Back-Office Web API](../../../backend/api/index.md#web-api) remain unchanged.

<!-- Frontend -->
