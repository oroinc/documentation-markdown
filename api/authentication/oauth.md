<a id="web-services-api-authentication-oauth"></a>

<a id="index-0"></a>

# OAuth Authentication

<a href="https://oauth.net/2/" target="_blank">OAuth 2.0</a> is the industry-standard protocol for authorization. OAuth 2.0 focuses on client developer simplicity
while providing specific authorization flows for web applications, desktop applications, mobile phones,
and living room devices.

It is implemented by the [OroOAuth2ServerBundle](../../bundles/platform/OAuth2ServerBundle/index.md#bundle-docs-platform-oauth2-server-bundle) that supports
<a href="https://oauth.net/2/grant-types/authorization-code/" target="_blank">OAuth 2.0 Authorization Code Grant</a>, <a href="https://oauth.net/2/grant-types/client-credentials/" target="_blank">OAuth 2.0 Client Credentials Grant</a> and <a href="https://oauth.net/2/grant-types/password/" target="_blank">OAuth 2.0 Password Grant</a>.

For more details, see [Manage OAuth Applications](../../user/back-office/system/user-management/oauth-app.md#oauth-applications)
and [Manage Customer User OAuth Applications](../../user/back-office/customers/customer-user-oauth-app/index.md#customer-user-oauth-app).

## Generate Tokens

* [Authorization Code Grant Type](oauth-authorization-code.md)
* [Client Credentials Grant Type: Generate Token](oauth-client-credentials.md)
* [Password Grant Type: Generate Token](oauth-password.md)
* [Password Grant Type: Refresh Token](oauth-password-refresh.md)

#### NOTE
In order to use OAuth authentication, private and public keys should be generated and placed
to the server. Please contact your administrator or please follow
the [OroOAuth2ServerBundle documentation](../../bundles/platform/OAuth2ServerBundle/index.md#bundle-docs-platform-oauth2-server-bundle-configuration)
if you see the following error message:

*The encryption key does not exist.*

#### NOTE
If the system has the customer portal package installed, OAuth authorization for customer users
to the storefront API resources is enabled automatically.

#### BUSINESS TIP
## Business Tip

Want to take advantage of the new digital commerce trend? Check out everything you need to know about a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B wholesale marketplace</a>.

<!-- Frontend -->
