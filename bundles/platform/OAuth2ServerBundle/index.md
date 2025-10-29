<a id="bundle-docs-platform-oauth2-server-bundle"></a>

<a id="index-0"></a>

# OroOAuth2ServerBundle

<a href="https://github.com/oroinc/oauth2-server" target="_blank">OroOAuth2ServerBundle</a> provides OAuth 2.0 authorization and resource server capabilities implemented
on top of <a href="https://github.com/thephpleague/oauth2-server" target="_blank">thephpleague/oauth2-server</a> library.

Currently, Authorization Code (with PKCE extention), Client Credentials and Password grants are implemented.

See <a href="https://oauth2.thephpleague.com/authorization-server/auth-code-grant/" target="_blank">OAuth 2.0 Server Authorization Code Grant</a> and <a href="https://oauth.net/2/grant-types/authorization-code/" target="_blank">OAuth 2.0 Authorization Code Grant</a> for details of
Authorization Code grant.

See <a href="https://oauth2.thephpleague.com/authorization-server/client-credentials-grant/" target="_blank">OAuth 2.0 Server Client Credentials Grant</a> and <a href="https://oauth.net/2/grant-types/client-credentials/" target="_blank">OAuth 2.0 Client Credentials Grant</a> for details of the
Client Credentials grant.

See <a href="https://oauth2.thephpleague.com/authorization-server/resource-owner-password-credentials-grant/" target="_blank">OAuth 2.0 Server Resource Owner Password Credentials Grant</a> and <a href="https://oauth.net/2/grant-types/password/" target="_blank">OAuth 2.0 Password Grant</a> for details on the
Password grant.

<a id="bundle-docs-platform-oauth2-server-bundle-configuration"></a>

## Configuration

The default configuration of OroOAuth2ServerBundle is illustrated below:

```yaml
oro_oauth2_server:
    authorization_server:

        # The lifetime in seconds of the access token.
        access_token_lifetime: 3600 # 1 hour

        # The lifetime in seconds of the refresh token.
        refresh_token_lifetime: 18144000 # 30 days

        # The lifetime in seconds of the authorization code.
        auth_code_lifetime: 600 # 10 minutes

        # Determines if the refresh token grant is enabled.
        enable_refresh_token: true

        # Determines if the authorization code grant is enabled.
        enable_auth_code: true

        # The full path to the private key file that is used to sign JWT tokens.
        private_key: '%kernel.project_dir%/var/oauth_private.key'

        # The string that is used to encrypt refresh token and authorization token payload.
        # How to generate an encryption key: https://oauth2.thephpleague.com/installation/#string-password
        encryption_key: '%kernel.secret%'

        # The configuration of CORS requests
        cors:
            # The amount of seconds the user agent is allowed to cache CORS preflight requests
            preflight_max_age: 600

            # The list of origins that are allowed to send CORS requests
            allow_origins: [] # Example: ['https://foo.com', 'https://bar.com']

            # The list of headers that are allowed to send by CORS requests.
            # This option specifies a list of headers that are sent
            # in the "Access-Control-Allow-Headers" response header of CORS preflight requests
            allow_headers: [] # Example: ['X-Foo', 'X-Bar']

    resource_server:

        # The full path to the public key file that is used to verify JWT tokens.
        public_key: '%kernel.project_dir%/var/oauth_public.key'
```

#### NOTE
To use OAuth 2.0 authorization, generate the private and public RSA keys and place them into locations specified in the authorization_server / private_key and resource_server / public_key options. You can use php bin/console oro:oauth-server:generate-keys Symfony command to easily generate RSA keys. Also see <a href="https://oauth2.thephpleague.com/installation/#generating-public-and-private-keys" target="_blank">Generating public and private keys</a> for details on how to generate the keys manually.

<a id="bundle-docs-platform-oauth2-server-bundle-manage-applications"></a>

## Manage OAuth Applications

See [Manage OAuth Applications](../../../user/back-office/system/user-management/oauth-app.md#oauth-applications) and [Manage Customer User OAuth Applications](../../../user/back-office/customers/customer-user-oauth-app/index.md#customer-user-oauth-app).

<a id="bundle-docs-platform-oauth2-server-bundle-create-app-via-data-fixtures"></a>

## Create OAuth Application via Data Fixtures

The OAuth applications can be added using data [fixtures](../../../backend/entities/fixtures.md#backend-entities-fixtures). For example:

```php
namespace Oro\Bundle\OAuth2ServerBundle\Migrations\Data\ORM;

use Doctrine\Common\DataFixtures\AbstractFixture;
use Doctrine\Persistence\ObjectManager;
use Oro\Bundle\OAuth2ServerBundle\Entity\Client;
use Oro\Bundle\OAuth2ServerBundle\Entity\Manager\ClientManager;
use Oro\Bundle\OrganizationBundle\Entity\Organization;
use Symfony\Component\DependencyInjection\ContainerAwareInterface;
use Symfony\Component\DependencyInjection\ContainerAwareTrait;

class LoadOAuthApplication extends AbstractFixture implements ContainerAwareInterface
{
    use ContainerAwareTrait;

    #[\Override]
    public function load(ObjectManager $manager)
    {
        $client = new Client();
        $client->setOrganization($manager->getRepository(Organization::class)->getFirst());
        $client->setName('My Application');
        $client->setGrants(['password']);
        $client->setIdentifier('my_client_id');
        $client->setPlainSecret('my_client_secret');

        $this->container->get(ClientManager::class)->updateClient($client, false);

        $manager->persist($client);
        $manager->flush();
    }
}
```

To load data fixtures, use either oro:migration:data:load or oro:platform:update command.

<a id="bundle-docs-platform-oauth2-server-bundle-rest-api"></a>

## Using OAuth Authorization in REST API

See [OAuth Authentication in API](../../../api/authentication/oauth.md#web-services-api-authentication-oauth).

#### BUSINESS TIP
## Business Tip

Find out what sets <a href="https://oroinc.com/b2b-ecommerce/what-is-b2b-ecommerce/" target="_blank">B2B eCommerce</a> apart from B2C and whether your company needs digital commerce.

## Related Documentation

* [Commands](commands.md)

<!-- Frontend -->
