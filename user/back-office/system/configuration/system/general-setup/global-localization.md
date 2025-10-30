<a id="sys-config-sysconfig-general-setup-localization-global"></a>

<a id="localization-localization"></a>

# Configure Global Localization Settings

#### HINT
This section is part of the [Localization and Translation](../../../../../concept-guides/administration/localization/index.md#concept-guide-localization-translation) concept guide that provides a general understanding of the localization and translation processes in OroCommerce.

<!-- begin_1 -->

In the system configuration, you can define the localization options, such as system locale, primary location, address formatting method, system timezone, calendar year settings, temperature and wind speed units on the map. Furthermore, you can set the default language of the UI elements displayed in the storefront.

#### HINT
The system configuration of the localization settings are available on four levels: globally, [per organization](../../../user-management/organizations/org-configuration/general-setup-org/organization-localization.md#config-guide-localization-organization-localization), [per website](../../../websites/web-configuration/general-sys-config/general/website-localization.md#sys-websites-sysconfig-general-setup-localization), and [per user](../../../user-management/users/configuration/user-localization.md#config-guide-localization-user-localization).

To configure localization settings globally:

1. Navigate to **System > Configuration** in the main menu.
2. In panel on the left, expand **General Setup** and click **Localization**.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   The following page is displayed:
   ![Global localization configuration options](user/img/system/config_system/localization_configuration_global.png)

   Configure the required options by clearing the **Use Default** checkbox and providing your own data.
3. In the **Location Options** section, provide:
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
   * **First Quarter Starts On** — Defines the quarter start date. The default value is January, 1.
4. In the **Map Settings**, provide:
   * **Temperature Unit** and **Wind Speed Unit** to display the weather on the map. The default values are Fahrenheit and miles per hour (MPH).
     ![Weather on a map](user/img/system/config_system/localization_map.png)
5. In the **Localization Settings**, provide:
   * **Default Localization** — The default language of the back-office and storefront UI. The list of available languages depends on the localizations added to the **Enabled Localizations** list.
   * **Enabled Localizations** — The list of localizations is generated automatically based on the data preconfigured in the **System > Localization > Localizations** menu.

     All supported localizations added to this list are displayed in the language switcher in the storefront.
     ![Language switcher in the storefront](user/img/system/config_system/language_switcher_storefront.png)

     In addition, they determine the languages available for the email notifications. If there is an email template for the supported language, the users who have selected that specific language in the storefront, receive localized notifications.
     ![Language tabs in email templates](user/img/system/config_system/language_tabs_email_template.png)

     #### NOTE
     Refer to the [Localizations](../../../localization/localizations/index.md#localization-localizations) section for more details.
6. Click **Save Settings**.

<!-- finish_1 -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
