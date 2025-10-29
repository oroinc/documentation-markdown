<a id="bundle-docs-commerce-sales-frontend-bundle-login-flow"></a>

# Login Flow

Sales Frontend application requires an OAuth2 access token to work with [Back-Office Web API](../../../backend/api/index.md#web-api) of the OroCommerce application. To obtain an OAuth2 access token, a user must log in via the login page provided by this bundle. To ensure that common cookies can be shared between the Sales Frontend and OroCommerce applications, the login page must be embedded into the Sales Frontend application via an iframe. The URL for the login page is `%oro_sales_frontend.routing_prefix%/user/login`.

#### NOTE
Routing prefix is /admin/sales-frontend by default and can be changed via the bundle configuration, see more in [Routing Prefix](routing-prefix.md#bundle-docs-commerce-sales-frontend-bundle-routing-prefix) configuration.

#### NOTE
The login page template can be customized. Find more details in the [Login Page](login-page.md#bundle-docs-commerce-sales-frontend-bundle-login-page) documentation.

In default configuration it is assumed that the Sales Frontend application in hosted on the same domain as OroCommerce application and is available in the subdirectory /sales-frontend. If the OroCommerce application domain is different from the Sales Frontend application, then its base URL must be added to the <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> configuration. For example, this configuration allows the login page to be embedded in the Sales Frontend application hosted on the domain `example.com`:

*config/config.yml*
```yaml
 oro_sales_frontend:
     app_base_urls:
         - "https://example.com"
```

The setting `oro_sales_frontend.app_base_urls` is used for multiple purposes, one of which is configuring <a href="https://www.w3.org/TR/CSP/" target="_blank">CSP</a> to specify to the browser where the login and login-related pages are allowed to be embedded. This ultimately results in the following header sent to a browser when it requests the login page:

```text
Content-Security-Policy: frame-ancestors 'self' https://example.com
```

When a user successfully logs in using the login page embedded in the iframe in the Sales Frontend application, the OroCommerce application sends back the 301 response that redirects a user to the route `oro_sales_frontend_default` (/admin/sales-frontend/ by default) and sets the following cookies:

* `OROSFAID` - Sales Frontend session cookie. Inherits the default session settings, but can be configured in the oro_sales_frontend.session bundle configuration.
* `OROSFARM` - Sales Frontend remember-me login cookie.
* `OROSFATOKEN` - Sales Frontend OAuth2 access token cookie obtained under-the-hood of <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> after a successful login. By default, it has the HTTP-only flag. Can be configured in the oro_sales_frontend.access_token bundle configuration.

#### NOTE
OAuth2 authentication is performed in the OroBundleSalesFrontendBundleEventListenerSecuritySalesFrontendLoginListener.

If the OroCommerce application domain is different from the Sales Frontend application, then the aforementioned cookie should be set to the following settings:

* `SameSite = none`
* `Secure = true`
* `Partitioned = true`

#### NOTE
For more information, see <a href="https://developer.mozilla.org/en-US/docs/Web/Privacy/Privacy_sandbox/Partitioned_cookies" target="_blank">Partitioned Cookies</a>.

These settings are necessary for the browser to share these cookies between the domain of OroCommerce and the Sales Frontend applications.

## Authentication in Back-Office API

The Sales Frontend application uses OAuth2 authentication when communicating with [Back-Office Web API](../../../backend/api/index.md#web-api). This means it requires an OAuth2 access token and the ability to refresh it. The OAuth2 authentication, including the authorization flow, is handled by the <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a>. When you log in successfully, a cookie called “OROSFATOKEN” is set, which already contains the OAuth2 access token. This HTTP-only cookie automatically authenticates requests to [Back-Office Web API](../../../backend/api/index.md#web-api), so there is no need to send the explicit `Authorization: Bearer ...` header. Therefore, scripts being executed in the browser do not need direct access to the OAuth2 access token.

The request to the API must contain credentials flag to tell browser that it should include cookies in the request. For example:

```javascript
const response = await fetch('https://example.com/admin/api/users', {credentials: 'include'});
```

Please ensure that the bundle configuration `oro_sales_frontend.app_base_urls` includes the Sales Frontend application base URL to automatically configure the <a href="https://www.w3.org/TR/cors/" target="_blank">CORS</a> headers of the [Back-Office Web API](../../../backend/api/index.md#web-api) and inform the browser that requests coming from the Sales Frontend application are allowed.

## Checking an OAuth2 Access Token

Although the OAuth2 authentication remains under-the-hood, the <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> provides the ability to check an OAuth2 access token stored in the `OROSFATOKEN` cookie.

OAuth2 access token cannot be accessed from scripts, but it can still be checked for validity. <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> provides a `GET` endpoint `%oro_sales_frontend.routing_prefix%/oauth2/check-token` that takes an OAuth2 access token from the `OROSFATOKEN` cookie and returns its metadata in response. For more information, see [Endpoints](endpoints.md#bundle-docs-commerce-sales-frontend-bundle-endpoints).

## Refreshing an OAuth2 Access Token

OAuth2 refresh token is not exposed to the browser and is instead stored in the PHP session. The <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> provides a `POST` endpoint `%oro_sales_frontend.routing_prefix%/oauth2/refresh-token` that takes an OAuth2 refresh token from the PHP session to update an OAuth2 access token and the related `OROSFATOKEN` cookie. For more information, see [Endpoints](endpoints.md#bundle-docs-commerce-sales-frontend-bundle-endpoints).

## Logging Out

<a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> provides a `GET` endpoint `%oro_sales_frontend.routing_prefix%/user/logout` to securely log out a user. For more informaion, see Endpoints <bundle-docs-commerce-sales-frontend-bundle-endpoints>.

<!-- Frontend -->
