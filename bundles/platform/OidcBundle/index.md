<a id="bundle-docs-platform-oidcbundle"></a>

# OroOidcBundle

#### NOTE
This bundle is available as of OroPlatform Enterprise version 6.1.7.

OroOidcBundle adds support for the **OpenID Connect** to the Oro applications. It enables SSO via 3-rd party systems like Okta, Microsoft Enta, Google, and others that support OpenID Connect.

<a href="https://openid.net/developers/how-connect-works/" target="_blank">OpenID Connect</a> (OIDC) is an authentication protocol built on top of OAuth 2.0. It allows an application to verify a user’s identity based on tokens issued by an external identity provider (IdP).

When a user signs in using OIDC:

1. The user is redirected to the identity provider’s login page.
2. After successful authentication, the identity provider returns an ID token to Oro.
3. Oro uses the information in the ID token (such as a unique user ID and profile data) to identify a corresponding user account.

OpenID Connect provides a standardized, secure, and interoperable way to exchange identity information between systems.

#### NOTE
Only the systems that return the **email** field in the ID token are supported. This field is required to map an Oro **User** or **Customer User** to the corresponding external account. After mapping, the subfield will be used.

#### NOTE
For more details on how to configure the OIDC integration with **OpenID Connect**, **Google OpenID Connect**, **Microsoft OpenID Connect**, or **Okta OpenID Connect**, refer to the [Configure OpenID Connect Integrations in the Back-Office](../../../user/back-office/system/integrations/openid/index.md#user-guide-integrations-openid-connect) documentation.

**Related Articles**

* [Configure OpenID Connect Integrations in the Back-Office](../../../user/back-office/system/integrations/openid/index.md#user-guide-integrations-openid-connect)
* [Configure User Provisioning and SCIM Synchronization](../../../user/back-office/system/configuration/system/general-setup/user.md#admin-configuration-user-settings-scim)
* [Configure Okta Provisioning Service](../../../user/back-office/system/configuration/system/general-setup/user.md#okta-provisioning-service)
* [Configure Microsoft Entra Provisioning Service](../../../user/back-office/system/configuration/system/general-setup/user.md#microsoft-entra-provisioning-service)
