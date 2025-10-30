<a id="admin-configuration-user-settings"></a>

# Configure Global User Settings

#### NOTE
You can configure user settings globally or [per specific organization](../../../user-management/organizations/org-configuration/general-setup-org/organization-user-settings.md#admin-configuration-user-settings-org).

To apply user-related settings, such as enabling sharing records or user provisioning, in your Oro application instance:

1. Navigate to **System > Configuration** in the main menu.
2. Click **System Configuration > General Setup > User Settings**.
   ![User settings on global level](user/img/system/config_system/user.png)

## Email Settings

Under **Email Settings**, configure the following:

* **Case-Insensitive Email Addresses** — If this option is enabled, the letter case is ignored when comparing email addresses. For example, [john.doe@example.com](mailto:john.doe@example.com) and [John.Doe@example.com](mailto:John.Doe@example.com) are treated equally. By default, the option is disabled. Be noted that the setting is only applied to back-office users. The identical option for customer users is managed [here](../../commerce/customer/global-customer-users.md#sys-config-configuration-commerce-customers-customer-users).

<a id="admin-configuration-user-settings-share"></a>

## Sharing Records

#### NOTE
Sharing Records is only available in the Enterprise edition.

Under **Sharing Records**, activate or deactivate the ability to share entity records:

* **Allow Sharing** — If this option is enabled, users are allowed to share entities in the Oro application back-office.

<a id="admin-configuration-user-settings-scim"></a>

## User Provisioning

#### NOTE
The SCIM synchronization is available as of OroCommerce Enterprise version 6.1.6.

Under **User Provisioning**, configure the SCIM (System for Cross-domain Identity Management) protocol in the Oro application. This setup allows you to import and synchronize users from external identity systems, such as Microsoft Entra ID, into Oro. Once imported, these users can log in to Oro via [Microsoft 365 Single Sign-On](../integrations/microsoft-settings/microsoft-single-sign-on.md#user-guide-integrations-microsoft-single-sign-on).

### Enable SCIM Synchronization

To enable and control SCIM synchronization, set the following options:

* **Enable SCIM** — Enable or disable the SCIM integration on the global level.
* **Default Access to Organization Business Units** — Select the organizations and business units that will be automatically assigned to newly synchronized users.
* **Default Roles** — Select the user roles that new users will receive upon synchronization.
* **Empty name values handling** — Choose how the system should handle cases when the identity provider does not send first or last name values. The available options are:
  > * **Leave as is and expect validation errors** — If selected, and the identity provider sends no first or last name to Oro, the system will return an exception without generating any replacement values.
  > * **Generate based on user name** (default) — If selected, the first and last name values will be copied from the username field.
  > * **Use random string** —  If selected, the first and last name values will be automatically generated as random strings.

<a id="microsoft-entra-provisioning-service"></a>

### Configure Microsoft Entra Provisioning Service

**OroCommerce side**

To configure the user provisioning via <a href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service" target="_blank">Microsoft Entra provisioning service</a>, make sure you have:

1. Configured the SCIM synchronization globally or [per required organization](../../../user-management/organizations/org-configuration/general-setup-org/organization-user-settings.md#admin-configuration-user-settings-org).
2. Created Client Credentials as described in the [Create an OAuth Application](../../../user-management/oauth-app.md#oauth-applications) topic.
3. Copied Client ID and Client secret. For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you close this dialog, so make sure you save it somewhere safe so you can access it later.
   > ![image](user/img/system/user_management/oauth/client_creds_app.png)

**Microsoft Entra side**

1. Log in to the <a href="https://entra.microsoft.com/" target="_blank">Microsoft Entra admin center</a> with an account that has at least <a href="https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference#application-administrator" target="_blank">Application Administrator</a> permissions.
2. Navigate to **Entra ID > Enterprise apps**.
3. Click **+New application > +Create your own application**.
4. Provide a name for the new app, select the **Integrate any other application you don’t find in the gallery** option, and then click **Add** to create an application object. The newly created app will appear in the list of enterprise applications and will open its management page.

![image](user/img/system/config_system/ms_app_create.png)
1. On the application management page, navigate to **Provisioning** in the menu to the left.
2. Click **+New configuration**.
3. Fill in the form with the following data:
   > * **Select authentication method**: OAuth2 client credentials grant
   > * **Tenant URL**: the SCIM endpoint URL of your application, for example: `https://yourapplication/scim/`, or `https://yourapplication/{backend_prefix}/scim/` if Commerce application is installed.
   > * **Token endpoint**: `https://yourapplication/oauth2-token`
   > * **Client identifier**: The Client ID value of the OAuth 2 application
   > * Client Secret: The client secret of the OAuth 2 application

   > ![image](user/img/system/config_system/ms_provisioning_config.png)
4. Click **Test Connection** to verify that Microsoft Entra ID can successfully connect to the SCIM endpoint. If the connection fails, an error message with details will appear.
5. If the connection is successful, click **Create** to set up the provisioning job.
6. To synchronize only specific users or groups (recommended), open the **Users and groups** tab and assign the users or groups you want to include in the synchronization.
7. In the left menu, go to **Attribute mapping**. You will see two mapping configurations — one for users and one for groups.
   * Disable group synchronization by turning off the **Provision Microsoft Entra ID Groups** mapping
   * Configure **Provision Microsoft Entra ID Users** with the following mapping settings:

   | customappsso Attribute             | Microsoft Entra ID Attribute                                | Matching precedence   |
   |------------------------------------|-------------------------------------------------------------|-----------------------|
   | userName                           | userPrincipalName                                           | 1                     |
   | active                             | Switch([IsSoftDeleted], , “False”, “True”, “True”, “False”) |                       |
   | title                              | jobTitle                                                    |                       |
   | emails[type eq “work”].value       | mail                                                        |                       |
   | name.givenName                     | givenName                                                   |                       |
   | name.familyName                    | surname                                                     |                       |
   | phoneNumbers[type eq “work”].value | telephoneNumber                                             |                       |
   ![image](user/img/system/config_system/ms_mapping.png)
   * Click Save to apply any changes.
8. Then, navigate to **Provision on-demand** in the left menu. Search for a user within the provisioning scope and trigger manual provisioning. Repeat this process with other users to test synchronization.
9. Once the setup is finished, open **Overview** in the left menu.
10. Select **Properties**, then click the pencil icon to edit them. Enable notification emails, enter the address to receive quarantine alerts, and turn on accidental deletion prevention. Click **Apply** to save your updates.
11. Select **Start provisioning** to launch the Microsoft Entra provisioning service.

After the initial provisioning cycle begins, go to **Provisioning logs** in the left menu to track its progress. This section displays all the actions performed by the provisioning service for your application.

After user was synced, you will be able to log in via [Microsoft 365 Single Sign-On](../integrations/microsoft-settings/microsoft-single-sign-on.md#user-guide-integrations-microsoft-single-sign-on) with such synced users.

#### IMPORTANT
The imported user must be assigned to at least one organization business unit in order to log in.

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
