<a id="admin-configuration-email-configuration-organization"></a>

# Configure Settings for Email Configuration per Organization

#### HINT
Read more on this topic in [Emails](../../../../emails/index.md#admin-guide-email-configuration).

## Configure Email Settings

#### NOTE
You can configure email settings [globally](../../../../configuration/system/general-setup/global-email.md#admin-configuration-email-configuration-global), per organization, [per website](../../../../websites/web-configuration/general-sys-config/general/website-email-settings.md#admin-configuration-system-mailboxes-website), [per user](../../../users/configuration/user-email-settings.md#admin-configuration-email-configuration-user).

To configure email settings per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
3. On the **Email Configuration** page, define options applied to all the emails in the application.

   #### NOTE
   To change any of the system-wide options, clear the **Use System** checkbox first.

   * **Email settings** — User emails are enabled by default. To disable the option, clear the **Use System** checkbox and clear the **Enable User Emails** option.
   * **Signature** — Add a signature to the emails.
     * *Signature Content* — Specify the text and formatting of your signature. By default, the email signature body is empty.
     * *Append Signature to Email Body* — Define whether a signature must be added automatically or manually.
4. Under **Email Threads**, select how to display emails and replies to users, either as threads or separately.
   * **Display Email Conversations As** — Defines the user’s email representation under **My Emails**.

   ![A sample of an email with the threaded option selected](user/img/system/config_system/threaded_emails.png)![A sample of an email with the non-threaded option selected](user/img/system/config_system/non-threaded-emails.png)
   * **Display Emails In Activity Lists As** — Defines how emails and replies are displayed under the **Activity** menu of a selected record.
     ![A sample of an email with the threaded option selected](user/img/system/config_system/threaded_email_activities.png)![A sample of an email with the non-threaded option selected](user/img/system/config_system/non_threaded_email_activities.png)
5. Under **SMTP Settings**, configure the SMTP protocol that allows sending email messages. Click **Check SMTP Connection** once you provide the following details:
   > * *Host* — SMTP Host name, e.g. smtp.gmail.com
   > * *Port* — SMTP Port number, e.g. 465
   > * *Encryption* — Encryption type: None, SSL or TLS
   > * *Username* — Your email address
   > * *Password* — The password for your email address
6. Under **HTML in templates**, configure the following:
   > * **Enable HTML Purifier** — Enable or disable HTML Purifier. Disabling HTML Purifier allows you to paste any HTML code into a template or an email body editor without tag stripping.
   > * **Enable WYSIWYG For Email Templates** — Enable or disable the WYSIWYG editor for [email templates](../../../../emails/index.md#admin-guide-email-configuration). Remember that the WYSIWYG editor does not support variables provided by the default base email template. Enabling the WYSIWYG editor may break existing email templates.
7. Under **System Mailboxes**, configure a [system mailbox](../../../../configuration/system/general-setup/global-email.md#admin-configuration-system-mailboxes) that allows people who do not have access to the company mailbox addresses to write to the company. To add a new system mailbox, click **Add Mailbox**.
8. Click **Save Settings**.

<a id="admin-configuration-system-mailboxes-organization"></a>

## Configure a System Mailbox

To configure a system mailbox on the [organization level](../../../../index.md#configuration-guide-config-levels):

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
3. Click **System Configuration > General Setup > Email Configuration** in the panel to the left.
4. In the **System Mailboxes** section, click **Add Mailbox**.
5. In the **General** section, define the basic settings of the mailbox:
   * **Mailbox Label** — Provide a name for the system mailbox.
   * **Email** — Provide the email address.
6. In the **Synchronization Settings**, configure your IMAP/SMTP connection:
   * *Enable IMAP* — Select the checkbox to enable retrieving email messages
   * *IMAP Host* — Provide the IMAP Host, e.g. imap.gmail.com
   * *IMAP Port* — Provide the IMAP Port, e.g. 993
   * *Encryption* — Select the encryption type, SSL or TLS
   * *Enable SMPT* — Select the checkbox to enable sending messages
   * *SMTP Host* — Provide the SMTP host, e.g. smtp.gmail.com
   * *SMTP Port* — Provide the SMTP port, e.g. 587
   * *Encryption* — Select the encryption type, SSL or TLS
   * *User* — Provide your email address
   * *Password* — Provide your password
7. Click **Check Connection/Retrieve Folders**. After a successful connection, a list of available folders is displayed. Select the checkboxes next to the folders you wish to synchronize.

   #### HINT
   Detailed instructions on the way to set up IMAP and SMTP connection in Gmail are provided on the <a href="https://support.google.com/mail/troubleshooter/1668960?hl=en&rd=1#ts=1665018%2C1665144" target="_blank">Google support page</a>.

   #### HINT
   To enable connection, select the checkbox next to <a href="https://support.google.com/accounts/answer/6010255?hl=en" target="_blank">Allow Access for Less Secure Apps Box</a>.
8. In the **Email Processing** section,  choose what happens to all the emails received in the mailbox.
   * *Do Nothing* — No actions are performed. Letters are saved in the mailbox.
   * *Convert To Lead* — Letters will be saved in the mailbox. Based on the first letter in the thread, a new Lead record will be created in the Oro application.
   * *Convert To Case* — Letters will be saved in the mailbox. Based on the first letter in the thread, a new Case record will be created in the Oro application.

   #### NOTE
   Options in the Source field should be defined in advance. This can be done through the entity manager in **System > Entities > Entity Management > Lead > Source**.
9. In the **Access Management** section, define which users will have access to the system mailbox. You can select [roles](../../../roles/index.md#user-guide-user-management-permissions) and/or specific users. All the users with defined roles and all the specifically defined users will have access to this mailbox.
10. In the **Autoresponse Rules** section, generate one or several auto-response rules. These rules determine which template is sent to the sender of the email.
11. Click **Add Rule** to add a new auto-response rule and complete the following details in the dialog:

> * *Status (Active/Inactive)* — Only rules with active statuses are applied
> * *Name* — Select the name for the rule to be used within the system.
> * *Conditions* — Define the rules according to which the rule will be applied. In the first selector, choose the field for which the condition is to be set: Body, From, Cc, Bcc. In the second selector, choose the conditions (e.g. contains, does not contain, is equal to, starts with, etc.). In the field besides the selectors, define the values where required. Click the + or **+Add** button to add another condition for the rule. Click the x button to remove the condition. All conditions are summed up (AND operator).
> * *Response Template* — Choose an [email template](../../../../emails/email-templates.md#user-guide-email-template) for auto-response.
> * *Type* — Choose if you want to use html or plain text for the email.
> * *Translations* — If you have more than one language configured in the system, select the necessary translation.
> * *Email Template* — Enter the subject and content of your email.
> * *Save Response As Email Template* — Checking the box automatically saves the current email as a template.

> Click **Add** on the bottom to save the rule.

> ![Sample autoresponse rule form](user/img/system/config_system/ar_rule.png)
1. Click **Save Settings**.

**Related Topics**

* [Configure Email Settings Globally](../../../../configuration/system/general-setup/global-email.md#admin-configuration-email-configuration-global)
* [Configure Email Settings per Website](../../../../websites/web-configuration/general-sys-config/general/website-email-settings.md#admin-configuration-system-mailboxes-website)
* [Configure Email Settings per User](../../../users/configuration/user-email-settings.md#admin-configuration-email-configuration-user)
* [Configure a System Mailbox Globally](../../../../configuration/system/general-setup/global-email.md#admin-configuration-system-mailboxes-global)

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
