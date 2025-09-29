<a id="sys-config-sysconfig-general-setup-localization"></a>

<a id="doc-user-management-users-configuration-localization"></a>

# Manage Localizations, Languages, and Translations in the Back-Office

[Localization](../../../glossary.md#term-Localization) is the process of translating and adapting a product for a specific country or region. Oro application allows a user to customize the format of date and time, numeric, percent, and monetary values as well as the format of names and addresses.

Oro application supports localization and provides decent out-of-the-box translation coverage for the most used languages. With out-of-the-box integration to CrowdIn service, Oro applications have live access to the most recent updates from the Oro team and community.

See [How to Contribute to Translations](../../../../community/contribute/code-ui-translations.md#doc-community-ui-translations) for more information about the translation process.

<!-- Keep reading to learn about the localization process (:ref:`open the quick visual guide <config-localization-quick-start>`): -->

## Localization Process

To translate the Oro application’s storefront and back-office to a desired language, make sure to take the following steps in the localization process:

> **Step 1**. In the [Languages](languages/index.md#localization-languages) section, add desired languages to the system, enable them, import translation texts for the language or install translation updates from the CrowdIn project.

> **Step 2**. In the [Translations](translations/index.md#localization-translations) section, check the existing and imported translations for the UI system elements (e.g., labels, checkboxes, buttons, notifications, etc.). There, you can add, modify, or delete translation texts for these items if necessary.

> > #### NOTE
> > Remember to [update the cache](translations/index.md#update-translation-cache) after each translation adjustment.

> **Step 3**. In the [Localizations](localizations/index.md#localization-localizations) section, create a localization that inherits a translation from another language when the translation to the main language of the localization is not available. This helps avoid double efforts when translating to similar and related languages and dialects of the same language.

> **Step 4**. Once the necessary localizations are created, you can now translate the content elements (e.g., names, titles, labels, descriptions, etc.) using inline [content translation](../../../concept-guides/localization/content-translation.md#content-translation) available for most of the text fields.

> > ![image](user/img/system/localization/ProductsCreateTranslation.png)

> **Step 5**. Now, enable all the necessary localizations of the UI system and content elements to be displayed to the user both in the storefront and the back-office in the [Localization Settings](../configuration/system/general-setup/global-localization.md#localization-localization) section.

For detailed information on these topics, please see the following sections:

* [Add and Enable Languages. Export and Import Translations to the Target Language](languages/index.md#localization-languages)
* [Edit and Cache Translations](translations/index.md#localization-translations)
* [Add and Manage Localizations](localizations/index.md#localization-localizations)
* [Configure Localization Settings](../configuration/system/general-setup/global-localization.md#localization-localization)
* [Translate Content](../../../concept-guides/localization/content-translation.md#content-translation)
* [Translate Product Attribute Labels](../../../concept-guides/localization/label-translation.md#localization-translations-labels)
* [Translate Content Blocks](../../marketing/content-blocks/index.md#user-guide-landing-pages-marketing-content-blocks-translation)
* [Translate Consents](../../../concept-guides/consents/localize-consents.md#user-guide-consents-localizing-consents)
* [Translate Email Templates](../emails/email-templates.md#localize-email-templates)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
