<a id="system-configuration-integrations-google"></a>

<a id="admin-configuration-integrations-google-gmail-oauth"></a>

# Configure Google Integration Settings in the Back-Office

To configure Google integration-related settings in the back-office:

1. Navigate to **System > Configuration** in the main menu.
2. In the panel to the left, click **System Configuration > Integrations > Google Settings**.

![Global Google Integration settings](user/img/system/config_system/google-integration-settings.png)
1. Before you begin, check out the <a href="https://support.google.com/cloud/answer/6158862?hl=en" target="_blank">instructions on obtaining credentials on the Google side</a>. Make sure that your Oro domain is included into Authorized JavaScript origins and Authorized redirect URIs.
2. In the **Google Integration Settings** section, provide the following details:
   > * **Client ID** — The Client ID generated in the API console.
   > * **Client Secret** — The Client Secret generated in the API console.
   > * **Google API Key** — The API Key generated in the API console. Provide a valid <a href="https://developers.google.com/maps/documentation/javascript/get-api-key" target="_blank">Google API key</a> to activate maps for addresses in the system.
   > * **Redirect URI** — **READ-ONLY** field, the value is auto-generated and should be added to the **Authorized Redirect URIs** configuration as described in the [Configure Google Single Sign-On](google-single-sign-on.md#user-guide-google-single-sign-on) section (Configure Consent Form > step 7).
3. In the **OAuth 2.0 for email sync** section, check **Enable** to activate synchronization with emails. Please, make sure that Gmail API is enabled in <a href="https://console.developers.google.com/apis" target="_blank">Google Developers Console</a>.
4. In the **Google Tag Manager Settings** section:
   > * Clear the **Use Default** checkbox.
   > * For the **Google Tag Manager** Integration filed, select the [GTM integration](../../../../integrations/gtm-ga4/index.md#gtm-ga-4-integration) you have configured for the application. Click **Save** to display an additional option.
   > * For **Data Collection For**, select the Google Analytics type (Universal, GA4, or both) that connects to your GTM account to enable data mapping.

**Related Topics**

* [Configure Global Google Settings](index.md#admin-configuration-integrations-google)
* [Configure Google Single Sign On](google-single-sign-on.md#user-guide-google-single-sign-on)
* [Set Up Voice and Video Calls via Hangouts](hangouts.md#user-guide-hangouts)
* [Configure Google Tag Manager Integration (Google Universal Analytics)](../../../../integrations/gtm/index.md#gtm-integration)
* [Configure Google Tag Manager Integration (GA4)](../../../../integrations/gtm-ga4/index.md#gtm-ga-4-integration)
