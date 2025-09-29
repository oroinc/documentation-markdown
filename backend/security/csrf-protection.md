<a id="backend-security-bundle-csrf"></a>

# CSRF Protection

<a href="https://owasp.org/www-community/attacks/csrf" target="_blank">Cross-Site Request Forgery (CSRF)</a> is an attack that forces an end user to execute unwanted actions on a web application
in which they are currently authenticated.

## AJAX Request CSRF Protection

To protect controllers against CSRF AJAX @CsrfProtection annotation should be used. This annotation may be used for the whole
controller or for individual actions.

<a href="https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet.html#double-submit-cookie" target="_blank">Double Submit Cookie</a> technique used for AJAX request protection, each AJAX request must have a X-CSRF-Header header with a valid token value, this header is added by default to all AJAX requests.
The current token value is stored in the cookie \_csrf for HTTP connections and https-_csrf for HTTPS.

**Controller level protection**

```php
// ...

use Oro\Bundle\SecurityBundle\Annotation\CsrfProtection;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;

/**
 * @CsrfProtection
 */
class AjaxController extends Controller
{
    /**
     * @Route("/ajax/change-stus/{statusName}", name="acme_ajax_change_status", methods={"POST"})
     */
    public function performAction($statusName)
    {
        // ...
    }
}
```

**Action level protection**

```php
// ...

use Oro\Bundle\SecurityBundle\Annotation\CsrfProtection;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;

class AjaxController extends Controller
{
    /**
     * @Route("/ajax/change-stus/{statusName}", name="acme_ajax_change_status", methods={"POST"})
     * @CsrfProtection
     */
    public function performAction($statusName)
    {
        // ...
    }
}
```

<!-- Frontend -->
