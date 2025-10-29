<a id="oroconnector-for-google-workspace"></a>

# OroConnector Add-on for Google Workspace

#### NOTE
OroConnector Add-on for Google Workspace is available for Enterprise Edition only.

The OroConnector add-on is a valuable tool for users of the Enterprise Oro applications. It allows users to interact with Oro applications from within Gmail through a Google Apps Script-based addon. It offers OAuth authentication, data synchronization, and UI integration with the Oro platform. The OroConnector eliminates the need for time-consuming switching between applications, streamlining workflow processes, and improving productivity. Its seamless integration with your email client makes it a game-changer for Oro users, providing a more convenient and streamlined workflow.

## Requirements

Ensure you have the following installed on your system before proceeding:

* <a href="https://nodejs.org/en/" target="_blank">Node.js</a> (v14+ recommended)
* <a href="https://pnpm.io/" target="_blank">pnpm</a> (package manager for Node.js) – Install via:

```bash
npm install -g pnpm
```

* <a href="https://github.com/google/clasp" target="_blank">Google Apps Script CLI (clasp)</a> Install via:

```bash
npm install -g @google/clasp
```

## Set Up the Project

Follow the steps below to set up a project:

**1. Clone the** <a href="https://github.com/oroinc/google-workspace-addon" target="_blank">Google Workspace add-on repository</a> **code to your project folder** (for Enterprise customers only).\*\*

**2. Log in to your Google Account**:

Before proceeding, log in to your Google Account and authorize clasp to access the necessary resources:

```bash
clasp login
```

Next, grant the following permissions:

* See, edit, configure, and delete your Google Cloud data.
* Manage your Google API service configuration.
* Publish this application as a web app or a service that may share your data.
* View log data for your projects.
* Create and update Google Apps Script deployments.
* Create and update Google Apps Script projects.

**3. Enable the Apps Script API**:

You need to enable the Apps Script API for your project. Visit the following URL to do so: <a href="https://script.google.com/home/usersettings" target="_blank">Enable Apps Script API</a>. If you have enabled this API recently, please wait a few minutes for the action to propagate and then retry the previous step.

**4. Create a new project in Google Apps Script**

To create a new project in Google Apps Script, run the following command:

```bash
clasp create --title "[your title]" --type standalone
```

This command creates a new project with the specified title and type. The project will be created in the current directory.

**5. Configure the project**:

* Open the `.clasp.json` file and add `/build` to the end of the `rootDir` path.
* Copy the `.clasp.json` file to the `config/development` and `config/production` directories.
* Create a `.env` file by copying the `.env.example` file.
* Run the following command to download all the required packages:

```bash
pnpm install
```

* Generate the images object in base64 format inside the `assets-config/images.ts` file by running:

```bash
pnpm run build:images
```

* Build the project for production by running:

```bash
pnpm run build:prod
```

* Push the code to Google Apps Script by running:

```bash
pnpm run sync
```

## Configure the OAuth Application

### Create OAuth Application

To create a new OAuth application in Oro:

Navigate to **System > User Management > OAuth Applications** in your Oro application. Create a new OAuth application with the following settings:

* **Grant Type**: Authorization Code
* **Redirect URL**: Enter the required URL in the `https://script.google.com/macros/d/{Script ID}/usercallback` format. For {Script ID}, use your Google Workspace **Script ID**. To locate the script ID, go to <a href="https://script.google.com/" target="_blank">Google Apps Script</a> and open your project “[your title]” > Project Settings > IDs.

![Script Id location in a Google workspace inserted to Oro application](user/img/activities/connector-gmail/script-id.png)

Once saved, the system will generate the **Client ID** and **Client Secret** for the OAuth application. Save it somewhere safe as we will need it in the next step of configuring the Goggle Workspace.

#### NOTE
For more details on OAuth application configuration, refer to the [related documentation](../../system/user-management/oauth-app.md#oauth-applications).

### Configure Google Workspace

1. Navigate to <a href="https://script.google.com/" target="_blank">Google Apps Script</a> and open your project > Project Settings > Script Properties:
2. Create new script properties with the following keys:
   > * **url**: Your Oro application URL (e.g., `https://oroinc.oro-cloud.com`)
   > * **clientId**: The OAuth client ID from the Oro application
   > * **clientSecret**: The OAuth client secret from the Oro application
   > * **backOfficePrefix**: Back-office prefix in Oro application (optional) (e.g., *admin*)
   > * **isHardReset**: Set to `true`/`false` for resetting storage without redeployment (optional)

![Script Properties details in a Google workspace](user/img/activities/connector-gmail/script-properties.png)

## Deploy the Project

### Test Deployments

To check and verify the project, you can install its test version:

1. Navigate to <a href="https://script.google.com/" target="_blank">Google Apps Script</a> and open your project.
2. Click **Deploy > Test deployments** next to the project name.
3. Click **Install** for applications: Gmail, Calendar.
4. Open Gmail and verify that the add-on is available on the side panel.

#### NOTE
For more detailed instructions, refer to the <a href="https://developers.google.com/workspace/add-ons/how-tos/testing-workspace-addons" target="_blank">public documentation</a>.

![Installing test deployments](user/img/activities/connector-gmail/test-deployments.png)

### Deploy Production and Publish on the Internal Marketplace

**Step 1: Configure OAuth Consent Screen**

1. Go to <a href="https://console.cloud.google.com/" target="_blank">Google Cloud Console</a> > APIs & Services > OAuth Consent Screen.

![Oauth consent screen location in a Google Cloud Console](user/img/activities/connector-gmail/oauth-consent-screen.png)
1. Select **Internal** for the user type (only available for Google Workspace accounts) and click **Create**.

![Selecting Internal user type for oauth consent screen in a Google Cloud Console](user/img/activities/connector-gmail/internal-user-type.png)
1. Fill in the required fields, including:

* App Name
* User Support Email
* Developer Contact Information

![Filling in the required fields for oauth consent screen in a Google Cloud Console](user/img/activities/connector-gmail/fill-contact-info-oauth.png)
1. Click **Save and Continue**.
2. You can skip the Scopes step by clicking **Save and Continue**.

![Skipping the Scopes step for oauth consent screen in a Google Cloud Console](user/img/activities/connector-gmail/skip-scopes-step.png)
1. Review and confirm your configuration, then go to **Cloud Overview > Dashboard** in the navigation menu.

![Display the Dashboard button under Cloud Overview](user/img/activities/connector-gmail/go-back-to-dashboard.png)

**Step 2: Link Google Cloud Project to Apps Script**

1. In the <a href="https://script.google.com/" target="_blank">Google Apps Script</a> page, open your project.
2. Go to **Settings** and click **Change Project**.

![Display the Change Project button under Settings](user/img/activities/connector-gmail/change-project-app-script.png)
1. Copy the Project Number from your Google Cloud Console (found in the Google Cloud Console Dashboard).
2. Paste this Project Number into the **GCP project number** field in the Settings page in Apps Script.

![Pasting the Project Number into the GCP project number field](user/img/activities/connector-gmail/gcp-project-number.png)
1. Click **Set project** to save the GCP project number.

**Step 3: Deploy the Add-on**

1. In the <a href="https://script.google.com/" target="_blank">Google Apps Script</a> page, open your project.
2. Click **Deploy > New deployment** next to the project name.

![Clicking the New Deployment button in the Deploy dropdown](user/img/activities/connector-gmail/new-deployment.png)
1. Select **Add-on** as the deployment configuration type.

![Selecting **Add-on** in the configuration dropdown](user/img/activities/connector-gmail/selecting-addon.png)
1. Fill in the description.
2. Click **Deploy** to complete the deployment.

![New deployment creation page](user/img/activities/connector-gmail/addon-description.png)
1. Copy the Deployment ID (you’ll need this in later steps).

![Displaying the created deployment ID](user/img/activities/connector-gmail/deployment-id.png)

**Step 4: Enable Google Workspace Marketplace SDK**

1. Go to <a href="https://console.cloud.google.com/" target="_blank">Google Cloud Console</a> > your project > APIs & Services.
2. Click **Enabled APIs & services**.

![Display the Enable APIs and Services menu under APIs & Services](user/img/activities/connector-gmail/api-services.png)
1. Search for **Google Workspace Marketplace SDK** and enable it for your project.

![Google Workspace Marketplace SDK details page](user/img/activities/connector-gmail/enable-marketplace-sdk.png)

**Step 5: Configure the App for Marketplace**

1. Go to the Google Workspace Marketplace SDK configuration page in the Google Cloud Console.
2. Click the **App Configuration** tab and set App Visibility to **Private**.

![Setting visibility of Google Workspace Marketplace SDK to private](user/img/activities/connector-gmail/app-configuration.png)
1. In the App integration section, select **Google Workspace Add-on** as the app type.
2. Choose **Deploy using Apps Script deployment ID**.
3. Paste the **Deployment ID** from Step 3 into the Deployment ID field.

![Configuring the app integration](user/img/activities/connector-gmail/app-integration.png)
1. Complete the required fields and click **Save**.

![Filling the details under Developer Information](user/img/activities/connector-gmail/developer-information.png)

**Step 6: Store Listing**

1. Navigate to the **Store Listing** tab.
2. Provide all required information for your app, including:
   > * App name
   > * Short description
   > * Detailed description

![Store Listing tab details page](user/img/activities/connector-gmail/store-listing.png)
1. Upload the icons for different screen sizes as required (e.g., 128x128, 256x256).

![Uploading the icons for different screen sizes](user/img/activities/connector-gmail/graphics-asset.png)
1. Complete any remaining fields.
2. Click **Publish** to submit the add-on.

**Step 7: Install the Add-on**

1. Once published, open the published link from the Google Workspace Marketplace.

![Displaying the published link from the Google Workspace Marketplace](user/img/activities/connector-gmail/app-URL.png)
1. Install the app as an admin for your Google Workspace domain.

![Installing the app from the Google Workspace Marketplace](user/img/activities/connector-gmail/install-application.png)
1. Open Gmail or the desired Google Workspace app and verify that the add-on is available on the side panel.

![View the OroConnector add-on on the side panel of the Gmail account](user/img/activities/connector-gmail/gmail-addon.png)

#### NOTE
For more detailed instructions, refer to the <a href="https://developers.google.com/workspace/add-ons/how-tos/publish-add-on-overview" target="_blank">public documentation</a>.

## Connect

Once OroConnector has been installed in your mail client, a new icon will appear in the side panel, indicating that the add-on is ready for use.

To connect the add-on to your Oro application:

1. Open the OroConnector add-on by clicking on the Oro icon.
2. Click **Connect**.
3. Provide valid Oro credentials to log in to your Oro application.
   ![image](user/img/activities/connector-gmail/credentials-login.png)
4. Click **Grant** to allow the connector to access information from the Oro application.
   ![image](user/img/activities/connector-gmail/connect-grant.png)

## Manage OroConnector Menu

The connector’s menu offers the following actions:

| **About**         | Read more information about the connector.                                                                                      |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------|
| **Disconnect**    | End the connection with the connector.                                                                                          |
| **Refresh**       | Update the connector.                                                                                                           |
| **Manage Add-on** | Access the connector’s settings. This option is only available to the organization’s administrator who installed the connector. |
![image](user/img/activities/connector-gmail/menu.png)

## Search & Context

Once you have completed the setup process, OroConnector is available for you to start your search for the necessary information and add or remove context from the add-on.

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

![image](user/img/activities/connector-gmail/context-search.png)

#### HINT
OroConnector will also give you prompts if there is an association with an entity, for example *Could Be Related To* or *In Context Of*.

![image](user/img/activities/connector-gmail/search.png)

## Manage Context

Click on the desired entity from the search results to view its details. Here, you can perform the following actions:

* **Open.**

  To view an entity you found in the OroConnector in the Oro application, click Open. You will be redirected to the view page of this entity on the Oro side.
  > ![image](user/img/activities/connector-gmail/open-context.png)
* **Add Context.**

  You can connect any relevant entities to an email thread as context. When the connector and Oro application are synchronized, you can easily view the added context on both the email and Oro application side. You can add multiple entities as necessary to provide additional context to the email.
  ![image](user/img/activities/connector-gmail/open-context-2.png)

  To add an entity as context, click **Add Context** on its details page. Alternatively, you can click on the chain icon next to the required entity in the search results.
  ![image](user/img/activities/connector-gmail/link-context-from-list.png)
* **Remove Context.**

  Removing context in the OroConnector removes it on the Oro application side as well. To disconnect entities from the email thread as its context, click **Remove Context** on the details page of the entity.
  ![image](user/img/activities/connector-gmail/remove-context-button.png)

  Alternatively, click X next to the required entity in the search results.

![image](user/img/activities/connector-gmail/remove-entity.png)

## Update the Project

To update the project, follow these steps:

1. Update the local development branch:

```bash
git pull origin main
```

1. Modify the environment variables (if necessary) by updating the  *.env* file.
2. Reinstall dependencies:

```bash
pnpm install
```

1. Rebuild the images (if necessary):

```bash
pnpm run build:images
```

1. Rebuild the project for production:

```bash
pnpm run build:prod
```

1. Push the updated code to Google Apps Script:

```bash
pnpm run sync
```

<!-- Frontend -->
