<a id="wysiwyg-field-validation"></a>

# WYSIWYG Field Validation

OroPlatform uses <a href="http://htmlpurifier.org/docs" target="_blank">HTML Purifier</a> (a standards-compliant HTML filter library) to prevent XSS attacks.
By default HTML Purifier is configured extremely strictly - only the allowed elements and attributes are permitted in WYSIWYG fields. This ensures that the content displayed on UI is always safe and secure, and the no users can embed unsecure markup in WYSIWYG fields.
However, sometimes it may be necessary to allow some potentially insecure elements or attributes, for example, iframes - to embed videos or other media content from 3-rd party websites, <a href="http://getbootstrap.com/" target="_blank">Bootstrap</a> framework elements or attributes - to utilize Bootstrap’s capabilities, etc. If your organization security policy allows some or all users to edit and publish such potentially unsecure content, you may extend the default HTML Purifier configuration for WYSIWYG fields.

#### NOTE
This configuration affects only the WYSIWYG field type. The OroRichTextType (with TinyMCE editor) fields always use the strict purifier rules.

## HTML Purifier Modes

Out of the box, there are two HTML Purifier modes available:

**\`\`default\`\`** - it has only secure elements and attributes and is used in common cases;
**\`\`lax\`\`** - this mode extends `default` mode and includes additional allowed HTML elements and attributes.

## Content Restrictions Modes

Which of the HTML Purifier modes is applied to WYSIWYG fields depends on the `content_restrictions` `mode` configuration.

There are three modes with different secure levels:

**secure** - on the secure level, there is no way to insert any potentially insecure content via UI by any users

**selective** - on the less secure level, some roles can insert the potentially insecure content via UI into specific fields of specific entities (even if a user has the edit permissions for the certain entity field, they should not be able to insert insecure content unless they also have one of the roles that are configured to allow this, and the specified entity field is in the list of the allowed entity fields).

**unsecure** - on this level, any content can be inserted via UI by any user with the edit permissions on the WYSIWYG field.

Out-of-the-box, this option is set to `strict.`

## Validation

Validator for WYSIWYG fields validates the content based on the content restrictions mode configuration by comparing the submitted content (before purification) to the content after purification. If submitted and purified versions do not match, a validation error will appear and the user will not be allowed to save the data.

<a id="wysiwyg-field-customization"></a>

## Customization

### Creating Custom HTML Purifier Modes

You can create your own HTML Purifier mode using the inheritance hierarchy:

> ```yaml
> oro_form:
>     html_purifier_modes:
>         additional:
>             extends: default
>             allowed_html_elements:
>                 div: ~
>                 iframe:
>                     attributes:
>                         - src
>             allowed_iframe_domains:
>                 - 'maps.google.com'

>         extra:
>             extends: additional
>             allowed_html_elements:
>                 img:
>                     hasClosingTag: false
>             allowed_iframe_domains:
>                 - 'example.com'
> ```

The `extends` key allows to reuse the existing config from the extended scope that will be merged with your configuration.

### Creating Custom Content Restrictions

The `addScopeMapping` method of the `oro_cms.provider.html_purifier_scope_provider` service provides the possibility to connect the HTML Purifier mode with content restrictions modes.
The `oro_cms.provider.html_purifier_scope_provide` class enables to get an appropriate scope based on the entity and entity field names taking into account current user roles.
To connect your custom HTML Purifier mode with the content restrictions mode, you should configure the container to call `addScopeMapping`.

> ```yaml
> services:
>     acme_wysiwyg_validation.provider.html_purifier_scope_provider:
>         decorates: oro_cms.provider.html_purifier_scope_provider
>         parent: oro_cms.provider.html_purifier_scope_provider
>         calls:
>             - [addScopeMapping, ['content_restrictions_additional', 'additional']]
>             - [addScopeMapping, ['content_restrictions_extra', 'extra']]
> ```

To be able to use the `content_restrictions_additional` and `content_restrictions_extra` modes in configuration, you should add this mode to the `oro_cms` extension.

> ```php
> <?php

> namespace ACME\Bundle\WysiwygValidationBundle;

> use Oro\Bundle\CMSBundle\DependencyInjection\OroCMSExtension;
> use Symfony\Component\DependencyInjection\ContainerBuilder;
> use Symfony\Component\HttpKernel\Bundle\Bundle;

> /**
>  * The WysiwygValidationBundle bundle class.
>  */
> class ACMEWysiwygValidationBundle extends Bundle
> {
>     /**
>      * {@inheritDoc}
>      */
>     public function build(ContainerBuilder $container)
>     {
>         /** @var OroCMSExtension $extension */
>         $extension = $container->getExtension('oro_cms');
>         $extension->addContentRestrictionMode('content_restrictions_additional');
>         $extension->addContentRestrictionMode('content_restrictions_extra');
>     }
> }
> ```

After this, you can use the `content_restrictions_additional` or  `content_restrictions_extra` mode in the content restrictions configuration.

> ```yaml
> oro_cms:
>     content_restrictions:
>         mode: content_restrictions_extra
>         lax_restrictions:
>             ROLE_ADMINISTRATOR:
>                 Oro\Bundle\CMSBundle\Entity\Page: ['content']
> ```

The `lax_restrictions` key in configuration is used to limit the usage of the HTML Purifier mode. It specifies the user role, entity, and entity field to which your HTML Purifier mode will be applied.
For example, the above mentioned user with the `ROLE_ADMINISTRATOR` role can use `example.com` for iframe domain when editing the `Landing Page` `content` field. At the same time, this user is not allowed to use this iframe domain in other WYSIWYG fields.

<!-- Frontend -->
