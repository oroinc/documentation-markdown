<a id="user-guide-my-profile-oauth"></a>

# Add OAuth Applications under My User Menu

<!-- begin_user_oauth -->

Oro applications support OAuth 2.0 credentials authorization grant type to enable connection of third-party applications to the web API. To connect a third-party application, you need to add it and configure its pre-generated credentials in the back-office of your Oro application. These credentials are managed on user level which enables generation of different credentials for various applications across multiple organizations (the multi-org functionality is only available in the Enterprise edition).

## Starting Conditions

To be able to create an OAuth application, make sure that you generate private and public encryption keys and add them to the /var directory of the installed Oro application. Although the path to the keys is predefined, you can change it by providing your custom location in the *config.yml* file.

#### NOTE
If no keys are found, the following warning message will be displayed in the back-office:

*OAuth authorization is not available as encryption keys configuration was not complete. Please contact your administrator.*

<!-- Install OAuth extension from Oro Extensions Store <link> (3.1). -->

## Add an Application

To add a new OAuth application in the back-office:

1. Click on your user name on the top right of the screen.
2. Click **My User**.
   ![Profile menu](user/img/getting_started/user_menu/oauth/my_user.png)
3. In the **OAuth Applications** section, click **Add Application** on the top right and provide the following details in the pop-up dialog:
   ![Add an oauth application](user/img/getting_started/user_menu/oauth/oauth_tab.png)
   * **Organization** — If you are adding an application within the organization with *global* access, you can select which other available organization to add the application to. This field is displayed to users with access to multiple organizations (available for the Enterprise edition only).
   * **Application Name** — Provide a meaningful name for the application you are adding.
   * **Active** — Select the **Active** checkbox to activate the new application.
4. Click **Create**.

A corresponding notification is sent to the user’s primary email address, the owner of the oauth application. You can change the default recipient, localization, or an email content if needed by updating the [OAuth email templates](../../system/emails/email-templates.md#user-guide-using-emails-create-template) and the related [notification rule](../../system/emails/notification-rules.md#user-guide-using-emails-notifications) set out-of-the-box in the system configuration.

Once the application is created, you are provided with a Client ID and a Client Secret. Click on the <i class="fa fa-copy" aria-hidden="true"></i> icon to copy the credentials to the clipboard.

![OAuth credentials](user/img/getting_started/user_menu/oauth/oauth_credentials.png)

#### IMPORTANT
For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you close this dialog, so make sure you save it somewhere safe to access it later.

You can add as many applications as you need for any of your existing organizations. All added applications are displayed in the grid; you can filter them by name, organization, and status.

#### HINT
Use the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to edit, deactivate or delete an application.

![Manage auth applications](user/img/getting_started/user_menu/oauth/manage_oauth_application.png)

Use the generated Client ID and Client Secret to retrieve an access token to connect to your Oro application.

#### NOTE
For the aggregated information on all OAuth applications created by users in the back-office, refer to the general [OAuth Applications](../../system/user-management/oauth-app.md#oauth-applications) topic.

<!-- finish_user_oauth -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
