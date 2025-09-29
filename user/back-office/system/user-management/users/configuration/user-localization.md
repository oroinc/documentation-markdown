<a id="config-guide-localization-user-localization"></a>

<a id="doc-my-user-configuration-localization"></a>

# Configure Localization Settings per User

#### HINT
This section is part of the [Localization and Translation](../../../../../concept-guides/localization/index.md#concept-guide-localization-translation) concept guide that provides a general understanding of the localization and translation processes in OroCommerce.

To define the custom localization options for the particular user:

1. Navigate to **System > User management > Users** in the main menu.
2. For the necessary user, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **System Configuration > General Setup > Localization** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![Localization options available on the user level](user/img/system/user_management/localization_configuration_user.png)

Here, you can configure the following options by clearing the **Use Organization** checkbox and providing your own data:

1. In the **Location Options** section, provide:
   * **Primary Location** and **Format Address Per Country** — Define the address formatting to be applied.

     If *Format Address Per Country* is enabled and the country-specific formatting is enabled for the instance, the address will be displayed in compliance with the rules specified for the country.
     For example, if the chosen country is China, the address is displayed as follows:
     * *ZIP code*
     * *Country*
     * *State, City*
     * *Street*
     * *First and Last name*

     whereas, for the US it is:
     * *First and Last name*
     * *Street name*
     * *CITY NAME, STATE CODE, COUNTRY, ZIP code*

     Otherwise, the *Primary Location* formatting is applied.
   * **Timezone** — Defines the timezone to be applied for all the time settings defined in the instance. If the time-zone is changed, all the time settings (e.g. due dates of [tasks](../../../../activities/tasks/index.md#doc-activities-tasks)), time of reminders, etc. change correspondingly. The default value is(UTC -08:00) America/Los Angeles.
2. In the **Map Settings**, select the **Temperature Unit** and **Wind Speed Unit** to display the weather on the map. The default values are Fahrenheit and miles per hour (MPH).
   ![image](user/img/system/config_system/localization_map.png)
3. In the **Localization Settings**, provide:
   * **Default Localization** — The default language of the back-office and storefront UI for the current website. The list of available languages depends on the localizations added on the global level.
4. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
