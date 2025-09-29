<a id="user-guide-dotmailer-configuration"></a>

<a id="user-guide-dotmailer-configuration-dotmailer-side"></a>

# Configure Dotdigital Integration in the Back-Office

## Create API Managed User on the Dotdigital Side

To configure integration with OroCRM and OroCommerce on the Dotdigital side, create **an API managed user**:

1. Log in to Dotdigital.
2. Navigate to **Settings > Access**.
   ![Open the Access menu to create a new user](user/img/marketing/marketing/dotdigital/access.png)
3. Click the **New User** button.

   Your unique email address is generated in the **Email Address** field. You need this email address to configure Oro integration with Dotdigital.
4. Create and confirm your **Password**. The **Description** field is optional. Mark your user **Enabled** and click **Save** to proceed.
   ![Creating a new user](user/img/marketing/marketing/dotdigital/dotdigital_api_users_new_user_details.png)

<a id="user-guide-dotmailer-configuration-oro-side"></a>

## Create Integration on the Oro Application Side

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** in the upper-right corner of the page.
   ![Creating the integration on the Oro application side](user/img/marketing/marketing/dotdigital/oro_create_dotdigital_integration_new.png)
3. Complete the following fields:

   | Field                   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Type**                | Select Dotdigital from the list of integrations available in the dropdown.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
   | **Name**                | Enter the integration name to refer to within the system.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   | **Username**            | Enter an API user name from your Dotdigital **Manage users** page.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   | **Password**            | Enter the password you set for your API user on the Dotdigital side. Click **Check connection**. **Connection Successful** message indicates that connection to Dotdigital has been established.                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
   | **Client ID**           | The Dotdigital uses OAuth 2.0 to provide single <a href="https://developer.dotdigital.com/docs/using-oauth-20-with-dotdigital" target="_blank">sign-on</a>. Client ID is the ID of the OAuth 2.0 making the request. Single sign-on provides the means for a Dotdigital user to log into their account just once, removing the need to constantly re-enter credentials. To register to use OAuth you will need to be on a Dotdigital Enterprise license and to contact your Dotdigital account manager. More information on sign-on is available in the [Configure Single Sign-on](dotdigital-single-sign-on.md#user-guide-dotmailer-single-sign-on) section of the guide. |
   | **Client Secret key**   | The pre-shared client secret, used to authenticate your application when making token request.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   | **Custom OAuth Domain** | Enter custom domain if it is used in Dotdigital. By default <a href="https://r1-app.dotdigital.com/" target="_blank">https://r1-app.dotdigital.com/</a> is used.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
   | **Default Owner**       | Select the owner of the integration. The selected user will be defined as the owner for all the records imported within the integration.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
4. Once all the details of the integration have been specified, click **Save and Close**.

   As soon as the integration is successfully configured, it will appear in the integration grid.

   In addition, **dotdigital menu group** will become available under **Marketing** in the main menu.

   The Dotdigital menu group contains the following sections:
   - **Email Studio** (see [Configure Single Sign-on guide](dotdigital-single-sign-on.md#user-guide-dotmailer-single-sign-on))
   - **Data Fields** (see [Manage Dotdigital Data Fields and Mappings guide](../../../marketing/email-campaigns/dotdigital-data-fields-mappings.md#user-guide-dotmailer-data-fields))
   - **Data Field Mappings** (see [Manage Dotdigital Data Fields and Mappings guide](../../../marketing/email-campaigns/dotdigital-data-fields-mappings.md#user-guide-dotmailer-data-fields))

   ![The dotdigital menu under the Marketing main menu](user/img/marketing/marketing/dotdigital/dotdigital-menu.png)

### Sync Dotdigital Integration

To sync Dotdigital integration:

1. Navigate to **System > Integrations > Manage Integrations**.
2. Select the newly created integration.
3. Click **Schedule Sync** in the upper-right corner of the page.

#### BUSINESS TIP
### Business Tip

Are you considering <a href="https://oroinc.com/b2b-ecommerce/what-is-b2b-ecommerce/" target="_blank">B2B eCommerce</a> for your business? Make a business case using our in-depth guide, which is filled with useful statistics and examples.

**Related Articles**

- [Dotdigital Overview](index.md#user-guide-dotmailer-overview)
- [Dotdigital Single Sign-on](dotdigital-single-sign-on.md#user-guide-dotmailer-single-sign-on)
- [Manage Dotdigital Data Fields and Mappings](../../../marketing/email-campaigns/dotdigital-data-fields-mappings.md#user-guide-dotmailer-data-fields)
- [Sending Email Campaign via Dotdigital](../../../marketing/email-campaigns/sending-email-campaign-via-dotdigital.md#user-guide-dotmailer-campaign)
- [Dotdigital Integration Settings](../../configuration/system/integrations/dotdigital-integration-settings.md#admin-configuration-dotmailer-integration-settings)
