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
4. In the **Google Tag Manager Settings** section, clear the **Use Default** checkbox and select a [Google Tag Manager Integration](../../../../integrations/gtm/index.md#gtm-ga-4-integration) from the list to configure it for the application and enable data mapping.

#### NOTE
You can enable cross-domain tracking to be able to track user interactions across multiple domains using a single GA4 property. See the <a href="https://developers.google.com/tag-platform/devguides/cross-domain#when_to_implement_cross-domain_measurement" target="_blank">Implement Cross-Domain Measurement</a> article on the Google website for more information.

**Related Topics**

* [Configure Global Google Settings](index.md#admin-configuration-integrations-google)
* [Configure Google Single Sign On](google-single-sign-on.md#user-guide-google-single-sign-on)
* [Configure Google Tag Manager Integration](../../../../integrations/gtm/index.md#gtm-ga-4-integration)
