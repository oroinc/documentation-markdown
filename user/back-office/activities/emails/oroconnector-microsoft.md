<a id="oroconnector-for-microsoft"></a>

# OroConnector Add-in for Microsoft 365

#### NOTE
OroConnector Add-in for Microsoft 365 is available for Enterprise Edition only.

The OroConnector add-in is a valuable tool for users of the Enterprise Oro applications. It allows users to interact with Oro applications from within Outlook through an Outlook add-in. The OroConnector eliminates the need for time-consuming switching between applications, streamlining workflow processes, and improving productivity. Its seamless integration with your email client makes it a game-changer for Oro users, providing a more convenient and streamlined workflow.

## Requirements

Ensure you have the following installed on your system before proceeding:

* <a href="https://nodejs.org/en/" target="_blank">Node.js</a> (v14+ recommended)
* <a href="https://pnpm.io/" target="_blank">pnpm</a> (package manager for Node.js) – Install via:

```bash
npm install -g pnpm
```

## Set Up the Project

### Set Up the Project Manually

1. Clone the MS365 Mailbox add-in repository code to your project folder (for Enterprise customers only).
2. Install node_modules:

```bash
pnpm i
```

1. Add a new  *.env* file and set up environment variables following the example in the  *.env.example* file.
2. Run the following command to generate a manifest file:

```bash
pnpm run generate-manifest
```

1. Run the following command to create a build folder:

```bash
pnpm run build
```

1. Deploy **dist** folder on [your-addin-domain] (for example on Azure server).

### Set Up Individual Local Environment

1. Generate certificates for local environment.
   * Install office-addin-dev-certs lib:

   ```bash
   npm i -g office-addin-dev-certs
   ```

   * Generate certificates:

   ```bash
   office-addin-dev-certs install
   ```
2. Open your <a href="https://aka.ms/olksideload" target="_blank">Get add-ins window</a>.
3. Navigate to **Add-Ins for Outlook > My add-ins > Custom Addins > + Add a custom add-in > Add from file**.

![View the Get add-ins popup window](user/img/activities/connector-outlook/add-from-file.png)
1. Choose the generated manifest file.
2. Run the following command:

```bash
pnpm run dev
```

1. Open your Outlook client. Open any email and find the OroConnector add-in.

## Configure the OAuth Application

To create a new OAuth application in Oro:

Navigate to **System > User Management > OAuth Applications** in your Oro application. Create a new OAuth application with the following settings:

* **Grant Type**: Authorization Code
* **Redirect URL**: Enter the required URL in the `https://[your-addin-domain].com/grant-access-token-success` format. For local setup it should be: `https://localhost:3000/grant-access-token-success`.

![Creating a new OAuth app in the Oro application](user/img/activities/connector-outlook/oauth-app-ms.png)

Once saved, the system will generate **Client ID** and **Client Secret** for the OAuth application. Update your  *.env* file with the generated credentials, where:

```php
VITE_APP_CLIENT_ID = Client ID
VITE_APP_CLIENT_SECRET = Client Secret
```

![Pasting the newly generated client id and client secret into the env. file](user/img/activities/connector-outlook/client-id-secret.png)

#### NOTE
For more details on OAuth application configuration, refer to the [related documentation](../../system/user-management/oauth-app.md#oauth-applications).

### Deploy Production and Publish on the Internal Marketplace

1. Log in to <a href="https://entra.microsoft.com/" target="_blank">Azure Service</a>.
2. Navigate to **Applications > App registrations** and click **+ New registration** to create a new registration.

![Highlighting the New registration button on the App registrations page](user/img/activities/connector-outlook/new-registration.png)
1. Fill in the app name, choose a supported account type, and select the **Single-page application (SPA)** option from the dropdown menu under **Redirect URI**. Click **Register**.

![Highlighting the fields a user needs to fill when creating a new registration](user/img/activities/connector-outlook/registration-details.png)
1. The system will generate **Application (client) ID** and **Directory (tenant) ID** for your application. Update your  *.env* file with the generated credentials, where:

```php
VITE_APP_AZURE_CLIENT_ID: Application (client) ID
VITE_APP_AZURE_TENANT_ID: Directory (tenant) ID
```

![Pasting the newly generated application id and directory id into the env. file](user/img/activities/connector-outlook/app-id-directory-id.png)
1. Navigate to the **API permissions** subsection and click **+ Add a permission**.

![Highlighting the Add a permission button under API permissions menu](user/img/activities/connector-outlook/add-permissions.png)
1. Click **Microsoft Graph > Delegated permissions** and select the following permissions:
   * Mail > Mail.Read
   * Mail > Mail.ReadBasic
   * OpenId permissions > Openid
   * OpenId permissions > Profile
   * OpenId permissions > Email
   * User > User.Read
2. Click **Add permissions** to save the request.

![Filling the required information to request API permissions for Microsoft Graph](user/img/activities/connector-outlook/api-permissions.png)
1. Navigate to **Applications > Enterprise applications** in the main menu, then **Manage > All applications** in the submenu. Search by your application name (from Step 3) via the search field and click it.

![Illustrating the path to your newly added app in the Microsoft admin center](user/img/activities/connector-outlook/search-app-by-name.png)
1. Go to **Users and groups** submenu and click the **+ Add users/group** button.

![Steps a user needs to take to add a user or a group](user/img/activities/connector-outlook/add-user-group.png)
1. On the **Add Assignment** page, click **None Selected** under **Users** to add all required users.
2. Choose the users or groups to be added to your application and click **Select**.

![Steps a user needs to take to add a user or a group](user/img/activities/connector-outlook/select-users.png)
1. Click **Assign** to save the list.

### Set Up Add-in to Your Organization

1. Create an OAuth Application.
2. Follow the [Set Up the Project Manually]() flow.
3. Navigate to <a href="https://admin.microsoft.com/" target="_blank">MS Admin Panel</a>.
4. Go to **Settings > Integrated Apps** in the menu to the left.
5. Click **Upload custom apps**.

![Path to the Upload custom apps button](user/img/activities/connector-outlook/upload-custom-apps.png)
1. For **App type** select **Office Add-in** and provide the URL to your manifest file. Click **Next**.

![Providing the app type details and a link to the manifest file](user/img/activities/connector-outlook/upload-custom-apps-step-1.png)
1. On the **Users** step, select users with whom you want to share the OroConnector Add-in. Click **Next**.
2. Complete the details on the **Deployment** step and click **Finish Deployment**.
3. The OroConnector Add-in should now be available at the bottom of the Integrated Apps page.

![Illustrating the OroConnector Add-in at the bottom of the Integrated Apps page](user/img/activities/connector-outlook/installed-ms-add-in.png)

## Connect

Once OroConnector has been installed in your mail client, a new icon will appear in the side panel, indicating that the add-in is ready for use.

To connect the add-in to your Oro application:

1. Open the OroConnector add-in by clicking on the Oro icon.
2. Click **Connect**.
3. Provide valid Oro credentials to log in to your Oro application.
   ![image](user/img/activities/connector-outlook/login-cred.png)
4. Click **Grant** to allow the connector to access information from the Oro application.
   ![image](user/img/activities/connector-outlook/grant.png)

## Manage OroConnector Menu

The connector’s menu offers the following actions:

| **About**         | Read more information about the connector.                                                                                      |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------|
| **Disconnect**    | End the connection with the connector.                                                                                          |
| **Refresh**       | Update the connector.                                                                                                           |
| **Manage Add-in** | Access the connector’s settings. This option is only available to the organization’s administrator who installed the connector. |
![image](user/img/activities/connector-outlook/addon-menu.png)

## Search & Context

Once you have completed the setup process, OroConnector is available for you to start your search for the necessary information and add or remove context from the add-in.

In Oro applications, context is a piece of information relevant to a particular user, task, or process within the application. When an OroConnector user opens an email thread in their mail client, they can see Oro entities related to that particular email and retrieve the latest context of the conversation. Context search is performed by the *From/To/CC/BCC* fields of the email being viewed.

By default, the following data is passed from your Oro application to the connector and vice versa:

* Accounts
* Contacts
* Customer users
* Leads
* Opportunities
* Orders
* Users
* Customers
* Tasks
* Cases
* Requests for quotes.

To begin your search, type a query into the search bar and click Enter. If the search returns many entities, click **Load More** to view all available search results.

![image](user/img/activities/connector-outlook/search-result.png)

#### HINT
OroConnector will also give you prompts if there is an association with an entity, for example *Could Be Related To* or *In Context Of*.

![image](user/img/activities/connector-outlook/in-context-of-association.png)

## Manage Context

Click on the desired entity from the search results to view its details. Here, you can perform the following actions:

* **Open.**

  To view an entity you found in the OroConnector in the Oro application, click Open. You will be redirected to the view page of this entity on the Oro side.
  > ![image](user/img/activities/connector-outlook/add-open-buttons.png)
* **Add Context.**

  You can connect any relevant entities to an email thread as context. When the connector and Oro application are synchronized, you can easily view the added context on both the email and Oro application side. You can add multiple entities as necessary to provide additional context to the email.

  To add an entity as context, click **Add Context** on its details page.
* **Remove Context.**

  Removing context in the OroConnector removes it on the Oro application side as well. To disconnect entities from the email thread as its context, click **Remove Context** on the details page of the entity.
  ![image](user/img/activities/connector-outlook/remove.png)

<!-- Frontend -->
