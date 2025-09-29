<a id="user-guide-google-single-sign-on"></a>

# Configure Google Single Sign-On in the Back-Office

Oro application supports Google Single Sign-On. This means that for a user that has the same primary email in the Oro application and Google accounts, it is enough to log in only once during a session.

## Google Side

### Create Project

To configure single sign-on on the Google side:

1. Open <a href="https://console.developers.google.com/start" target="_blank">Google API Console</a>.
2. Navigate to **My Project** selector in the top left corner and click **Create Project**.
   ![Create a project in the Google API console](user/img/google/create_project.png)
3. Define the **Project Name** and click **Create**.
   ![A new project page](user/img/google/new_project.jpg)

### Create Credentials

1. Click **Credentials** in the menu on the left and open the **Credentials** tab.
   ![The Credentials tab details](user/img/google/create_credentials.jpg)
2. Click **Create Credentials** and select **0Auth client ID.**
   ![A list of available credential options](user/img/google/create_credentials_2.jpg)
3. To create an OAuth client ID, first set a product name on the consent screen.

### Configure Consent Form

1. Click **Configure Consent Screen**.
   ![Settings under the Credentials menu](user/img/google/consent_form.jpg)
2. Complete the form by providing the following details:

> - Your email address
> - Project name
> - Homepage URL
> - Product logo
> - Private Policy URL
> - Terms of Service URL

> ![The details you need to provide to configure the consent form](user/img/google/complete_form.jpg)
1. Click **Save** to launch the **Create Client ID** page.
2. Set the **Application Type** to **Web Application**.
3. For **Authorized JavaScript Origins**, enter the URL of the Oro application instance for which single sign-on is being enabled.
4. **Authorized Redirect URIs** are unified resource names used for the interaction between Google and the Oro application instance. It is recommended to add the following two values:
   * [Oro application instance URL]/admin/login/check-google
   * [Oro application instance URL]/index.php/admin/login/check-google
5. Click **Create Client ID**.
   ![The Create Client ID page](user/img/google/create_id.jpg)

#### NOTE
Please pay attention to the **Authorized Redirect URIs**, the value from the **System > Configuration > Integrations > Google Settings > Google Integration Settings > Redirect URI** must be added in Authorized Redirect URIs configuration.

1. Your client ID is generated.
   ![OAuth client ID and secret](user/img/google/id_secret.jpg)![A new client ID is added to the list of all IDs](user/img/google/id_secret_2.jpg)

## Oro Application Side

### Configure Google Single Sign-On

To configure the integration with Google Single Sign-On in your OroCRM or OroCommerce application:

1. Navigate to **System > Configuration > Integrations > Google Settings** in the main menu.
2. Make sure that the information in the **Google Integration Settings** and **OAuth 2.0 for Gmail emails sync** is filled as described in the [Configure Google Integration Settings](google-integration.md#system-configuration-integrations-google) topic.
3. Define the following fields for **Google Sign-on:**
   * **Enable** — Check **Enable** to activate Google Single Sign-on.
   * **Domains** — Domains is a comma separated list of allowed domains. It limits the list of mailboxes for which single sign-on can be used (e.g., only a domain used specifically by your company). Leave the field empty to set no such limitation

![Global Google integration settings](user/img/system/config_system/google_integration_new.png)

### Log in with Google

When a user opens the login page of the instance with the enabled single sign-on capability, the **Login Using Google** link is displayed.

![The login page with the link to log in via google](user/img/google/login_using_google.jpg)

If the user is not logged into their Google account, then clicking the button triggers opening a usual Google login page.

As soon as the user logs into their Google account, they need to accept the policy of using the application.

As soon as the user has logged into their Google account, a request to use the account in order to login to the Oro application is displayed (details defined for the consent screen is used).

![Google account page](user/img/google/google_connection.jpg)

Now, a Google-registered user can click the **Login using Google** button to enter the Oro application.

#### NOTE
Note that the email used for the Google account and the primary email of the user in the Oro application must be the same.

**Related Topics**

* [Configure Global Google Settings](index.md#admin-configuration-integrations-google)
* [Configure Google Integration Settings](google-integration.md#system-configuration-integrations-google)
* [Set Up Voice and Video Calls via Hangouts](hangouts.md#user-guide-hangouts)
* [Configure Google Tag Manager Integration](../../../../integrations/gtm/index.md#gtm-integration)
