<a id="doc-integrations-fedex"></a>

# Configure FedEx Shipping Integration in the Back-Office

#### HINT
This section is part of the [Shipping Configuration](../../../../concept-guides/administration/shipping-configuration/index.md#admin-guide-shipping) topic that provides a general understanding of the shipping concept in OroCommerce.

FedEx is the largest multinational delivery service company that provides a variety of shipping methods solutions, both ground and airfreight, day and overnight, to meet the customers’ requirements.

This section describes the steps that are necessary to expose FedEx as a shipping method in OroCommerce orders and quotes.

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-shipping-integrations" target="_blank">how to set up a shipping integration in OroCommerce</a> or keep reading the step-by-step guidance below.

> <iframe width="560" height="315" src="https://www.youtube.com/embed/ileKXVTG6B8" frameborder="0" allowfullscreen></iframe>

## Prepare for Integration

Before adding FedEx as a shipping method in OroCommerce, you need to create a FedEx business account and obtain a dedicated shipping account number and API keys via the official FedEx website.

### Create a FedEx Business Account

To register a business account and enable a checkout shipping integration with OroCommerce, follow the next steps:

1. Navigate to the <a href="https://www.fedex.com/en-us/home.html" target="_blank">FedEx login</a> page.
2. Click **Sign Up or Log In** and then **Open an account**.
   ![image](user/img/system/integrations/FedEx/fedex_login_page.png)
3. Click **Open an account** to register an account in several steps.
   ![image](user/img/system/integrations/FedEx/fedex_open_account.png)
4. Fill in the registration form with your personal contact information and a credit card number. Select *Business* when choosing the shipping account type. Agree to the terms and conditions and check the benefits you can get at the final step.
   ![image](user/img/system/integrations/FedEx/fedex_account_registration.png)

### Obtain a Set of Testing Credentials

Once the registration is complete, you can now obtain the necessary test keys to set up the integration between FedEx and OroCommerce and make sure the integration is working properly.

Follow the official <a href="https://developer.fedex.com/api/en-us/get-started.html#step3" target="_blank">FedEx step-to-step guide</a>, the *Create organization* and *Create API project* sections,
to get the test credentials.

As result, you will have

> ![image](user/img/system/integrations/FedEx/fedex_api_project.png)
> * **Project API Key** in the API KEY field
> * **Project API Secret Key** in the SECRET KEY field
> * **Shipping Account Number** in the ACCOUNT field

## Configure a FedEx Integration in OroCommerce

#### NOTE
FedEx has package weight and size limits for shipping. Please check <a href="https://www.fedex.com/content/dam/fedex/us-united-states/services/GrlPkgGuidelines_fxcom.pdf" target="_blank">the FedEx website for more details</a>.

To enable the integration with FedEx in order to request the shipping cost estimation and/or request the shipping services:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration**.
3. On the **Create Integration** page, select *FedEx* for **Type**.
   ![image](user/img/system/integrations/FedEx/fedex_create_integration.png)
4. Type in the *Common Integration Details*:
   * **Name** – the shipping method name that is shown as an option for shipping configuration in the OroCommerce back-office.
   * **Label** – the shipping method name/label that is shown as a shipping option for the buyer in the OroCommerce storefront during the checkout.

Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. Click the <i class="fas fa-language" aria-hidden="true"></i> **Default Language** icon to return to the single-language view.

1. Set the **Test Mode** checkbox into the necessary state. Enable it if you are using the test FedEx access key and disable for the production access.

   #### NOTE
   For security reasons, it is critically important to use the mode that matches your environment and the FedEx access key type.

   #### WARNING
   Never use the FedEx access key that is dedicated for the production environment in your sandbox/test OroCommerce environment.

   Never enable **Test Mode** for the FedEx integration on your production instance of OroCommerce.
2. Provide the connection credentials which you have received from FedEx:
   * Project API Key
   * Project API Secret Key
   * Shipping Account Number
3. Select the available pickup type that applies to the deliveries for the shipping methods via this integration:
   * FedEx will be contacted to request a pickup.
   * Shipment will be dropped off at a FedEx Location.
   * Shipment will be picked up as part of a regular scheduled pickup.
4. Select a unit of weight to use for the shipping price calculation: a pound or kilogram.

   #### NOTE
   The unit of weight should match the options supported by your FedEx account.
5. Select the FedEx shipping services that are supported in the OroCommerce shipping options. Hold the CTRL key to select/deselect multiple options.
6. Click **Check FedEx Connection** to ensure FedEx API is accessible.
7. Set the status to **Active** to enable the integration.
8. The **Default Owner** field is prepopulated with the user creating the integration. You can change this value to a different user, if necessary.

#### NOTE
In the **Synchronization Settings** section, select the **Log Warnings** checkbox if you want all synchronization errors to be written into the application log.

1. Click **Save and Close**.

Next, set up a shipping rule via the [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules) page to enable this shipping method for all or some customer orders.

Once the shipping method is added to the shipping rule, provide the information that configures the shipping fee components and the method to calculate it following the [Configure a Shipping Method in a Shipping Rule](../../shipping-rules/index.md#doc-shipping-rules-shipping-methods-detailed) topic.

## Obtain a Set of Production Credentials

Once you have successfully configured the OroCommerce FedEx integration, and the connection to the test environment is working properly, you can move to a production stage and request a new set of credentials.

To get production credentials, follow the official <a href="https://developer.fedex.com/api/en-us/get-started.html#step3" target="_blank">FedEx step-to-step guide</a>, the *Create organization* and *Create API project* sections.

After obtaining production credentials, follow the steps described in the aforementioned [Configure a FedEx Integration in OroCommerce]() section to set up the production integration between FedEx and OroCommerce.

> #### IMPORTANT
> Make sure that the **Test Mode** checkbox is NOT selected as you are configuring the production integration.

## Update the FedEx Integration From the Previous Version

The previous version of the FedEx Shipping Integration used the SOAP API to communicate between Oro and FedEx.

As of May 15, 2024, the SOAP API is deprecated, and FedEx offers to switch to a new REST API which uses OAuth Authorization.

If you have the configured integration for the old API, this integration will still be working until FedEx cancels it.

That is why, when you check or update the existing integration, you will see the old fields marked as deprecated. To update the integration, input new credentials.

**Related Topics**

* [Shipping Configuration Concept Guide](../../../../concept-guides/administration/shipping-configuration/index.md#admin-guide-shipping)
* [System Shipping Configuration](../../configuration/commerce/shipping/index.md#configuration-guide-commerce-configuration-shipping)
* [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
