<a id="bundle-docs-commerce-sales-frontend-bundle-login-page"></a>

# Login Page

<a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> provides the login and login-related pages for the Sales Frontend application. By default these pages are available on the following URLs:

* `/admin/sales-frontend/user/login`
* `/admin/sales-frontend/user/login-check`
* `/admin/sales-frontend/user/reset-request`
* `/admin/sales-frontend/user/send-email`
* `/admin/sales-frontend/user/check-email`
* `/admin/sales-frontend/user/user/two-factor-auth`
* `/admin/sales-frontend/user/user/two-factor-check`
* `/admin/sales-frontend/user/login/check-google`
* `/admin/sales-frontend/user/login/check-office365`

Prefix /admin/sales-frontend can be changed via the `oro_sales_frontend.routing_prefix` bundle setting. For more information, see the [Routing Prefix](routing-prefix.md#bundle-docs-commerce-sales-frontend-bundle-routing-prefix) documentation.

The login page must be embedded via an iframe to make it possible to share common cookies between the Sales Frontend and OroCommerce applications. For more information, see [Login Flow](login-flow.md#bundle-docs-commerce-sales-frontend-bundle-login-flow).

## Firewall

The <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> defines the `sales_frontend_app` firewall to handle the login, login-related pages, and user-session lifecycle endpoints under a separate context from the main context. It replicated the main firewall and overrides some options to make it function on other URLs.

The firewall URL prefix is /admin/sales-frontend by default and can be changed via the `oro_sales_frontend.routing_prefix` bundle setting. For more information, see [Routing Prefix](routing-prefix.md#bundle-docs-commerce-sales-frontend-bundle-routing-prefix).

For more implementation details, see `Resources/config/app.yml` and `\Oro\Bundle\SalesFrontendBundle\DependencyInjection\OroSalesFrontendExtension` in the <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a>.

## Login Page Customization

You can customize the login page by overriding the @OroSalesFrontend/Security/login.html.twig TWIG template via standard Symfony method (see <a href="https://symfony.com/doc/6.4/bundles/override.html#routing" target="_blank">How to Override any Part of a Bundle</a>). The same approach works for the login-related pages.

#### NOTE
The login and login-related pages are reused from their original bundles but with overridden TWIG templates. For more details, refer to `Resources/config/oro/routing.yml` of <a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a>.

#### NOTE
Please note that the “Reset Password” email takes user to the URL defined in the `Application URL` (i.e., `oro_ui.application_url`) setting specified under **System Configuration > General Setup > Application Settings** in the back-office configuration.

<!-- Frontend -->
