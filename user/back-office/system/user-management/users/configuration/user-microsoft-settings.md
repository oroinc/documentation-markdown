<a id="user-configuration-microsoft-settings"></a>

# Configure Microsoft Settings per User

To configure email, calendar events, and task synchronization with Microsoft 365 for a particular user, follow the steps outlined below.

#### NOTE
To use calendar events and tasks, add the **Calendars.ReadWrite** and **Tasks.ReadWrite** API permissions to the list of application permissions as well as the default list.

#### NOTE
These settings can be configured [globally](../../../configuration/system/integrations/microsoft-settings/index.md#configuration-integrations-microsoft), [per organization](../../organizations/org-configuration/general-setup-org/integrations/organization-microsoft.md#organization-configuration-microsoft), and user.

1. Before configuring the Microsoft settings for a specific user, make sure that the [Azure Active Directory Application Settings](../../../configuration/system/integrations/microsoft-settings/microsoft-oauth-azure.md#user-guide-integrations-azure-oauth) are filled in the system configuration (System > Configuration > Integrations > Microsoft Settings). Ask your administrator for help if you do not have the related permissions to check the system configuration.
2. Once filled, navigate to **System > User Management > Users** in the main menu.
3. For the necessary user, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
4. Select **System Configuration > Integrations > Microsoft Settings** in the menu to the left.
   ![Settings menu options available on the user level](user/img/system/user_management/user-microsoft-settings.png)
5. In the **Microsoft Account** section, click **Connect** to connect the user’s Microsoft 365 account and synchronize calendar events and tasks with it.
6. Once clicked, a popup dialog appears, prompting to sign in with the user’s Microsoft credentials. After successful login, the user’s Microsoft 365 account name is displayed, and you can check whether the Oro Microsoft connection works properly by clicking **Check Connection**.
   ![Settings menu options available on the user level](user/img/system/user_management/user-microsoft-conection.png)
7. Clear the **Use Organization** checkbox to override the organization-wide setting for a selected user.
8. In the **Synchronization Settings** section, determine how often the data synchronization should be performed. The interval is set in minutes.
9. In the **Calendar Synchronization** and **Tasks Synchronization** sections, define the following:
   * **Enabled** - Indicates whether the synchronization of calendar events and tasks is enabled for the user.
   * **Sync Direction** - Data synchronization direction. It can be Oro to Microsoft, Microsoft to Oro, and Bidirectional.
   * **Conflict Resolution** - The conflict resolution strategy that should be used if the same calendar events and tasks are changed in both Microsoft and Oro. This option is applicable only when bidirectional data synchronization is configured.
10. Click **Save Settings**.

#### NOTE
To enable and configure the email synchronization for users, please see the [User Email Synchronization Settings](user-email-settings.md#my-email-configuration) and [System Mailbox Synchronization Settings](../../../configuration/system/general-setup/global-email.md#admin-configuration-system-mailboxes) documentation.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
