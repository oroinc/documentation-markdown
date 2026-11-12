<!-- meta: description = The extension points of OroHeadlessStorefrontBundle: reusable form fields and page blocks, the website scope, the bundle parameters, and the checkout layout in Session Transfer mode -->

<a id="bundle-docs-commerce-headless-storefront-bundle-extend"></a>

# Reuse and Customize the General Storefront Features

OroHeadlessStorefrontBundle provides the following parts that other headless application types can reuse:

* The [form fields and page blocks](#bundle-docs-commerce-headless-storefront-bundle-extend-blocks) of the
  application form, view page, and edit page.
* The [website start scope](#bundle-docs-commerce-headless-storefront-bundle-extend-website-scope) of the
  system configuration settings.
* The [bundle parameters](#bundle-docs-commerce-headless-storefront-bundle-extend-parameters).
* The [checkout layout in Session Transfer mode](#bundle-docs-commerce-headless-storefront-bundle-extend-checkout).

For the extension points of OroHeadlessApplicationBundle, see [Add and Customize Headless Application Types](../../platform/HeadlessApplicationBundle/extend.md#bundle-docs-platform-headless-application-bundle-extend).

For a step-by-step guide, see [Create a New Headless Application Type](application-type.md#bundle-docs-commerce-headless-storefront-bundle-application-type).

<a id="bundle-docs-commerce-headless-storefront-bundle-extend-blocks"></a>

## Reuse the Form Fields and Page Blocks

The `website` field and each of the `application_urls`, `application_logo`, and `contact_request_form` blocks
consist of a form extension and page listeners. The last constructor argument of each of these classes is the type
name.

To add a field or a block to your type, declare new services of the same classes with the name of your type. For the classes, the service definitions, and the priorities, see [Add the Form Fields and Page Blocks](application-type.md#bundle-docs-commerce-headless-storefront-bundle-application-type-blocks).

The `contact_request_form` block has the following requirements:

* Declare its services only when OroContactUsBundle is installed.
* Add the `application_urls` block too. The allowed domains of the embedded form come from the `applicationUrl`
  field.
* Do not declare a form handler listener. The listener of OroHeadlessStorefrontBundle already processes the forms of
  all types. For more information, see [Contact Request Form](index.md#bundle-docs-commerce-headless-storefront-bundle-contact-request-form).

<a id="bundle-docs-commerce-headless-storefront-bundle-extend-website-scope"></a>

## Use the Website Start Scope

OroHeadlessStorefrontBundle registers the scope identifier provider of the `website` system configuration scope. The
provider returns the `website` field of an application of any type. To store the system configuration settings of
your type per website, use `website` as the start scope and add the `website` field to your type. For the
system configuration services, see
[Add System Configuration Settings to a Type](../../platform/HeadlessApplicationBundle/extend.md#bundle-docs-platform-headless-application-bundle-extend-system-config).

<a id="bundle-docs-commerce-headless-storefront-bundle-extend-parameters"></a>

## Change the Bundle Parameters

The bundle defines the following parameters:

* `oro_headless_storefront.general_storefront.config_keys` — The system configuration settings of the
  `general_storefront` type.
* `oro_headless_storefront.session_transfer_checkout.application_types` — The application types whose URLs and
  logo the checkout in Session Transfer mode uses. The default value contains only the `general_storefront` type.

To change a parameter, redefine it in the `Resources/config/services.yml` file of your bundle. Your bundle must load
after OroHeadlessStorefrontBundle. For this reason, give your bundle a priority higher than `116` in its
`Resources/config/oro/bundles.yml` file.

<a id="bundle-docs-commerce-headless-storefront-bundle-extend-checkout"></a>

## Customize the Checkout in Session Transfer Mode

To change the checkout layout in Session Transfer mode, add a layout update for the `oro_checkout_frontend_checkout`
route with the `context["is_in_session_transfer_mode"]` condition. For the blocks that the bundle adds and changes,
and for the values of the `session_transfer_checkout_url` and `session_transfer_checkout_logo` layout data
providers, see [Checkout in Session Transfer Mode](index.md#bundle-docs-commerce-headless-storefront-bundle-checkout).

The following layout update in the `Resources/views/layouts/<theme>/oro_checkout_frontend_checkout/` directory of
your bundle adds a link to a help page. Replace `<theme>` with the name of your theme:

```yaml
layout:
    actions:
        - '@add':
            id: acme_checkout_help_link
            parentId: session_transfer_checkout_actions
            blockType: link
            options:
                path: 'https://example.com/help'
                text: acme.checkout.help_link.label

    conditions: 'context["is_in_session_transfer_mode"]'
```

The styles of the checkout in Session Transfer mode are SCSS variables in the
`Resources/public/default/scss/variables/session-transfer-checkout-config.scss` file of the bundle. Each variable
uses the `!default` flag. As a result, your theme can override it in a variables file of your bundle. For how to
register the file, see [Styles Assets Organization](../../../frontend/storefront/css/assets-css.md#dev-doc-frontend-css-frontend-styles-assets).

<!-- Frontend -->
