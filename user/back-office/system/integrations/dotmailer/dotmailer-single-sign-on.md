<a id="user-guide-dotmailer-single-sign-on"></a>

# Configure dotmailer Single Sign-on in the Back-Office

<a href="https://developer.dotdigital.com/docs/using-oauth-20-with-dotdigital" target="_blank">Single sign-on</a> allows to enter dotmailer account from within your OroCRM and OroCommerce applications.

To be able to use single sign-on:

1. Obtain a Client ID and a Client Secret Keys from your dotmailer manager.
2. Enter these credentials during integration configuration (see the [Configure dotmailer Integration guide](dotmailer-configuration.md#user-guide-dotmailer-configuration)).
3. The requested call back URL should be as follows: `https://{your domain}/dotmailer/oauth/callback`.
4. Navigate to **Marketing > dotmailer > Email Studio** and select the integration you wish to connect to.
5. Click **Connect** to perform OAuth authorization.

Once the connection is established, you will be able to see your dotmailer account dashboard within Email Studio in Oro application.

With the help of single sign-on, there will be no need of logging into dotmailer account every time and it will be possible to access it straight from the Oro application.

**Related Articles**

- [dotmailer Overview](index.md#user-guide-dotmailer-overview)
- [dotmailer Configuration](dotmailer-configuration.md#user-guide-dotmailer-configuration)
- [Manage dotmailer Data Fields and Mappings](../../../marketing/email-campaigns/dotmailer-data-fields-mappings.md#user-guide-dotmailer-data-fields)
- [Sending Email Campaign via dotmailer](../../../marketing/email-campaigns/sending-email-campaign-via-dotmailer.md#user-guide-dotmailer-campaign)
- [dotmailer Integration Settings](../../configuration/system/integrations/dotmailer-integration-settings.md#admin-configuration-dotmailer-integration-settings)
