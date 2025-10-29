<a id="admin-configuration-email-configuration-user"></a>

<a id="my-email-configuration"></a>

<a id="doc-my-user-configuration-email"></a>

# Configure Email Settings per User

#### HINT
This topic is part of the [Email Configuration in the Back-Office](../../../emails/index.md#admin-guide-email-configuration) topic.

#### NOTE
You can configure email settings [globally](../../../configuration/system/general-setup/global-email.md#admin-configuration-email-configuration-global), [per organization](../../organizations/org-configuration/general-setup-org/organization-email-settings.md#admin-configuration-email-configuration-organization), [per website](../../../websites/web-configuration/general-sys-config/general/website-email-settings.md#admin-configuration-system-mailboxes-website), per user.

To configure email settings per user:

1. Navigate to **System > User Management > Users**  in the main menu.
2. For the necessary user, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Click **System Configuration > General Setup > Email Configuration** in the panel to the left.

<a id="id1"></a>
> #### IMPORTANT
> To change *your own* email configuration settings:

> 1. Click on your username on the top right.
> 2. Click **My Configuration**.
> 3. Follow the steps described below.

## Settings

On the **Email Configuration** page, define options applied to all the emails in the application.

#### NOTE
To change any of the system-wide options, clear the **Use Organization** checkbox first.

1. **Signature** — Add a signature to the emails.
   * *Signature Content* — Specify the text and formatting of your signature. Bby default, the email signature body is empty.
   * *Append Signature to Email Body* — Define whether a signature must be added automatically or manually.
2. **Email Synchronization Settings** — provide details to configure your personal mailbox. Select one of the options below:

   #### NOTE
   Please be aware that if the Account Type value has changed, a new mailbox will be registered, and all data from the currently configured mailbox will be lost. However, if the Account Type value has changed from or to the **Other** type, a new mailbox will *not* be registered, and all data from the currently configured mailbox will stay. This helps migrate existing mailboxes from the basic IMAP configuration to Microsoft or Gmail.

   * **Account Type: Gmail** is available when the application is integrated with Google and [OAuth 2.0 for email sync](../../../configuration/system/integrations/google-settings/google-integration.md#admin-configuration-integrations-google-gmail-oauth)  is enabled.
     * *Connected Account* — The account connected to Gmail. Click **Retrieve Folders** to load folders from the connected account.
   * **Account Type: Office 365** is available when the application is integrated with [Microsoft 365 OAuth](../../../configuration/system/integrations/microsoft-settings/microsoft-oauth-azure.md#user-guide-integrations-azure-oauth).
     * *Connected Account* — The account connected to Microsoft 365. Click **Retrieve Folders** to load folders from the connected account.

   ![Email synchronization settings for Microsoft 365](user/img/system/integrations/microsoft/office-365-email-sync.png)
   * **Account Type: Other**:
     * *Enable IMAP* — Select the checkbox to enable retrieving email messages
     * *IMAP Host* — Provide the IMAP Host, e.g. imap.gmail.com
     * *IMAP Port* — Provide the IMAP Port, e.g. 993
     * *Encryption* — Select the encryption type, SSL or TLS.
     * *Enable SMTP* — Select the checkbox to enable sending messages
     * *SMTP Host* — Provide the SMTP host, e.g. smtp.gmail.com
     * *SMTP Port* — Provide the SMTP port, e.g. 587
     * *Encryption* — Select the encryption type, SSL or TLS.
     * *User* — Provide your email address
     * *Password* — Provide your password

     Click **Check Connection/Retrieve Folders**. After successful connection, a list of folders will be loaded. Check the folders that you wish to be synchronized (e.g., Inbox).

     As an example, we have synchronized a Gmail mailbox with your Oro application, having previously turned on **access for less secure apps**. More details on how to synchronize your Gmail and turn on access for less secured apps can be found in the <a href="https://support.google.com/mail/answer/7126229?hl=en&rd=2&visit_id=1-636180891016092253-2149088408#ts=1665018%2C1665144" target="_blank">Use IMAP to check Gmail</a> and <a href="https://support.google.com/accounts/answer/6010255?hl=en" target="_blank">Less secure apps & your Google Account</a> topics.

> <br/>
> > ![Email synchronization settings configuration on the user level](user/img/system/user_management/personabox_imap_smtp.jpg)
> <br/>
1. Under **Email Threads**, select how to display emails and replies to users, either as threads or separately.
   * **Display Email Conversations As** — Defines the user’s email representation under **My Emails**.

   ![A sample of an email with the threaded option selected](user/img/system/config_system/threaded_emails.png)![A sample of an email with the non-threaded option selected](user/img/system/config_system/non-threaded-emails.png)
   * **Display Emails In Activity Lists As** — Defines how emails and replies are displayed under the **Activity** menu of a selected record.
     ![A sample of an email with the threaded option selected](user/img/system/config_system/threaded_email_activities.png)![A sample of an email with the non-threaded option selected](user/img/system/config_system/non_threaded_email_activities.png)
2. **Reply** — Define which button will be displayed as the default one: **Reply** is available by default with the **Forward** and **Reply all** options in the dropdown. The settings can be changed to have **Reply all** displayed at the top.
3. Click **Save Settings**.

**Related Topics**

* [Configure Email Settings Globally](../../../configuration/system/general-setup/global-email.md#admin-configuration-email-configuration-global)
* [Configure Email Settings per Organization](../../organizations/org-configuration/general-setup-org/organization-email-settings.md#admin-configuration-email-configuration-organization)
* [Configure Email Settings per Website](../../../websites/web-configuration/general-sys-config/general/website-email-settings.md#admin-configuration-system-mailboxes-website)
* [Configure Microsoft 365 OAuth](../../../configuration/system/integrations/microsoft-settings/microsoft-oauth-azure.md#user-guide-integrations-azure-oauth)

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
