<a id="backend-security-bundle-csrf"></a>

# CSRF Protection

<a href="https://owasp.org/www-community/attacks/csrf" target="_blank">Cross-Site Request Forgery (CSRF)</a> is an attack that forces an end user to execute unwanted actions on a web application in which they are currently authenticated.

## AJAX Request CSRF Protection

To protect controllers against CSRF, use AJAX @CsrfProtection annotation. You can use it for the whole controller or individual actions.

<a href="https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html#double-submit-cookie" target="_blank">Double Submit Cookie</a> technique used for AJAX request protection, each AJAX request must have an X-CSRF-Header header with a valid token value, this header is added by default to all AJAX requests. The current token value is stored in the cookie \_csrf for HTTP connections and https-_csrf for HTTPS.

**Controller level protection**

*src/Acme/Bundle/DemoBundle/Controller/FavoriteController.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Controller;

use Acme\Bundle\DemoBundle\Entity\Favorite;
use Oro\Bundle\SecurityBundle\Annotation\Acl;
use Oro\Bundle\SecurityBundle\Annotation\AclAncestor;
use Oro\Bundle\SecurityBundle\Annotation\CsrfProtection;
use Oro\Bundle\SecurityBundle\ORM\Walker\AclHelper;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;
use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\Routing\Annotation\Route;
use Symfony\Component\Security\Acl\Voter\FieldVote;
use Symfony\Component\Security\Core\Exception\AccessDeniedException;

/**
 * Contains CRUD actions for Favorite
 *
 * @Route("/favorite", name="acme_demo_favorite_")
     * @CsrfProtection()
 */
class FavoriteController extends AbstractController
{
}
```

**Action level protection**

*src/Acme/Bundle/DemoBundle/Controller/FavoriteController.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Controller;

    /**
     * @Route("/custom", name="custom")
     * @Template("@AcmeDemo/Favorite/index.html.twig")
     * @Acl(
     *   id="acme_demo_favorite_custom",
     *   type="entity",
     *   class="AcmeDemoBundle:Favorite",
     *   permission="VIEW"
     * )
     * @CsrfProtection()
     */
    public function customAction(): array
    {
        return ['entity_class' => Favorite::class];
    }
}
```

<!-- Frontend -->
