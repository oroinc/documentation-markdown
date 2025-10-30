<a id="user-guide-integrations-azure-oauth"></a>

# Configure Microsoft 365 OAuth Integration (Azure Active Directory Application)

Integration with Microsoft 365 via OAuth 2 API enables users to log in with their Microsoft 365 account and connect their mailbox to the Oro application using OAuth authentication.
To achieve this, you need to register a custom Azure application and connect it with your Oro application.

## Register an Application in Azure

### Create a New Azure Active Directory Application

The first step is to <a href="https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal" target="_blank">create a new Azure Active Directory application</a> on the Microsoft side:

1. Navigate to the <a href="https://portal.azure.com/" target="_blank">Azure portal</a>.
2. Ensure that you are logged into your microsoft account and access to the Azure platform is granted.
3. Open the menu on your left and click **Azure Active Directory**.
   ![Open Azure Active Directory](user/img/system/integrations/microsoft/azure-directory.png)
4. Navigate to **App Registration** and click **New Registration**.
   ![New registration button](user/img/system/integrations/microsoft/new-registration.png)
5. Provide application information and click **Register**.
   ![Register button](user/img/system/integrations/microsoft/register-application.png)
   <br/>

   Once you create the application, its basic information, such as **Application (client) ID** and **Directory (tenant) ID**, is displayed on the app’s main page section in the Essentials section.
   ![Essentials section on the main page displaying application credentials such as client id, directory id.](user/img/system/integrations/microsoft/essentials.png)

### Create a Client Secret

1. To create a password/client secret, navigate to **Manage > Certificates and Secrets**.
2. Click **New Client Secret** and fill in the form.
   ![Creating a client secret under Certificates and Secrets](user/img/system/integrations/microsoft/client-secret.png)
   <br/>

   Remember to copy the client secret as soon as you create it. You will not be able to retrieve it after you perform another operation or leave the page.

   #### IMPORTANT
   To integrate with the Oro application, make sure to use the **client secret value**, not the secret ID.
   ![Client secret value and ID on the Microsoft side](user/img/system/integrations/microsoft/client-secret-value-id.png)

### Grant API Permissions

Next, define the rights that the application will be able to grant.

1. In the panel to the left, click **API permissions**.
2. Select the permissions that your application needs access for. Try narrowing down the access to the smallest possible/required set.
   ![Api permissions](user/img/system/integrations/microsoft/api-permissions.png)
   <br/>

   The screenshot below illustrates a set of permissions for User profile + Email access to Microsoft 365 services provided by Microsoft.You can use this set to authorize IMAP/POP/SMTP access (receiving, synchronizing and sending email messages and email account information):
   ![An example of a set of permissions for user profile and email access to Microsoft 365](user/img/system/integrations/microsoft/example-permissions.png)
3. Click **Add a permission** and then **Microsoft Graph**.
   ![Microsoft graph menu](user/img/system/integrations/microsoft/graph.png)
   <br/>
4. Click **Delegated Permissions**  and select the ones that you need. You can also use **Search**.
   ![Delegated permissions list](user/img/system/integrations/microsoft/delegated-permissions.png)
   <br/>

   #### NOTE
   Some access rights may require <a href="https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/grant-admin-consent" target="_blank">Administrator Consent</a>. It is an administrative task and can be only performed by an organization admin user.
5. Click **Add permissions**.

   #### IMPORTANT
   Please be aware that in order to complete the active directory application configuration, you will need to copy the value of the **Redirect URI** from the Microsoft System Configuration Settings of your Oro application and paste it into the Azure application settings:
   ![Copy Redirect URI and paste it into the Azure application settings](user/img/system/integrations/microsoft/redirect-url-azure-side.png)

## Configure Integration in the Oro Back-Office

Once your Azure Active Directory application is configured, you can connect it to your Oro application.

For that:

1. Navigate to **System > Configuration > Integrations > Microsoft Settings**.
2. Provide the following details under **Azure Active Directory Application Settings**:
   ![Azure Active Directory Application Settings](user/img/system/config_system/azure-directory-application-settings.png)
   * **Application (Client) ID** - The client id generated on the Azure side when creating an active directory application. It is located on the main application page under **Essentials**. Selecting the *Use Default* checkbox resets the value.
   * **Client Secret** - Provide the client secret value generated on the Azure side. To integrate with the Oro application, make sure to use the *client secret value*, not the secret ID.

   ![Client secret value and ID on the Microsoft side](user/img/system/integrations/microsoft/client-secret-value-id.png)
   * **Directory (Tenant) ID** - The directory id generated on the Azure side when creating an active directory application. It is located on the main application page under **Essentials**.
   * **Redirect URI** - Copy this value and add it to your Azure Application trusted redirect URIs in order to complete the connection.

   ![How to connect Redirect URI](user/img/system/integrations/microsoft/redirect-url-azure-side.png)
3. Click **Save Settings**.

#### NOTE
To enable and configure email synchronization on the system level, please see the [Global Email Synchronization Settings](../../general-setup/global-email.md#doc-email-configuration) and [Global System Mailbox Synchronization Settings](../../general-setup/global-email.md#admin-configuration-system-mailboxes-global).

**Related Topics**

* [Configure Global Microsoft Settings](index.md#configuration-integrations-microsoft)
* [Microsoft 365 Single Sign-On](microsoft-single-sign-on.md#user-guide-integrations-microsoft-single-sign-on)
* [Microsoft 365 Integrations](microsoft-365-integrations.md#user-guide-integrations-microsoft)
