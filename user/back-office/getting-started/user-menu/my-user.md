<a id="doc-my-user-view-page"></a>

# My User

#### IMPORTANT
The provided description covers fields and features that are default or commonly used. The actual set of available elements may vary depending on your role and other system settings.

When you log into the Oro application, you can always find a link to your user page under menu below your username. This is a fast way to access your user profile, calendar, mailbox, and task list.

## Explore Your User Page

There are a number of effective tools and actions available on the page of your user profile, from configuring your personal profile to generating an API key for third-party applications. In particular, from the page of your user profile you can:

1. **View your full name, avatar, and system information such as status, login count, date and time of the last login.**
   * The first status shows that you are granted rights to use the system. The second status is called an authentication status and shares the state of your password. As you can see your user page only when you are logged into the system, you will always see **Enabled** as the first status and **Active** as the second one. When an administrator views your page, they will able to see the values of your statuses.
     ![View the statuses of the user profile](user/img/getting_started/user_menu/my_user_review_pagetop_new.png)
   * You can also check which business unit owns your user record. Click on the owner name (e.g., Acme, General ) to open the page of the corresponding business unit. If you are logged into the organization with global access (i.e., a technical organization that aggregates data from all organizations created in the system), then in brackets you will see the name of the organization that owns the user.
     ![View the business unit of the user record](user/img/getting_started/user_menu/my_user_review_owner.png)
   * You can also see who, how, and when modified your profile by clicking **Change History** link.
2. **Access user-level configuration options.**

   In particular, you can set up localization, language, display settings, update email configuration details, as well as configure customer-visible contact information in the storefront. Read more about the available settings in the relevant [User-Level Configuration section](../../system/user-management/users/configuration/index.md#doc-my-user-configuration) of the documentation library.
3. **Edit your user profile.**

   To update the details of your profile, click **Edit** on the top right on the page. On the edit page, you can update your credentials, change the password, upload a new avatar, and update email details.
4. **Perform actions available under the More Actions menu**:
   * [Send an email](my-emails.md#user-guide-using-emails-view)
   * [Log a call](../../activities/calls/index.md#doc-activities-calls)
   * [Assign an event](../../activities/calendar-events/index.md#doc-activities-events)
   * [Edit back-office menus](../../system/menus/index.md#doc-menu-config-levels)
   * [Assign tasks](../../activities/tasks/index.md#doc-activities-tasks)
   * [Change your profile password](#user-guide-getting-started-profile-password)
   * [Reset your profile password](#user-guide-getting-started-profile-password)

   ![The More Actions menu with available options](user/img/getting_started/user_menu/My_User_More_Actions.png)

   #### NOTE
   Non-default buttons can be added to **More Actions** menu. If you see non-default buttons such as Add Task, Add Event or Add Attachment, please refer to the [Activities](../../activities/index.md#user-guide-activities) guide for more information.
5. **View your profile details aggregated under 3 sections: general information, activity, and additional information.**
   * In the **General Information** section, you can view the details of your profile, [create an API key](#doc-my-user-actions-api).
   * In the **Activity** section, you can see the emails you sent and the calls you logged. If a user mentions you as a context for their activity, this activity also appears on the list. See the [Activities](../../activities/index.md#user-guide-activities) topic for more information on activities available in the Oro application.
   * In the **Additional Information** section, you can view and manage tasks and cases related to you. See the [Activities](../../activities/index.md#user-guide-activities) topic for more information on activities available in the Oro application.

<a id="doc-my-user-actions-api"></a>

## Generate an API Key

When a third-party software requires an API key to integrate with your Oro application, you can generate it on the page of your profile.

1. Click on your user name on the top right of the screen.
2. Click **My User**.
3. In the **General Information section**, click **Generate Key** next to the API Key label.
   ![The Generate key button](user/img/getting_started/user_menu/My_User_Create_Api.png)
4. Copy the generated key and use it where required.

#### CAUTION
One user can have only one API key at a time. When you generate a new key, the old key becomes invalid.

<a id="user-guide-getting-started-profile-password"></a>

<a id="doc-my-user-actions-change-password"></a>

## Change Your Password

You can change your password to the Oro application in 3 ways:

* When editing your user profile.
* Using the **More Actions** menu on your user profile page.
* By resetting it using the **More Actions** menu on your user profile page.

#### NOTE
It is recommended to change your password after the first login, unless you use a Google account or corporate-wide credentials.

**To change your password when editing your user profile:**

1. Click on your user name on the top right of the screen.
2. Click **My User**.
3. On the page of your profile, click **Edit**.
4. In the **Password** section, provide the following information:
   * **Password** — Provide your current password.
   * **New Password** – Provide new password. It must be at least 8 characters long and include a lower case letter, an upper case letter, and a number
   * **Repeat New Password** – Confirm the new passport by typing it in once again.
5. Click **Save**. The new password will be sent to your primary email address.

**To change your password via the More Actions menu:**

1. Click on your user name on the top right of the screen.
2. Click **My User**.
3. On the page of your profile, click **More Actions > Change Password**.
   ![The change password popup dialog](user/img/getting_started/user_menu/My_User_Change_Password.png)
4. Provide a new passport in the corresponding field. Alternatively, click **Suggest Password** to generate a secure random password. To see/hide  the entered password, click the <i class="fa fa-eye" aria-hidden="true"></i> **Show** / <i class="fa fa-eye-slash" aria-hidden="true"></i> **Hide** icon next to the **New password** field.
5. Click **Save**. The new password will be sent to your primary email address.

**To reset your password via the More Actions menu**:

Only administrators can reset passwords.

1. Click on your user name on the top right of the screen.
2. Click **My User**.
3. On the page of your profile, click **More Actions > Reset Password**.
4. In the dialog box, click **Reset**. The password reset link will be sent to your (admin) primary email address.

## Add OAuth Applications

Oro applications support OAuth 2.0 credentials authorization grant type to enable connection of third-party applications to the web API. To connect a third-party application, you need to add it and configure its pre-generated credentials in the back-office of your Oro application. These credentials are managed on user level which enables generation of different credentials for various applications across multiple organizations (the multi-org functionality is only available in the Enterprise edition).

### Starting Conditions

To be able to create an OAuth application, make sure that you generate private and public encryption keys and add them to the /var directory of the installed Oro application. Although the path to the keys is predefined, you can change it by providing your custom location in the *config.yml* file.

#### NOTE
If no keys are found, the following warning message will be displayed in the back-office:

*OAuth authorization is not available as encryption keys configuration was not complete. Please contact your administrator.*

<!-- Install OAuth extension from Oro Extensions Store <link> (3.1). -->

### Add an Application

To add a new OAuth application in the back-office:

1. Click on your user name on the top right of the screen.
2. Click **My User**.
   ![Profile menu](user/img/getting_started/user_menu/oauth/my_user.png)
3. In the **OAuth Applications** section, click **Add Application** on the top right and provide the following details in the pop-up dialog:
   ![Add an oauth application](user/img/getting_started/user_menu/oauth/oauth_tab.png)
   * **Organization** — If you are adding an application within the organization with *global* access, you can select which other available organization to add the application to. This field is displayed to users with access to multiple organizations (available for the Enterprise edition only).
   * **Application Name** — Provide a meaningful name for the application you are adding.
   * **Active** — Select the **Active** check box to activate the new application.
4. Click **Create**.

A corresponding notification is sent to the primary email address of the user, the owner of oauth application. You can change the default recipient, localization, or an email content if needed by updating the [OAuth email templates](../../system/emails/email-templates.md#user-guide-using-emails-create-template) and the related [notification rule](../../system/emails/notification-rules.md#user-guide-using-emails-notifications) set out-of-the-box in the system configuration.

Once the application is created, you are provided with a Client ID and a Client Secret. Click on the <i class="fa fa-copy" aria-hidden="true"></i> icon to copy the credentials to the clipboard.

![OAuth credentials](user/img/getting_started/user_menu/oauth/oauth_credentials.png)

#### IMPORTANT
For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you close this dialog, so make sure you save it somewhere safe so you can access it later.

You can add as many applications as you need for any of your existing organizations. All added applications are displayed in the grid, and you can filter them by name, organization, and status.

#### HINT
Use the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to edit, deactivate or delete an application.

![Manage auth applications](user/img/getting_started/user_menu/oauth/manage_oauth_application.png)

Use the generated Client ID and Client Secret to retrieve an access token to connect to your Oro application.

#### NOTE
For the aggregated information on all OAuth applications created by users in the back-office, refer to the general [OAuth Applications](../../system/user-management/oauth-app.md#oauth-applications) topic.

## Configure User-Level Settings

Read the [My Configuration](my-configuration.md#doc-my-user-configuration-profile) topic for the details on how to configure available system settings for a particular user.

**Related Topics**

* [User Menu](index.md#user-guide-intro-log-in-edit-profile)
* [My Configuration](my-configuration.md#doc-my-user-configuration-profile)
* [My Emails](my-emails.md#doc-my-oro-emails)
* [My Tasks](../../activities/tasks/index.md#doc-activities-tasks)
* [My Calendar](my-calendar.md#user-guide-calendars-manage)
* [Log Out](../application-authentication/log-in-out.md#doc-log-out)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
