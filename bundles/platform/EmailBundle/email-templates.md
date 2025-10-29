<a id="bundle-docs-platform-email-bundle-template"></a>

# Email Templates

Email template is a predefined email content that can be used to send emails. They can contain variables (placeholders) that are replaced with actual values when the email is sent.

Email template can be created and managed in the following ways:

- in the UI via **System > Emails > Templates**,
- programmatically via data fixtures. See [Email Templates Migrations](email-templates-migrations.md#bundle-docs-platform-email-bundle-templates-migrations) ,
- from the command line via `oro:email:template:import` Symfony command. See [Commands](commands.md#bundle-docs-platform-email-bundle-commands).

Before an email is sent, a corresponding email template is rendered using the <a href="https://twig.symfony.com/" target="_blank">TWIG templating engine</a> in a separate sandbox environment. See [Email Templates Rendering](email-templates-rendering.md#bundle-docs-platform-email-bundle-templates-rendering) and [Email Templates Rendering Sandbox](email-templates-rendering-sandbox.md#bundle-docs-platform-email-bundle-templates-rendering-sandbox) for the internals.

## Related Documentation

* [Loading an Email Template](email-templates-load.md)
* [Rendering an Email Template](email-templates-rendering.md)
* [Email Templates Rendering Sandbox](email-templates-rendering-sandbox.md)
* [Email Templates Inheritance](email-templates-inheritance.md)
* [Sending an Email Created from an Email Template](email-templates-send.md)
* [Email Templates Migrations](email-templates-migrations.md)
* [Email Templates Attachments](email-templates-attachments.md)

<!-- Frontend -->
