<a id="organization-configuration-microsoft"></a>

# Configure Microsoft Settings per Organization

#### HINT
Microsoft 365 calendar synchronization is available starting from OroCRM v4.2.5. Task synchronization is available starting from v4.2.6. To check which application version you are running, see the [system information](../../../../../system-information/index.md#system-information).

To configure email, calendar events, and task synchronization with Microsoft 365 for a particular organization, follow the steps outlined below.

#### NOTE
To use calendar events and tasks, add the **Calendars.ReadWrite** and **Tasks.ReadWrite** API permissions to the list of application permissions as well as the default list.

#### NOTE
These settings can be configured [globally](../../../../../configuration/system/integrations/microsoft-settings/index.md#configuration-integrations-microsoft), per organization, and [user](../../../../users/configuration/user-microsoft-settings.md#user-configuration-microsoft-settings).

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Click **System Configuration > Integrations > Microsoft Settings** in the menu to the left.
4. Clear the **Use System** check box to provide the values for a particular organization overriding the global settings.

> ![Microsoft 365 Integration settings on the organization level](user/img/system/user_management/org_configuration/general/microsoft-settings-organization.png)
1. In the **Synchronization Settings** section, determine how often the data synchronization should be performed. The interval is set in minutes.
2. In the **Calendar Synchronization** and **Tasks Synchronization** sections, define the following:
   * **Enabled** - Indicates whether the synchronization of calendar events and tasks is enabled for the user.
   * **Sync Direction** - Data synchronization direction. It can be Oro to Microsoft, Microsoft to Oro, and Bidirectional.
   * **Conflict Resolution** - The conflict resolution strategy that should be used if the same calendar events and tasks are changed in both Microsoft and Oro. This option is applicable only when bidirectional data synchronization is configured.
3. Click **Save Settings**.

#### NOTE
To enable and configure the email synchronization on the organization level, please see the [Email Synchronization Settings](../organization-email-settings.md#admin-configuration-email-configuration-organization) per Organization and [System Mailbox Synchronization Settings](../organization-email-settings.md#admin-configuration-system-mailboxes-organization) per Organization.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
