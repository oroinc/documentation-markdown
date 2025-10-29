<a id="doc-integrations-ups"></a>

# Configure UPS Shipping Integration in the Back-Office

#### HINT
This section is part of the [Shipping Configuration](../../../../concept-guides/administration/shipping-configuration/index.md#admin-guide-shipping) topic that provides a general understanding of the shipping concept in OroCommerce.

UPS shipping integration section describes the steps that are necessary to expose UPS as a shipping method in OroCommerce orders and quotes.

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-shipping-integrations" target="_blank">how to set up a shipping integration in OroCommerce</a> or keep reading the step-by-step guidance below.

> <iframe width="560" height="315" src="https://www.youtube.com/embed/ileKXVTG6B8" frameborder="0" allowfullscreen></iframe>

## Prepare for Integration

First, ensure you have <a href="https://www.ups.com/one-to-one/register" target="_blank">registered with UPS.com</a> and have opened a UPS Account with the necessary shipping services level.

Next:

1. Log in to <a href="https://ups.com" target="_blank">ups.com</a>.
2. Navigate to <a href="https://www.ups.com/upsdeveloperkit/" target="_blank">UPS Developer Kit</a> in the **Support > Technology Support** section.
3. <a href="https://www.ups.com/upsdeveloperkit/requestaccesskey?loc=en_US" target="_blank">Request an access key</a> (e.g., 5F235F292A54F51F).

Please, ensure that you have requested separate access keys for your test and production environments.

## Configure a UPS Integration in OroCommerce

#### NOTE
UPS has package weight and size limits for shipping. Please check <a href="https://www.ups.com/us/en/shipping/order-supplies.page" target="_blank">the UPS website for more details</a>.

To enable communication with UPS in order to request the shipping cost estimate and/or request the shipping services, establish a connection with UPS API:

1. Navigate to the **Manage Integrations** page by clicking **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** and select **UPS** as integration type:
   ![image](user/img/system/integrations/CreateUPSIntegration.png)
3. Type in **Basic Information**:

* **Name** – the shipping method name that is shown as an option for shipping configuration in the OroCommerce back-office.
* **Label** – the shipping method name/label that is shown as a shipping option for the buyer in the OroCommerce storefront on the checkout.
* **Status** - set the status to **Active** to enable the integration.

1. Set the **Test Mode** into the necessary state. Enable it if you are using the test UPS access key and disable for production access.

   #### NOTE
   For security reasons, it is critically important to use the mode that matches your environment and the UPS access key type.

   #### WARNING
   Never use the UPS access key that is dedicated for the production environment in your sandbox/test OroCommerce environment.

   Never enable the Test Mode for the UPS integration on your production instance of OroCommerce.
2. Provide the UPS connection details: OAuth Client Id and OAuth Client Secret to connect. Click **Check UPS Connection** to ensure UPS API is accessible.
   > #### NOTE
   > For the case when you update existing integration, you may see the additional deprecated **API user (Deprecated)**, **API Password (Deprecated)**, **API Key (Deprecated)** fields.

   > Please follow the <a href="https://developer.ups.com/oauth-developer-guide?loc=en_US" target="_blank">UPS Migration Guide</a> to finalize the migration to OAuth authentication.
   > ![image](user/img/system/integrations/UpdateUPSIntegration.png)

   > #### WARNING
   > As of June 2024, you will no longer be able to transact with UPS APIs using an access key for authentication and are required to update your security model to OAuth 2.0
3. Provide the UPS service account details:
   * Shipping account name
   * Shipping account number
4. Select the pickup type that shall apply to the deliveries for the shipping methods via this integration. Available options are:
   * Regular Daily Pickup
   * Customer Counter
   * One Time Pickup
   * On Call Air
   * Letter Center
5. Select unit of weight to use for the shipping price calculation.

   #### NOTE
   The unit of weight should be in sync with the options that are supported by your UPS account.
6. Select the destination country. To support shipping globally, create a dedicated UPS integration (e.g., UPS USA, UPS UK, UPS Germany, etc) for every country you would like to cover with UPS shipping services.

   Once you select the destination, the list of shipping services appears.
7. Select the UPS shipping services that should be supported in the OroCommerce shipping options. Use *Ctrl*/*Shift* to select multiple options.
8. Set status to **Active** to enable the integration.

#### NOTE
In the **Synchronization Settings** section, select the **Log Warnings** checkbox if you want all synchronization errors to be written into the application log.

1. Click **Save**.

Next, set up a shipping rule via the [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules) page to enable this shipping method for all or some customer orders.

Once the shipping method is added to the shipping rule, provide the information that configures the shipping fee components and the method to calculate it following the [Configure a Shipping Method in a Shipping Rule](../../shipping-rules/index.md#doc-shipping-rules-shipping-methods-detailed) topic.

**Related Topics**

* [Shipping Configuration Concept Guide](../../../../concept-guides/administration/shipping-configuration/index.md#admin-guide-shipping)
* [System Shipping Configuration](../../configuration/commerce/shipping/index.md#configuration-guide-commerce-configuration-shipping)
* [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules)
