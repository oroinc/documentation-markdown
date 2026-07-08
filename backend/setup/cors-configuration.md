<a id="backend-setup-cors"></a>

# CORS Configuration in OroCommerce

Cross-Origin Resource Sharing (<a href="https://www.w3.org/TR/cors/" target="_blank">CORS</a>) is a browser security mechanism that controls whether a web application hosted on one origin (domain, protocol, or port) can access resources hosted on another origin.

Browsers enforce CORS restrictions for cross-origin HTTP requests. Before sending certain requests, a browser may issue a preflight OPTIONS request to verify that the target endpoint allows the requested operation.

In Oro applications, CORS configuration may be required when APIs, OAuth endpoints, published OpenAPI specifications, MCP endpoints, or custom application routes are accessed from a different origin.

This guide provides an overview of all available CORS configuration options and links to detailed documentation for each use case.

The following table summarizes where CORS settings are configured for different types of endpoints:

| Endpoint Type                                          | Configuration                         |
|--------------------------------------------------------|---------------------------------------|
| Back-Office API                                        | `oro_api.cors`                        |
| Storefront API                                         | `oro_frontend.frontend_api.cors`      |
| OpenAPI Specifications                                 | `oro_api.open_api.cors`               |
| Back-Office MCP Endpoints                              | `oro_commerce_mcp.http.cors`          |
| Storefront MCP Endpoints                               | `oro_frontend_commerce_mcp.http.cors` |
| Field Sales Application OAuth Authentication Endpoints | `oro_sales_frontend.app_base_urls`    |
| Custom Routes and Pages                                | `nelmio_cors`                         |

## Configure CORS for the Back-Office API

Use the `oro_api.cors` configuration section to enable cross-origin access to back-office API resources.

Example:

```yaml
oro_api:
    cors:
        allow_origins:
            - 'https://example.com'
```

The following options are available:

* `allow_origins`
* `allow_credentials`
* `allow_headers`
* `expose_headers`
* `preflight_max_age`

For detailed configuration instructions, see [Configure CORS for API Resources](../api/cors.md#api-cors-config).

## Configure CORS for the Storefront API

Use the `oro_frontend.frontend_api.cors` configuration section to enable cross-origin access to storefront API resources.

Example:

```yaml
oro_frontend:
    frontend_api:
        cors:
            allow_origins:
                - 'https://example.com'
```

The following options are available:

* `allow_origins`
* `allow_credentials`
* `allow_headers`
* `expose_headers`
* `preflight_max_age`

For additional information, see [Storefront API configuration](../api/storefront.md#web-api-storefront).

## Configure CORS for OpenAPI Specifications

When publishing OpenAPI specifications for use by external tools and applications, CORS can be configured separately from API resource access.

Example:

```yaml
oro_api:
    open_api:
        cors:
            allow_origins:
                - 'https://example.com'
```

The following options are available:

* `allow_origins`
* `allow_headers`
* `preflight_max_age`

For detailed configuration instructions, see [Configure CORS for Published OpenAPI Specifications](../api/cors-open-api.md#openapi-cors-config).

## Configure CORS for Back-Office MCP Endpoints

Back-office Model Context Protocol (MCP) endpoint CORS settings can be configured using the `oro_commerce_mcp.http.cors` configuration section.

Example:

```yaml
oro_commerce_mcp:
    http:
        cors:
            allow_origins:
                - 'https://example.com'
            allow_headers:
                - 'Authorization'
```

The following options are available:

* `allow_origins` — The list of origins allowed to send cross-origin requests to the MCP server.
* `allow_headers` — The list of request headers allowed in CORS requests.

For detailed information about MCP configuration options, see [CommerceMcpBundle](../../bundles/commerce/CommerceMcpBundle/index.md#bundle-docs-commerce-commerce-mcp-bundle).

## Configure CORS for Storefront MCP Endpoints

Storefront MCP servers can be accessed by external applications and AI clients. When an MCP client is hosted on a different origin than the Oro application, CORS configuration may be required.

Storefront MCP endpoint CORS settings can be configured using the `oro_frontend_commerce_mcp.http.cors` configuration section:

```yaml
oro_frontend_commerce_mcp:
    http:
        cors:
            allow_origins:
                - 'https://example.com'
            allow_headers:
                - 'Authorization'
```

The following options are available:

* `allow_origins` — The list of origins allowed to send cross-origin requests to the MCP server.
* `allow_headers` — The list of request headers allowed in CORS requests.

For detailed information about MCP configuration options, see [FrontendCommerceMcpBundle](../../bundles/commerce/FrontendCommerceMcpBundle/index.md#bundle-docs-frontend-commerce-commerce-mcp-bundle).

## Configure CORS for Field Sales Application OAuth Authentication Endpoints

When the [Field Sales application (FSA)](../../user/concept-guides/field-sales-app/index.md#concept-guide-field-sales-app) is hosted on a different origin than the Oro application, CORS configuration may be required for authentication-related endpoints.

[SalesFrontendBundle](../../bundles/commerce/SalesFrontendBundle/index.md#bundle-docs-commerce-sales-frontend-bundle) automatically configures CORS for OAuth authentication endpoints and user authentication routes based on the configured application URLs.

To allow cross-origin requests, configure the allowed frontend application URLs using the `oro_sales_frontend.app_base_urls` option:

```yaml
oro_sales_frontend:
    app_base_urls:
        - 'https://example.com'
```

The configured URLs are used to determine the allowed origins for cross-origin requests to authentication-related endpoints.

For detailed information about the automatically configured endpoints, allowed methods, headers, credentials, and other CORS settings, see [SalesFrontendBundle: CORS](../../bundles/commerce/SalesFrontendBundle/cors.md#bundle-docs-commerce-sales-frontend-bundle-cors).

## Configure CORS for Custom Routes and Pages

The CORS configuration options described above apply only to the endpoints managed by their respective components.

If you need to enable CORS for custom controllers, routes, or application pages, install and configure <a href="https://github.com/nelmio/NelmioCorsBundle" target="_blank">NelmioCorsBundle</a>. This bundle is not included by default in Oro applications.

Example:

```yaml
nelmio_cors:
    paths:
        '^/product/information':
            allow_origin: ['*']
            allow_methods: ['POST']
```

This configuration enables CORS handling for requests that match the specified route pattern and ensures that browsers receive the required CORS response headers.

Custom route configuration can be useful when:

* Exposing custom JSON endpoints
* Supporting browser-based integrations
* Handling preflight OPTIONS requests
* Allowing cross-origin access to custom application functionality

Refer to the <a href="https://github.com/nelmio/NelmioCorsBundle" target="_blank">NelmioCorsBundle</a> documentation for a complete list of available options.

<!-- Frontend -->
