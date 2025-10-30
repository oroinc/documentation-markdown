<a id="localization-translations-labels"></a>

# Translate Product Attribute Options

#### HINT
This section is part of the [Localization and Translation](index.md#concept-guide-localization-translation) concept guide that provides a general understanding of the localization and translation processes in OroCommerce.

To translate a product attribute option from English into the required language, change the default language first:

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

The product attribute label and it options are updated in the storefront.

> ![Updated product attribute label in the storefront](user/img/system/localization/labels/label_updated.png)

#### NOTE
To translate any UI system element, label, or a popup message, read the [related documentation](messages-translation.md#localization-translations-messages).
