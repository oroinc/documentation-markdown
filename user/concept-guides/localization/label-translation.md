<a id="localization-translations-labels"></a>

# Translate Product Attribute Labels and Options

There are two ways to translate product attribute labels in OroCommerce:

* By changing the source language to the target language for the label and then adding the label translation to the required attribute on its edit page.
* By updating the attribute label translation directly on the Translations page.

You may find option 1 less time consuming and more straightforward. However, with option 2, you can search for any attribute labels or entity fields within a single Translations table.

## Method 1

To translate a product attribute label from English into the required language, change the default language first:

1. Navigate to **System > Configuration > System Configuration > General Setup > Localization** in the main menu.
2. In the **Localization Settings**, select the required localization from the list to add to **Enabled Localizations**.
   ![Add another supported language to the application in the system configuration](user/img/system/localization/labels/add_supported_language.png)

   #### NOTE
   Make sure you have created the corresponding localization in the **System > Localization > Localizations** menu to make them available in the list.
3. Click **Save Settings**.
4. Navigate to your user configuration by clicking on your user name on the top right of the page and clicking **My Configuration**.
   ![User configuration menu](user/img/system/localization/labels/user_config_menu.png)
5. Clear the **Use Organization** checkbox and set the localization that you have just added (e.g., German) as the default language for your application and for the UI system elements and content displayed in the back-office and in the storefront.
   ![Changing the default language on user level](user/img/system/localization/labels/user_config_language_settings.png)
6. Click **Save Settings**.

Once the default language is changed, update the label for the required product attributes:

1. Navigate to **Products > Product Attributes** in the main menu.
   ![Navigating to the product attributes menu](user/img/system/localization/labels/product_att_menu.png)
2. Open the edit page of the required product attribute.
   ![Editing a product attribute from the grid](user/img/system/localization/labels/edit_product_att.png)
3. Update the text for the label.
   ![The product attribute label translated once the application language on use level is updated](user/img/system/localization/labels/translated_label.png)

#### NOTE
Keep in mind that if an attribute is of a *select* or *multi-select* type, you can provide a proper translation to its options directly from the attribute edit page.

![Translating the attribute options to German](user/img/system/localization/labels/translated_label_options.png)

1. Click **Save and Close** (or its version in your default language).
2. Update the translation cache by clicking on the link in the pop-up dialog.
   ![Click on the link to update cache once the label is translated](user/img/system/localization/labels/update_translation_cache.png)
3. Once you are redirected to the translations page, click **Update Cache** (or its version in your default language) on the top right.
   ![Update translation cache](user/img/system/localization/labels/update_cache_page.png)

The product attribute label and it options are updated in the storefront.

> ![Updated product attribute label in the storefront](user/img/system/localization/labels/label_updated.png)

## Method 2

To translate a product attribute label from within the Translations grid, navigate to **System > Localization > Translations** in the main menu.

**If the attribute has been created in a language other than English, use the following filters to narrow down the search and locate the attribute label key:**

* **Languages** — The language in which the attribute was created
* **Translated Value** — [Attribute Name] or its part, e.g, demo_attribute
* **English Translation** – Not available

  #### NOTE
  Please note that when an attribute is created under a non-English localization, the English translation is absent.
* **Key** — oro.product.

  All product attribute labels start with *oro.product.* and include the name of the attribute (often with underscores). You are looking for the key that ends with a *label*. For example, oro.product.deutsch_demo_attribute.label
* **Domain** — messages
  ![Filtered attributes](user/img/system/localization/labels/filtered_attributes.png)

Once you locate the key, you can use it to translate the label into any selected language using the following filters:

* **Languages** — All (or selected)
* **Key** — [Your Key] e.g. oro.product.deutsch_demo_attribute.label
  ![Translating the filtered label](user/img/system/localization/labels/translations_all_languages.png)

**If the attribute has been created in English, use the following filters to narrow down the search and locate the attribute label key:**

* **English Translation** — [Attribute Name], e.g, english_demo_attribute
* **Language** — English
  ![Locating the key for the label](user/img/system/localization/labels/english_attr_label_located_translations_grid.png)

Once you locate the key, you can use it to translate the label into any selected language using the Key filter:

* **Key** — [Your Key] e.g. oro.product.english_demo_attribute.label
  ![Translating the label from English using the key filter](user/img/system/localization/labels/english_pr_att_translation_grid.png)
