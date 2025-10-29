<a id="user-guide-consents-localizing-consents"></a>

# Localize Consents

To translate the consent labels and content from English into the required language, make sure to take the following steps:

1. Create a necessary [localization](../../../back-office/system/localization/localizations/index.md#localization-localizations) under **System > Localization > Localizations**.
2. Add the required localization to the list of enabled localizations under **System > Configuration > System Configuration > General Setup > Localization**. It enables customers to select a desired language of the website content in the storefront.
   ![Add the necessary localizations to the list of enabled localizations](user/img/system/consents/consents_enabled_localization.png)
3. Enable consents on the [global](../../../back-office/system/configuration/commerce/customer/global-interactions.md#admin-guide-commerce-configuration-customers-consents-enable-globally) and [website](../../../back-office/system/websites/web-configuration/commerce/customers/website-interactions.md#admin-guide-commerce-configuration-customers-consents-enable-website) levels.
4. Select a consent that needs to be localized under **System > Consent Management** and provide a translation of the consent name following the guidance in the [Translations and Localizations section](../../../back-office/system/configuration/system/general-setup/global-localization.md#localization-localization).
   ![Provide a translation of the consent name](user/img/system/consents/translate_consent_name.png)
5. Create a consent [landing page](add-consent.md#user-guide-consents-add) with the title and description of the consent in the target language (e.g., German, French, etc) and add the landing page to the existing content tree node that requires translation.
   ![A sample of the consent landing page with the title and text of the consent in German](user/img/system/consents/create_landing_page_german.png)

#### NOTE
Keep in mind that for each localization you need to create a new landing page in the corresponding language.

1. Set the visibility restriction of the consent landing page to a certain localization. This defines which consent variant to display to the customer based on the language they select in the storefront.
   ![Steps that need to be performed to add consent landing pages to a content node](user/img/system/consents/add_landing_pages_to_consents.png)

The changes in the storefront are applied immediately once the settings are saved.

1. Check the consent translation in the storefront by selecting the desired localization.
   ![View the consent translated to German when the German localization is selected](user/img/system/consents/german_consent.png)
2. Click the consent link to open the consent landing page.
   ![A sample of the consent landing page translated to German](user/img/system/consents/german_consent_example.png)
