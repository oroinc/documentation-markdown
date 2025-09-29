# Manage Users in the Back-Office

<a id="doc-user-management-users-actions-enable"></a>

<a id="doc-user-management-users-actions-disable"></a>

## Enable/Disable a User

To enable or disable a user in the Oro application:

1. Navigate to **System > User Management > Users**.
2. In record table, click once on the name of the selected user to open their page.
3. On page of the selected user, click <i class="fa fa-check fa-lg" aria-hidden="true"></i> **Enable User**/ <i class="fa fa-ban fa-lg" aria-hidden="true"></i> **Disable User** on the top right.
   ![image](user/img/system/user_management/user_enable.png)![image](user/img/system/user_management/user_disable.png)

   #### NOTE
   Alternatively, you can <i class="fa fa-check fa-lg" aria-hidden="true"></i> enable and <i class="fa fa-ban fa-lg" aria-hidden="true"></i> disable users from the record table. Hover over the ellipsis menu at the end of the row of the selected user and click on the corresponding icon.
   > ![image](user/img/system/user_management/all_users_grid.png)

   Keep in mind that besides the page with all users, you can get to the pages of only active or disabled users, or those who cannot log in.
   > ![image](user/img/system/user_management/users_saved_views.png)

## Enable/Disable Multiple Users

To enable/disable several users at the same time, use mass actions:

1. Navigate to **System > User Management > Users**.
2. In the table of all users, select the check boxes in front of the names of those users whose passwords you want to reset.
3. Click the ellipsis menu at the right end of the table header row and then click <i class="fa fa-check fa-lg" aria-hidden="true"></i> **Enable** or <i class="fa fa-ban fa-lg" aria-hidden="true"></i> **Disable**.
   ![image](user/img/system/user_management/users_enable_disable_mass_action.png)

<a id="doc-user-management-users-actions-activate"></a>

## Activate a User

When a user exceed the allowed number of failed login attempts, the system automatically locks them out. User authentication status changes to **Locked**, and the **Activate** button appears on the user page.

To activate a user:

1. Navigate to **System > User Management > Users** in the main menu.
2. Click on the selected user once to open their page.
3. On the user page, click the **Activate** on the top right.
   ![image](user/img/system/user_management/user_activate.png)

   The user authentication status changes from **Locked** to **Active**.

<a id="doc-user-management-users-actions-delete"></a>

## Delete a User

To delete a user from the system:

1. Navigate to **System > User Management > Users**.
2. In the table of all users, hover over the ellipsis menu at the end of the row of the selected user and click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete**.

   #### IMPORTANT
   Keep in mind that you can delete only those users who have no records assigned to them.

   ![image](user/img/system/user_management/users_delete.png)
3. In the **Deletion Confirmation** dialog box, click **Yes, Delete**.

   #### NOTE
   Alternatively, you can delete a user from their user page by clicking the **Delete** on the top right.

   ![image](user/img/system/user_management/user_page_delete.png)

<a id="doc-user-management-users-actions-export"></a>

## Export Multiple Users

You can export all user records into a .csv file. The exported file will contain all user record fields marked to be exported in the **User** entity settings. For more information about configuring which fields will be exported, see the [Entity Fields](../../entities/entity-fields/index.md#admin-guide-create-entity-fields) topic.

#### NOTE
All existing user records are exported at once. Passwords are stored and exported in the hashed form.

To export user records:

1. Navigate to **System > User Management > Users**.
2. On the page of all users, click **Export** on the top right.
3. When the export job finishes, you will receive a notification to your primary email address.
   ![image](user/img/system/user_management/users_grid_export.png)![image](user/img/system/user_management/users_export_csv.png)

<a id="doc-user-management-users-actions-api"></a>

## Generate an API Key for a User

Integration with third-party software sometimes requires API access to the Oro application. A user can generate an API key to grant access to the required API while protecting their password from being disclosed to the third party.

1. Navigate to **System > User Management > Users** in the main menu.
2. On the page of all users, click once on the selected user to open their page.
3. In the **General Information**, click **Generate Key** next to the **API Key** field.
   ![image](user/img/system/user_management/users_generate_api_key.png)

Once the API key is generated, the user can execute API requests via the sandbox, Curl command, any other REST client, or use the API via the custom application.

#### IMPORTANT
Only one key can be generated for one user within one organization.

<a id="doc-user-management-users-actions-change-password"></a>

<a id="doc-user-management-users-actions-reset-password"></a>

## Change/Reset User Passwords

You can change and reset the password for a specific user on their profile page in the **More Actions** menu:

> ![image](user/img/system/user_management/user_page_change_reset_password.png)
1. Navigate to **System > User Management > Users**.
2. On the page of all users, click once on the selected user to open their page.
3. On the user page, click **More Actions** on the top right.
   * Click <i class="fa fa-key fa-lg" aria-hidden="true"></i> **Change Password** to open a new dialog and provide a new password. Alternatively, you can click the **Suggest Password** link to generate a secure random password. To see / hide  the entered password, click the <i class="fa fa-eye" aria-hidden="true"></i> **Show**/<i class="fa fa-eye-slash" aria-hidden="true"></i> **Hide** icon next to the **New password** field. Once a new password is provided, a reset password email is sent to this user.
     ![image](user/img/system/user_management/user_change_password.png)
   * Click <i class="fa fa-unlock-alt" aria-hidden="true"></i> **Reset Password** to send an email to the user with a new password.
     ![image](user/img/system/user_management/user_reset_password.png)

     The user will not be able to log into the application until their password is changed. In this case, the user authentication status changes to **Password reset**. It will return to **Active** when the user changes the password.
     ![image](user/img/system/user_management/user_password_reset.png)

#### NOTE
Alternatively, you can reset password for a specific user from the table of all users. For this, hover over the ellipsis menu at the end of the row of the selected user, and click **Reset Password**.

![image](user/img/system/user_management/user_reset_password_from_grid.png)

<a id="doc-user-management-users-actions-reset-password-multiple"></a>

## Reset Multiple Passwords

When you suspect a security breach, you can reset passwords for multiple users at the same time:

1. Navigate to **System > User Management > Users**.
2. In the table of all users, select the check boxes in front of the names of those users whose passwords you want to reset.
3. Click the ellipsis menu at the right end of the table header row and then click <i class="fa fa-unlock-alt" aria-hidden="true"></i> **Reset Password**.
4. In the **Reset Password** dialog box, click **Reset**. The password reset links are sent to the primary email addresses of the selected users.

#### IMPORTANT
The users will not be able to log into the application until their passwords are changed. Note that user authentication statuses change to **Password reset**. They will return to **Active** when the users complete password change procedure.

![image](user/img/system/user_management/users_mass_reset_passwords.png)

<a id="user-guide-add-oauth-to-user"></a>

## Add OAuth Applications to a User

Oro applications support OAuth 2.0 credentials authorization grant type to enable connection of third-party applications to the web API. To connect a third-party application, you need to add it and configure its pre-generated credentials in the back-office of your Oro application. These credentials are managed on user level which enables generation of different credentials for various applications across multiple organizations (the multi-org functionality is only available in the Enterprise edition).

### Starting Conditions

To be able to create an OAuth application, make sure that you generate private and public encryption keys and add them to the /var directory of the installed Oro application. Although the path to the keys is predefined, you can change it by providing your custom location in the *config.yml* file.

#### NOTE
If no keys are found, the following warning message will be displayed in the back-office:

*OAuth authorization is not available as encryption keys configuration was not complete. Please contact your administrator.*

<!-- Install OAuth extension from Oro Extensions Store <link> (3.1). -->

### Add an Application

To add a new OAuth application in the back-office:

1. Navigate to **System > User Management > Users** in the main menu.
2. Click on a user name that you want to add an OAuth application to.
3. In the **OAuth Applications** section, click **Add Application** on the top right and provide the following details in the pop-up dialog:
   ![Add an oauth application](user/img/getting_started/user_menu/oauth/oauth_tab.png)
   * **Organization** — If you are adding an application within the organization with *global* access, you can select which other available organization to add the application to. This field is displayed to users with access to multiple organizations. Keep in mind that the multi-org functionality is only available in the Enterprise edition.
   * **Application Name** — Provide a meaningful name for the application you are adding.
   * **Active** — Select the **Active** check box to activate the new application.
4. Click **Create**.

A corresponding notification is sent to the user’s primary email address, the owner of the OAuth application. You can change the default recipient, localization, or email contents if needed by updating the [OAuth email templates](../../emails/email-templates.md#user-guide-using-emails-create-template) and the related [notification rule](../../emails/notification-rules.md#user-guide-using-emails-notifications) set out-of-the-box in the system configuration.

Once the application is created, you are provided with a Client ID and a Client Secret. Click on the <i class="fa fa-copy" aria-hidden="true"></i> icon to copy the credentials to the clipboard.

![OAuth credentials](user/img/getting_started/user_menu/oauth/oauth_credentials.png)

#### IMPORTANT
For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you close this dialog, so make sure you save it somewhere safe to access it later.

You can add as many applications as you need for any of your existing organizations. All added applications are displayed in the grid, and you can filter them by name, organization, and status.

#### HINT
Use the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to edit, deactivate or delete an application.

![Manage auth applications](user/img/getting_started/user_menu/oauth/manage_oauth_application.png)

Use the generated Client ID and Client Secret to retrieve an access token to connect to your Oro application.

#### NOTE
For the aggregated information on all OAuth applications created by users in the back-office, refer to the general [OAuth Applications](../oauth-app.md#oauth-applications) topic.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
