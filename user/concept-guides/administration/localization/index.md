<a id="concept-guide-localization-translation"></a>

# Localization and Translation Concept Guide

Oro application supports localization process, enabling you to translate and adapt the content of your web application to a specific country or region. By default, it offers decent translation coverage for the most used languages and live access to all updates from the Oro team and community thanks to the CrowdIn service integration.

In the Oro application, you can provide the translation for all the content elements of your storefront (e.g., product names, descriptions, catalog titles, SEO attributes, and product attribute labels, etc.) and localize everything beyond the text, such as system elements, UI labels, monetary values, time and date layout, measurements, numbers, etc.

## Prerequisites

To start configuring localization, language, and translation settings, ensure that:

1. Your current organization is the global organization (for multi-organization application). The required user role has the permissions (*Organization* or *Global*) to manage localization, language, and translation settings.

![image](user/img/concept-guides/localization/global-access-levels.png)
1. Your current organization is a non-global organization (for multi-organization application). The required user role has the permissions (*Organization* or *Global*) to manage localization, language, and translation settings per your organization.

![image](user/img/concept-guides/localization/non-global-access.png)
1. If the application has no global organizations at all, or there is only one organization, the required user role must have the permissions with the *Organization* or *Global* access level to manage localization, language, and translation settings per this specific organization.

#### HINT
For more information about multiple organizations and available access levels and permissions, see the [Configure Organizations in the Back-Office](../../../back-office/system/user-management/organizations/index.md#user-management-organizations) and [Understand Roles and Permissions](../../../back-office/system/user-management/roles/index.md#user-guide-user-management-permissions-roles) guides.

## General Localization Process

To translate the Oro application’s storefront and back-office to a desired language, make sure to take the following steps in the localization process:

**Step 1**. In the [Languages](../../../back-office/system/localization/languages/index.md#localization-languages) section, add desired languages to the system, enable them, import translation texts for the language or install translation updates from the CrowdIn project.

> ![image](user/img/concept-guides/localization/languages-grid.png)

**Step 2**. In the [Translations](../../../back-office/system/localization/translations/index.md#localization-translations) section, check the existing and imported translations for the UI system elements (e.g., labels, checkboxes, buttons, notifications, etc.). There, you can add, modify, or delete translation texts for these items if necessary.

> ![image](user/img/concept-guides/localization/all-translations-grid.png)

**Step 3**. In the [Localizations](../../../back-office/system/localization/localizations/index.md#localization-localizations) section, create a localization that inherits a translation from another language when the translation to the main language of the localization is not available. This helps avoid double efforts when translating to similar and related languages and dialects of the same language.

> ![image](user/img/concept-guides/localization/german-localization-details.png)

**Step 4**. Now, enable the necessary localizations to be displayed to the user both in the storefront and the back-office under the [Localization Settings](../../../back-office/system/configuration/system/general-setup/global-localization.md#localization-localization) section (**System Configuration > General Setup > Localization**). Here, you can also set the default language of the UI system and content elements, and define the localization options, such as system locale, primary location, address formatting method, system timezone, calendar year settings, temperature and wind speed units on the map.

![image](user/img/concept-guides/localization/localization-config-settings.png)

**Step 5**. Once the necessary localizations are created and enabled, you can now translate the required content / UI system element / UI messages / consents to the necessary language. For detailed information on each specific translation purpose, see the following sections:

* [Translate Content](content-translation.md#content-translation)
* [Translate UI Labels, Options, and Messages](messages-translation.md#localization-translations-messages)
* [Translate Product Attribute Options](label-translation.md#localization-translations-labels)
* [Translate Content Blocks](../../../back-office/marketing/content-blocks/index.md#user-guide-landing-pages-marketing-content-blocks-translation)
* [Translate Landing Pages](../../content-management/landing-page.md#concept-guide-localize-landing-page)
* [Translate Consents](../consents/localize-consents.md#user-guide-consents-localizing-consents)
* [Translate Email Templates](../../../back-office/system/emails/email-templates.md#localize-email-templates)
