<a id="user-guide-dotmailer-single-sign-on"></a>

# Configure Dotdigital Single Sign-on in the Back-Office

<a href="https://developer.dotdigital.com/docs/using-oauth-20-with-dotdigital" target="_blank">Single sign-on</a> allows to enter Dotdigital account from within your Oro applications.

To be able to use single sign-on:

1. Obtain a Client ID and a Client Secret Keys from your Dotdigital manager.
2. Enter these credentials during integration configuration (see the [Configure Dotdigital Integration guide](dotdigital-configuration.md#user-guide-dotmailer-configuration)).
3. The requested call back URL should be as follows: `https://{your domain}/dotdigital/oauth/callback`.
4. Navigate to **Marketing > dotdigital > Email Studio** and select the integration you wish to connect to.
5. Click **Connect** to perform OAuth authorization.

Once the connection is established, you will be able to see your Dotdigital account dashboard within Email Studio in Oro application.

With the help of single sign-on, there will be no need of logging into Dotdigital account every time and it will be possible to access it straight from the Oro application.

**Related Articles**

- [Dotdigital Overview](index.md#user-guide-dotmailer-overview)
- [Dotdigital Configuration](dotdigital-configuration.md#user-guide-dotmailer-configuration)
- [Manage Dotdigital Data Fields and Mappings](../../../marketing/email-campaigns/dotdigital-data-fields-mappings.md#user-guide-dotmailer-data-fields)
- [Sending Email Campaign via Dotdigital](../../../marketing/email-campaigns/sending-email-campaign-via-dotdigital.md#user-guide-dotmailer-campaign)
- [Dotdigital Integration Settings](../../configuration/system/integrations/dotdigital-integration-settings.md#admin-configuration-dotmailer-integration-settings)
