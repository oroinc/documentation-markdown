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

* **Case-Insensitive Email Addresses** — If this option is enabled, the letter case is ignored when comparing email addresses. For example, [john.doe@example.com](mailto:john.doe@example.com) and [John.Doe@example.com](mailto:John.Doe@example.com) are treated equally. By default, the option is disabled. Please note that the setting only applies to back-office users. The identical option for customer users is managed [here](../../commerce/customer/global-customer-users.md#sys-config-configuration-commerce-customers-customer-users).

<a id="admin-configuration-user-settings-share"></a>

## Sharing Records

#### NOTE
Sharing Records is only available in the Enterprise edition.

Under **Sharing Records**, activate or deactivate the ability to share entity records:

* **Allow Sharing** — If this option is enabled, users are allowed to share entities in the Oro application back-office.

<a id="admin-configuration-user-settings-scim"></a>

## User Provisioning

#### HINT
This section is part of the [Identity Management Concept Guide](../../../../../concept-guides/administration/identity-management/index.md#concept-guide-identity-management) topic that provides a general understanding of external identity systems supported by OroCommerce.

#### NOTE
The SCIM synchronization is only available in the Enterprise edition.

Under **User Provisioning**, configure the SCIM (System for Cross-domain Identity Management) protocol in the Oro application. This setup allows you to import and synchronize users from external identity systems, such as Microsoft Entra ID or Okta, into Oro. Once imported, these users can log into Oro via Microsoft Entra Single Sign-On or Okta Single Sign-On.

### Enable SCIM Synchronization

To enable and control SCIM synchronization, set the following options:

* **Enable SCIM** — Enable or disable the SCIM integration on the global level.
* **Default Access to Organization Business Units** — Select the organizations and business units that will be automatically assigned to newly synchronized users.
* **Default Roles** — Select the user roles that new users will receive upon synchronization.
  > #### IMPORTANT
  > At least one organization business unit and user role should be configured in order to allow login of imported users.
* **Extra Fields Handling** — Choose how the system should handle cases when the identity provider sends extra fields. The available options are:
  > * **Return error** (default) — If selected, and the identity provider sends extra fields to Oro, the system will return an error.
  > * **Ignore extra fields** — If selected, and the identity provider sends extra fields to Oro, the system will ignore these fields.
* **Empty Name Values Handling** — Choose how the system should handle cases when the identity provider does not send first or last name values. The available options are:
  > * **Leave as is and expect validation errors** — If selected, and the identity provider sends no first or last name to Oro, the system will return an error without generating any replacement values.
  > * **Generate based on user name** (default) — If selected, the first and last name values will be copied from the username field.
  > * **Use random string** — If selected, the first and last name values will be automatically generated as random strings.

<a id="okta-provisioning-service"></a>

### Configure Okta Provisioning Service

**OroCommerce side**

To configure the user provisioning via <a href="https://help.okta.com/en-us/content/topics/provisioning/lcm/con-okta-prov.htm" target="_blank">Okta provisioning service</a> and allow importing of users from Okta to Oro, make sure you have:

1. Configured the **SCIM synchronization** globally or [per required organization](../../../user-management/organizations/org-configuration/general-setup-org/organization-user-settings.md#admin-configuration-user-settings-org).
   > #### IMPORTANT
   > At least one organization business unit and user role should be configured in order to allow login of imported users.
2. Created **Authorization Code** OAuth application as described in the [Create an OAuth Application](../../../user-management/oauth-app.md#oauth-applications) topic.
   > #### NOTE
   > You can find the redirect URL in the <a href="https://developer.okta.com/docs/guides/scim-provisioning-integration-prepare/main/#authentication" target="_blank">Okta SCIM API</a> authentication documentation which provides example URLs to use. These URLs include an identifier `{appName}` generated after you create your app integration in Okta. If the Okta application is already created, use the generated URL. Otherwise, you can temporarily specify a placeholder (fake) URL and update it later once the application is created.
   ![Creating an Okta OAuth app page](user/img/system/config_system/okta_oauth_app.png)
3. Copied **Client ID** and **Client secret**. For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you leave a page with the created application information, so make sure you save it somewhere safe so you can access it later.
   ![Client Id and Client Secret details of the Okta OAuth app](user/img/system/config_system/okta_client_id_secret.png)

**Okta side**

**Create an Okta app instance**

1. Log into your <a href="https://login.okta.com/" target="_blank">Okta Admin Console</a>.
2. Navigate to **Applications > Applications**.
3. Click **Create App Integration**.
4. Choose **SAML 2.0** sign-in method and click **Next**.

> ![Creating a new app integration on the Okta side](user/img/system/config_system/okta-create-new-app.png)
1. Provide a name and a logo for the new application and click **Next**.
2. Fill in the form with the following data and click **Next**:
   > * **Single sign-on URL**: `https://yourapplication`
   > * **Audience URI (SP Entity ID)**: `https://yourapplication`
3. Specify options that will help Okta Support understand how you configured this application and click **Finish**.

**Get Redirect URL**

As the Okta application has been successfully created, you can now add the **Redirect URL** to the OroCommerce OAuth application. You can find the redirect URL example in the <a href="https://developer.okta.com/docs/guides/scim-provisioning-integration-prepare/main/#authentication" target="_blank">Okta SCIM API</a> authentication documentation.

#### NOTE
Okta requires the **Redirect URL to follow this format**:

> `https://system-admin.okta.com/admin/app/cpc/{appName}/oauth/callback`

> The `{appName}` value is generated when you create your app integration in Okta. You can obtain it from the Admin Console URL after navigating to **Applications > Applications > your app instance**.

> The Admin Console URL has the following format:

> `https://{orgSubDomain}-admin.{oktaEnvironment}.com/admin/app/{appName}/instance/{instanceID}/#tab-general`

> The `{appName}` is the string between `/app/` and `/instance/` in the URL.
![Retrieving the appName from Okta app instance and pasting into the Redirect URL field of the Oro OAuth application](user/img/system/config_system/okta-app-name.png)

**Edit Okta app instance**

1. On the application details page, navigate to the **General** tab and click **Edit** in **App Settings**.
2. Choose **SCIM** provisioning method and click **Save**.

> ![Okta app details page](user/img/system/config_system/okta-app-details-page.png)
1. Navigate to the **Provisioning** tab and click **Edit** in **SCIM Connection**.
2. Fill in the form with the following data and click **Save**:
   > * **SCIM connector base URL**: `https://yourapplication/{backend_prefix}/scim`
   > * **Unique identifier field for users**: `userName`
   > * **Supported provisioning actions**: `Push New Users` and `Push Profile Updates`
   > * **Authentication Mode**: `OAuth 2`
   > * **Access token endpoint URI**: `https://yourapplication/oauth2-token`
   > * **Authorization endpoint URI**: `https://yourapplication/{backend_prefix}/oauth2-token/authorize`
   > * **Client ID**: The Client ID value of the OAuth 2 application
   > * **Client Secret**: The client secret of the OAuth 2 application
   ![Okta app SCIM connection details page](user/img/system/config_system/okta-app-scim-connection.png)
3. Click **Authorize with {your application}** and grant access to your application to Okta.
4. Navigate to the **Provisioning** tab, click **To App** in the left menu and click **Edit** in **Provisioning to App**.
5. Fill in the form with the following data and click **Save**:
   > * **Create Users**: Enable
   > * **Update User Attributes**: Enable
   > * **Deactivate Users**: Enable
6. Configure user mapping with the following attributes:
   > | Attribute        | Attribute Type   | Value                                                                |
   > |------------------|------------------|----------------------------------------------------------------------|
   > | userName         | Personal         |                                                                      |
   > | givenName        | Personal         | user.firstName                                                       |
   > | familyName       | Personal         | user.lastName                                                        |
   > | middleName       | Personal         | user.middleName                                                      |
   > | honorificPrefix  | Personal         | user.honorificPrefix                                                 |
   > | honorificSuffix  | Personal         | user.firstName                                                       |
   > | email            | Personal         | user.email                                                           |
   > | emailType        | Personal         | (user.email != null && user.email != ‘’) ? ‘work’ : ‘’               |
   > | title            | Personal         | user.title                                                           |
   > | primaryPhone     | Personal         | user.primaryPhone                                                    |
   > | primaryPhoneType | Personal         | (user.primaryPhone != null && user.primaryPhone != ‘’) ? ‘work’ : ‘’ |
7. Navigate to the **Assignments** tab and configure the user to be provisioned.

Once the provision is established, the users that are/will be registered within this Okta app instance will be synced to Oro. Their details will appear under **System > User Management > Users** in the OroCommerce back-office.

![Okta-imported users available under the Users menu in the OroCommerce back-office](user/img/system/config_system/okta-users.png)

#### IMPORTANT
The next step is to configure the [Okta OpenID Connect](../../../integrations/openid/index.md#user-guide-integrations-openid-connect) integration under **System > Manage Integrations** menu in the back-office to enable synced users to log into Oro via OIDC SSO.

![The Login via Okta button is available on the Oro login page after the Okta OIDC integration is created](user/img/system/config_system/okta-sso-back-office.png)

<a id="microsoft-entra-provisioning-service"></a>

### Configure Microsoft Entra Provisioning Service

**OroCommerce side**

To configure the user provisioning via <a href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service" target="_blank">Microsoft Entra provisioning service</a>, make sure you have:

1. Configured the **SCIM synchronization** globally or [per required organization](../../../user-management/organizations/org-configuration/general-setup-org/organization-user-settings.md#admin-configuration-user-settings-org).
   > #### IMPORTANT
   > At least one organization business unit and user role should be configured in order to allow login of imported users.
2. Created **Client Credentials** OAuth application as described in the [Create an OAuth Application](../../../user-management/oauth-app.md#oauth-applications) topic.
3. Copied **Client ID** and **Client secret**. For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you leave a page with the created application information, so make sure you save it somewhere safe so you can access it later.
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
   > * **Client Secret**: The client secret of the OAuth 2 application

   > ![image](user/img/system/config_system/ms_provisioning_config.png)
4. Click **Test Connection** to verify that Microsoft Entra ID can successfully connect to the SCIM endpoint. If the connection fails, an error message with details will appear.
5. If the connection is successful, click **Create** to set up the provisioning job.
6. To synchronize only specific users or groups (recommended), open the **Users and groups** tab and assign the users or groups you want to include in the synchronization.
7. In the left menu, go to **Attribute mapping**. You will see two mapping configurations — one for users and one for groups.
   * Disable group synchronization by turning off the **Provision Microsoft Entra ID Groups** mapping
   * Configure **Provision Microsoft Entra ID Users** with the following mapping settings:

   | customappsso Attribute             | Microsoft Entra ID Attribute                                |   Matching precedence |
   |------------------------------------|-------------------------------------------------------------|-----------------------|
   | userName                           | userPrincipalName                                           |                     1 |
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

Once the provision is established, the users that are/will be registered within this Okta app instance will be synced to Oro. Their details will appear under **System > User Management > Users** in the OroCommerce back-office.

![Microsoft-imported users available under the Users menu in the OroCommerce back-office](user/img/system/config_system/okta-users.png)

#### IMPORTANT
The next step is to configure the [Microsoft OpenID Connect](../../../integrations/openid/index.md#user-guide-integrations-openid-connect) integration under **System > Manage Integrations** menu in the back-office to enable synced users to log into Oro via OIDC SSO.

![The Login via Microsoft button is available on the Oro login page after the Microsoft OIDC integration is created](user/img/system/config_system/microsoft-sso-back-office.png)

**Related Articles**

* [Identity Management Concept Guide](../../../../../concept-guides/administration/identity-management/index.md#concept-guide-identity-management)
* [Configure OpenID Connect Integrations in the Back-Office](../../../integrations/openid/index.md#user-guide-integrations-openid-connect)
* [OroOidcBundle Developer Documentation](../../../../../../bundles/platform/OidcBundle/index.md#bundle-docs-platform-oidcbundle)

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
