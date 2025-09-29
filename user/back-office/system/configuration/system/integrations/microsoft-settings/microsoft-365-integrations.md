<a id="user-guide-integrations-microsoft"></a>

# Configure Microsoft 365 Integration in the Back-Office

#### HINT
Microsoft 365 calendar synchronization is available starting from OroCRM Enterprise v4.2.5. Task synchronization is available starting from v4.2.6. To check which application version you are running, see the [system information](../../../../system-information/index.md#system-information).

#### NOTE
To use calendar events and tasks, add the **Calendars.ReadWrite** and **Tasks.ReadWrite** API permissions to the list of application permissions as well as the default list.

To configure email, calendar events, and task synchronization with Microsoft 365, follow the steps outlined below:

1. Navigate to **System > Configuration > Integrations > Microsoft Settings** in the main menu.
   ![Microsoft 365 Integration settings](user/img/system/config_system/microsoft-sync-settings.png)
2. Make sure that the [Azure Active Directory Application Settings](microsoft-oauth-azure.md#user-guide-integrations-azure-oauth) are filled.
3. In the **Microsoft 365 Integrations** section, select the related check boxes to enable email, calendar, and tasks synchronization with Microsoft 365.
4. In the **Synchronization Settings** section, determine how often the data synchronization should be performed. The interval is set in minutes.
5. In the **Calendar Synchronization** and **Tasks Synchronization** sections, define the following:
   * **Sync Direction** - Data synchronization direction. It can be Oro to Microsoft, Microsoft to Oro, and Bidirectional.
   * **Conflict Resolution** - The conflict resolution strategy that should be used if the same calendar events and tasks are changed in both Microsoft and Oro. This option is applicable only when bidirectional data synchronization is configured.

#### NOTE
To enable and configure the email synchronization on the system level, please see the [Global Email Synchronization Settings](../../general-setup/global-email.md#doc-email-configuration) and [Global System Mailbox Synchronization Settings](../../general-setup/global-email.md#admin-configuration-system-mailboxes-global).

**Related Topics**

* [Configure Global Microsoft Settings](index.md#configuration-integrations-microsoft)
* [Microsoft 365 OAuth (Azure Active Directory Application)](microsoft-oauth-azure.md#user-guide-integrations-azure-oauth)
* [Microsoft 365 Single Sign-On](microsoft-single-sign-on.md#user-guide-integrations-microsoft-single-sign-on)
