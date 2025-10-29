<a id="bundle-docs-platform-email-bundle-templates-rendering"></a>

# Rendering an Email Template

OroEmailBundle makes use of the TWIG engine to render an email template.

#### NOTE
For security reasons, an email template is :ref:\` rendered in the sandbox mode <bundle-docs-platform-email-bundle-templates-rendering-sandbox>\`.

## Implementation Overview

The main entry point to render an email template is `\Oro\Bundle\EmailBundle\Provider\EmailRenderer`. It expects a ready-to-be-rendered email template model, template parameters (further passed as TWIG variables) and email template context. More details about how to load an email template or get an email template context, see [Loading Templates](email-templates-load.md#bundle-docs-platform-email-bundle-templates-loading).

## Examples

If you already have an email template entity to render, use `\Oro\Bundle\EmailBundle\Provider\TranslatedEmailTemplateProvider` to translate and `\Oro\Bundle\EmailBundle\Provider\EmailRenderer` to render it. Example:

```php
use Oro\Bundle\EmailBundle\Entity\EmailTemplate as EmailTemplateEntity;
use Oro\Bundle\EmailBundle\Provider\EmailRenderer;
use Oro\Bundle\EmailBundle\Provider\EmailTemplateContextProvider;
use Oro\Bundle\EmailBundle\Provider\TranslatedEmailTemplateProvider;
use Oro\Bundle\NotificationBundle\Model\NotificationSettings;
use Oro\Bundle\UserBundle\Entity\User;

class Sample
{
    private NotificationSettings $notificationSettings;

    private TranslatedEmailTemplateProvider $translatedEmailTemplateProvider;

    private EmailTemplateContextProvider $emailTemplateContextProvider;

    private EmailRenderer $emailRenderer;

    private User $user;

    public function render(EmailTemplateEntity $emailTemplateEntity, array $templateParams)
    {
        // ...

        $from = $this->notificationSettings->getSender();

        $templateContext = $this->emailTemplateContextProvider
            ->getTemplateContext($from, $this->user, 'invite_user', $templateParams);

        $translatedEmailTemplate = $this->translatedEmailTemplateProvider
            ->getTranslatedEmailTemplate($emailTemplateEntity, $templateContext['localization'] ?? null);

        $renderedEmailTemplate = $this->emailRenderer->renderEmailTemplate($translatedEmailTemplate, $templateParams, $templateContext);

        // ...
    }
}
```

#### NOTE
To send an email with a rendered email template, see [Send EmailBundle Templates](email-templates-send.md#bundle-docs-platform-email-bundle-templates-send).

If you have only an email template name, use `\Oro\Bundle\EmailBundle\Provider\RenderedEmailTemplateProvider` that uses `\Oro\Bundle\EmailBundle\Provider\EmailTemplateProvider` to load an email template and `\Oro\Bundle\EmailBundle\Provider\EmailRenderer` to render it.

Example:

```php
use Oro\Bundle\EmailBundle\Entity\EmailTemplate as EmailTemplateEntity;
use Oro\Bundle\EmailBundle\Model\EmailTemplateCriteria;
use Oro\Bundle\EmailBundle\Provider\EmailTemplateContextProvider;
use Oro\Bundle\EmailBundle\Provider\RenderedEmailTemplateProvider;
use Oro\Bundle\NotificationBundle\Model\NotificationSettings;
use Oro\Bundle\UserBundle\Entity\User;

class Sample
{
    private NotificationSettings $notificationSettings;

    private EmailTemplateContextProvider $emailTemplateContextProvider;

    private RenderedEmailTemplateProvider $renderedEmailTemplateProvider;

    private User $user;

    public function render(EmailTemplateEntity $emailTemplateEntity, array $templateParams)
    {
        // ...

        $from = $this->notificationSettings->getSender();

        $emailTemplateCriteria = new EmailTemplateCriteria('invite_user', User::class);

        $templateContext = $this->emailTemplateContextProvider
            ->getTemplateContext($from, $this->user, $emailTemplateCriteria, $templateParams);

        $renderedEmailTemplate = $this->renderedEmailTemplateProvider
            ->findAndRenderEmailTemplate($emailTemplateCriteria, $templateParams, $templateContext);

        // ...
    }
}
```

#### NOTE
Email renderer also compiles the email template attachments (if any) to make it possible to convert them into email attachments. For more details, see [Email Templates Attachments](email-templates-attachments.md#bundle-docs-platform-email-bundle-templates-attachments).

<!-- Frontend -->
