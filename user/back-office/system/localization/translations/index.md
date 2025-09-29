<a id="localization-translations"></a>

# Configure Translations in the Back-Office

<!-- begin -->

Translations are a collection of visual elements in the Oro application, like labels, information massages, notifications, alerts, workflow statuses, etc.

To add or edit the text translated to the target language, navigate to **System > Localization > Translations** in the main menu.

![image](user/img/system/localization/translations_overview.png)

The following information about the translations is available in the All Translations list:

| Name                   | Description                                                                                                                                                                                                                   |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| LANGUAGE               | The language of the text system elements available to the user.                                                                                                                                                               |
| TRANSLATED             | The status indicates whether the text items are translated to the target language (Yes/No).                                                                                                                                   |
| ENGLISH TRANSLATION    | The column contains the english translation of the text items.                                                                                                                                                                |
| TRANSLATED VALUE       | The translation value of the text item to the target language.                                                                                                                                                                |
| CURRENT (CACHED) VALUE | The translation of the system element currently displayed to the user on the UI of the Oro application.                                                                                                                       |
| KEY                    | A coded text string that identifies the text system element and is used to find its translation to the target language<br/>(e.g. oro.ui.updated_at) in Oro applications.                                                      |
| DOMAIN                 | The logical affiliation to a particular functionality that organises linguistic sources by domain (e.g. tooltips, security,<br/>entities, jsmessages, maintenance, install, workflows, messages, validators, HWIOAuthBundle). |
| CONTEXT                | The detailed location of the translated functional component (e.g., Workflow “Checkout” -> Name).                                                                                                                             |

#### IMPORTANT
Remember a rule of thumb:

The translations which are currently displayed to the user in the Oro application are located in the **Current (cached) value** column. This column inherits the values from the **Translated value** column upon update. If there is no translation provided for a specific language, the **Current (cached) value** column is populated with the default English translation mentioned in the **English translation** column. If the system element doesn’t have the English equivalent, the **Current (cached) value** column takes the value from the **Key** column.

![image](user/img/system/localization/translations_rule_of_thumb.png)

## Verify Translations

View and check the validity of all the available UI element translations. Use search and filters to help find the necessary text element.

<a id="update-translation-cache"></a>

## Update Cached Translated Values

If the translations were imported manually or from the Crowdin website as described in the [Languages](../languages/index.md#localization-languages) section, they appear in the **Translated value** column.
After the import or an update, click **Update Cache** on the top right to populate the **Current (cached) value** column with the updated information from the **Translated value** column.

> ![image](user/img/system/localization/translations_update_cache.png)

## Update Translated Value

Add a translation to any UI element or update the existing one by proceeding a few steps:

> 1. Double-click the cell in the **Translated Value** column.
> 2. Type in the translation of the required system items.
> 3. Click <i class="fa fa-check fa-lg" aria-hidden="true"></i> to save the changes.
> 4. Click **Update Cache** on the top right to enable the translation.
>    ![image](user/img/system/localization/translations_add.png)

## Reset Custom Translations to the Default Ones

To remove one or more custom translations and roll back to the default translation downloaded from the Crowdin service, click <i class="fa fa-caret-down fa-lg" aria-hidden="true"></i> in the left corner of the list header. Confirm the removal by clicking the **Reset** button.

* The **All** option enables to select all the translations available under this section.
* The **All visible** option enables to select only the translations visible on the page you are currently viewing.
* The **None** option enables to deselect all the translations which were selected previously.

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the list header and click <i class="fas fa-sync-alt" aria-hidden="true"></i> **Reset** to delete multiple custom translations at a time.

> ![image](user/img/system/localization/translations_reset.png)
<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
