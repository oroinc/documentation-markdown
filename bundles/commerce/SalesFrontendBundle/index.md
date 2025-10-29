<a id="bundle-docs-commerce-sales-frontend-bundle"></a>

# SalesFrontendBundle

<a href="https://github.com/oroinc/sales-frontend" target="_blank">SalesFrontendBundle</a> provides an integration with the headless [Field Sales application](../../../user/concept-guides/field-sales-app/index.md#concept-guide-field-sales-app), specifically it:

1. Enables the [Back-Office Web API](../../../backend/api/index.md#web-api) during the OroCommerce application installation/upgrade via `\Oro\Bundle\SalesFrontendBundle\Migrations\Data\ORM\EnableBackofficeApi` data migration.
2. Generates the private and public RSA keys required by the [OAuth2 server](../../platform/OAuth2ServerBundle/index.md#bundle-docs-platform-oauth2-server-bundle). The keys are generated automatically (if they do not yet exist) via composer script @oauth-server-generate-keys defined in the `scripts` section of the `composer.json` of this package. To generate the keys manually, see <a href="https://oauth2.thephpleague.com/installation/#generating-public-and-private-keys" target="_blank">Generating public and private keys</a>.
3. Creates [OAuth2 applications](../../../user/back-office/system/user-management/oauth-app.md#oauth-applications) with grant type `Authorization Code` required for communication between the Field Sales and OroCommerce applications via the [Back-Office Web API](../../../backend/api/index.md#web-api) using the OAuth2 authentication method. OAuth2 applications are created automatically for each organization by data migration `\Oro\Bundle\SalesFrontendBundle\Migrations\Data\ORM\LoadSalesFrontendOAuth2Clients`. The creation of a new organization is handled by the `\Oro\Bundle\SalesFrontendBundle\EventListener\Doctrine\SalesFrontendOAuth2ClientListener` doctrine listener.
4. Provides the login and login-related pages to be embedded into the Field Sales application.
5. Provides the endpoints to manage a user-session lifecycle in the Field Sales application.
6. Configures <a href="https://www.w3.org/TR/cors/" target="_blank">CORS</a> and <a href="https://www.w3.org/TR/CSP/" target="_blank">CSP</a> for the [Back-Office Web API](../../../backend/api/index.md#web-api), the Field Sales application login, login-related pages and endpoints.

For more information on the setup, see [OroCommerce Field Sales App Setup and Connection](../../../backend/field-sales-app/index.md#dev-guide-field-sales-app-setup).

## Related Documentation

* [Commands](commands.md)
* [Configuration](configuration.md)
* [CORS](cors.md)
* [CSP](csp.md)
* [Endpoints](endpoints.md)
* [Login Flow](login-flow.md)
* [Login Page](login-page.md)
* [Routing Prefix](routing-prefix.md)
* [Web Server Config](web-server-config.md)

<!-- Frontend -->
