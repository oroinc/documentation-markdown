<a id="gtm-integration"></a>

# Configure Google Tag Manager Integration in the Back-Office (Google Universal Analytics)

Integration between your Oro application and <a href="https://support.google.com/tagmanager/answer/2574372?hl=en&topic=2574304&ctx=topic" target="_blank">Google Tag Manager</a> enables you to add tracking tags to your OroCommerce web store pages with the help of <a href="https://developers.google.com/tag-manager/enhanced-ecommerce" target="_blank">Enhanced E-commerce</a> and collect information on customer behavior, purchases, product clicks, page views, etc. All this information can subsequently be shared with Google Analytics to measure various user interactions with products on your website through <a href="https://support.google.com/analytics/answer/6014872?hl=en" target="_blank">E-Commerce reports</a>. This can help you get a full picture of on-page visitor behavior, how well your marketing strategies work, and how to target your audience better.

#### HINT
The feature requires extension, so visit Oro Extensions Store to download the <a href="https://marketplace.oroinc.com/orocommerce/extension/google-tag-manager-w-enhanced-ecommerce/" target="_blank">Google Tag Manager extension</a> and then use the composer to [install the extension to your application](../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

In this topic, we are going to illustrate how to [integrate your Oro application with Google Tag Manager](#gtm-integration-oro-side) and pass data to Google Analytics using two methods:

* By importing a pre-configured container with pre-defined tags and triggers for all collected events, or
* By configuring tags for all required events manually

#### HINT
Please, be aware that you must have <a href="https://support.google.com/tagmanager/answer/6103696?hl=en" target="_blank">Google Tag Manager</a> and <a href="https://support.google.com/analytics/answer/1009694?hl=en" target="_blank">Google Analytics</a> accounts already created to proceed with the integration between your Oro application and Google Tag Manager, and pass data to Google Analytics.

## Configure Google Universal Analytics Settings

<a id="ga-tracking-id"></a>

### Retrieve Tracking ID

You require <a href="https://support.google.com/analytics/answer/7372977" target="_blank">Google Analytics Tracking ID</a> to configure your Google Tag Manager variable for the tag that tracks events on your OroCommerce website.

The Tracking ID is located in your Google Analytics account under **Admin > Tracking Info > Tracking Code**.

> ![Tracking ID in Google Analytics](user/img/system/integrations/gtm/tracking_id.png)

Keep the ID at hand when you start configuring tags in Google Tag Manager.

### Enable Google Analytics Enhanced E-Commerce

<a href="https://developers.google.com/tag-manager/enhanced-ecommerce" target="_blank">Google Analytics Enhanced E-commerce</a> enables you to get better insights into the shopping behavior of your web store users (e.g., by offering you out-of-the-box reports on products, brands, orders). It sends valuable data, such as product impressions, promotions, and sales data with any of your Google Analytics page views and events. You can use page views to track product impressions and product purchases, and use events to track checkout steps and product clicks.

You need to enable Enhanced E-commerce in your Google Analytics account and map your checkout steps to retrieve the data collected by Google Tag Manager on your OroCommerce website. Please keep in mind that in order for Enhanced E-commerce to retrieve and process information, you need to select Data Layer as a source of E-commerce data when configuring tags in Google Tag Manager.

To enable Enhanced E-commerce:

1. Navigate to your Google Analytics account, and click **Admin > All Web Site Data > E-commerce Settings**.
   ![Enhanced E-commerce setup](user/img/system/integrations/gtm/ecommerce_settings.png)
2. Toggle the switches to set **Enable E-commerce** and **Enable Enhanced E-commerce Reporting** to **ON**.
   ![Enable E-commerce and Reporting](user/img/system/integrations/gtm/ecommerce_switcher.png)
3. In the **Checkout Labeling** section, add your checkout steps to the funnel.

   The following screenshot illustrates mapping of the checkout steps of the default OroCommerce web store.
   > ![Mapping checkout steps to Enhanced E-commerce](user/img/system/integrations/gtm/mapping_checkout_steps.png)

   Adding checkout steps of your web store enables you to track checkout behavior.

1. Click **Save**

#### IMPORTANT
Google Analytics tracks only one currency at a time. This means that if, for example, your default currency is set to **US dollars**, but you have a multi-currency web store (available for the Enterprise edition only), a purchase of 100EUR will be tracked in the converted dollar amount of 113USD (depending on the currency rate that day). To set the default currency in your Google Analytics account, navigate to **Admin > View Settings > Basic Settings > Currency displayed as**.

![Currency settings in Google Analytics](user/img/system/integrations/gtm/tracked_currency.png)

## Configure Google Tag Manager Settings

To collect information (events) from your web store, you need to create tags in your Google Tag Manager account for each event that you want to track. Enhanced E-commerce enables you to track and collect information about the following events:

* [Page Views](#page-views)
* [Product Impressions](#product-impressions)
* [Product Clicks](#product-clicks)
* [Add to Cart](#add-to-cart)
* [Remove from Cart](#remove-from-cart)
* [Promotion Impressions](#promotion-impressions)
* [Promotion Clicks](#promotion-clicks)
* [Checkout](#checkout-event)
* [Purchases](#purchase-event)

You can either import pre-defined tags that we have configured for all types of events that can be collected for Enhanced E-commerce, or create tags manually for those events that you would like to track. Importing pre-defined tags requires minimal efforts, as each tag has already been pre-configured with triggers and variables that will enable you to connect to your OroCommerce website. Creating tags from scratch requires more time but allows you to provide custom data during configuration, or create tags only for specific events.

<a id="gtm-container-id"></a>

### Retrieve Container ID

You require <a href="https://support.google.com/tagmanager/answer/6103696?hl=en" target="_blank">Google Tag Manager Container ID</a> to integrate with your Oro application.

The Container ID is located in your Google Tag Manager account on the top right of the workspace page. It is formatted as *GTM-XXXXXX*.

![Container id in Google Tag Manager account](user/img/system/integrations/gtm/containder_id.png)

Keep the container ID at hand when you start creating an [integration](#gtm-integration-oro-side) between Google Tag Manager and OroCommerce.

### Option 1: Import Container

To simplify tag configuration, download a .json file with a container that includes tags that have already been pre-defined for your convenience. All you need to do is import this file into your Google Tag Manager account, and substitute the dummy Tracking ID in the variable to the Tracking ID of your Google Analytics account.

![Minimal effort GTM integration](user/img/system/integrations/gtm/import_gtm_container.png)

Follow the steps below to complete import:

1. <a href="https://academy.oroinc.com/wp-content/uploads/sites/21/2023/05/oroUaContainer-24-05-23.zip" target="_blank">Download the .json file</a> with a pre-configured container.
2. Save and extract the archive on your computer.
3. In your Google Tag Manager account, navigate to **Admin > Import Container**.
   ![Import container in GTM](user/img/system/integrations/gtm/import_container.png)
4. Click **Choose container file** to import the extracted .json file. The file contains 10 tags, 9 triggers, and 6 variables.
5. Choose the workspace and <a href="https://support.google.com/tagmanager/answer/6106997?hl=en" target="_blank">import</a> option.
   ![Confirm container import](user/img/system/integrations/gtm/confirm_import.png)
6. Click **Confirm** to start file import.

The container that you have imported contains a dummy Tracking ID number. You need to change the ID to be able to transfer correct data to Google Analytics.

To change the tracking ID for the imported variable:

1. In your Google Tag Manager Account, click **Variables** in the left menu pane.
2. In the **User-defined Variables** section, click **GA var** to open its configuration page.
   > ![Open imported variable](user/img/system/integrations/gtm/user_defined_variable.png)
3. Click the **Edit** icon
   ![Edit imported variable configuration](user/img/system/integrations/gtm/edit_variable.png)
4. Provide your [Google Analytics Tracking ID](#ga-tracking-id) number that follows the **UA-XXXXXXXXX-1** instead of the dummy number.
5. Click **Save** to save variable settings.

### Option 2: Configure Tags Manually

To start collecting information from your web store, you need to create a variable and triggers to populate tags for all or selected events that you want to track on your website. When configuring tags manually, make sure that:

* The variable is of Google Analytics Type
* Tags have *Enable Enhanced Ecommerce Features* enabled
* Tags use *Data Layer* to store information and pass it to Google Analytics

![A diagram showing complete GTM integration](user/img/system/integrations/gtm/full_gtm_intgration.png)

<a id="create-gtm-variable"></a>

#### Create a Variable

To create a variable that enables you to configure Google Analytics settings for the tags:

1. In the left pane menu of your workspace, click **Variables** and then **New**.
2. Provide variable name, e.g., {{GA var}}.
3. Click **Variable Configuration**.
4. For **Variable Type**, select *Google Analytics Settings*. This setting ensures that tracking data is sent to Google Analytics.
5. Provide the Tracking ID from your Google Analytics account.

   #### HINT
   The Tracking ID is located in your Google Analytics account under **Admin > Tracking Info > Tracking Code**.
6. Click **Save**.

#### Create Tags

To create a new tag, navigate to the left side of the main interface, click **Tags** and then **New**.

![Create a tag via Google Tag Manager's left panel](user/img/system/integrations/gtm/create_tag_alternative.png)

Further configuration options depend on the event type that you want to track.

<a id="add-to-cart"></a>

##### addToCart

To track when items are added to customer user shopping lists in your web store, create an *addToCart* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — addToCart tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — addToCart
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — addToCart
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![addToCart tag configuration details](user/img/system/integrations/gtm/addToCart.png)

<a id="remove-from-cart"></a>

##### removeFromCart

To track when items are removed from customer user shopping lists in your web store, create a *removeFromCart* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — removeFromCart tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — removeFromCart
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — removeFromCart
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![removeFromCart tag configuration details](user/img/system/integrations/gtm/removeFromCart.png)

<a id="checkout-event"></a>

##### checkout

To measure each step in a checkout process, create a *checkout* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — checkout tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — checkout
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — checkout
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![checkout tag configuration details](user/img/system/integrations/gtm/checkout.png)

<a id="product-clicks"></a>

##### productClick

To measure product clicks, create a *productClick* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — productClick tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — productClick
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — productClick
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![productClick tag configuration details](user/img/system/integrations/gtm/productClick.png)

<a id="product-detail"></a>

##### productDetail

To track product detail views, create a *productDetail* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — productDetail tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — productDetail
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — productDetail tag
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![productDetail tag configuration details](user/img/system/integrations/gtm/productDetail.png)

<a id="product-impressions"></a>

##### productImpression

To track how many times a product was seen on the web page, create a *productImpression* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — productImpression tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — productImpression
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — productImpression
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![productImpression tag configuration details](user/img/system/integrations/gtm/productImpression.png)

<a id="promotion-clicks"></a>

##### promotionClick

To measure clicks on promotions on your website, create a *promotionClick* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — promotionClick tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — promotionClick
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — promotionClick
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![productClick tag configuration details](user/img/system/integrations/gtm/promotionClick.png)

<a id="promotion-impressions"></a>

##### promotionImpression

To track how many times a promotion was seen on the web page, create a *promotionImpression* tag.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — promotionImpression tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — promotionImpression
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — promotionImpression
* **Trigger Type** — Custom Event
* **The trigger fires on** — All Custom Events

![promotionImpression tag configuration details](user/img/system/integrations/gtm/promotionImpression.png)

<a id="purchase-event"></a>

##### purchase

To collect transaction details once the order was placed, create a *purchase* tag:

To configure it correctly, provide the following tag, trigger, and variable configuration options:

**Tag Configuration**

* **Name** — purchase tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — purchase
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — purchase
* **Trigger Type** — Custom Event
* **The trigger fires on** — Some Custom Events. For this trigger, add the following condition: *ecommerce.items > equals > undefined*.

![purchase tag configuration details](user/img/system/integrations/gtm/purchase.png)

<a id="page-views"></a>

##### pageView

To track each time a page loads in a web browser, create a *pageView* tag.

#### NOTE
The pageView tag is a universal tag for tracking any page and is used in the guide as an implementation example. For the E-Commerce flow, productDetail tag is used.

To configure it correctly, provide the following tag, trigger, and variable configuration options:

* **Name** — pageView tag
* **Track Type** — Event
* **Category** — Ecommerce
* **Action** — pageView
* **Google Analytics Settings** — [{{GA var}}](#create-gtm-variable)
* **Enable overriding settings in this tag** — Yes
* **Tracking ID** — Inherited from Settings variable
* **More Settings > Ecommerce > Enable Enhanced Ecommerce Features** — True
* **Use Data Layer** — Yes

**Triggering**

* **Name** — All Pages
* **Trigger Type** — Page View

![pageView tag configuration details](user/img/system/integrations/gtm/pageView.png)

<a id="gtm-integration-oro-side"></a>

## Create and Enable Google Tag Manager Integration

To create a new integration with Google Tag Manager in your Oro application:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** on the top right.
3. In the **Type** fields, select **Google Tag Manager**.
4. In the **Name** field, provide the name for the integration you are creating to refer to it in the Oro application. Since you can create many Google Tag Manager integrations, make sure the name is meaningful.
5. In the **Container ID** field, provide the [container ID](#gtm-container-id) that follows the *GTM-XXXXXXX* pattern. You can find container ID in your Google Tag Manager Account.
   ![Container id in Google Tag Manager account](user/img/system/integrations/gtm/containder_id.png)
6. In the **Status** field, set the integration to *Active* to enable it. Should you need to disable it, select *Inactive* from the list.
   ![Google tag manager integration creation form](user/img/system/integrations/gtm/gtm_integration.png)
7. In the **Default Owner**, select the owner of the integration.
8. Click **Save and Close**.

Once the integration is saved, it becomes available in the Integrations grid under **System > Integrations > Manage Integrations**.

#### IMPORTANT
To enable a Google Tag Manager integration for data mapping, connect it to the application in the system settings [globally](../../configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google), [per organization](../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-google.md#organization-google-settings) or [website](../../websites/web-configuration/general-sys-config/integrations/index.md#website-google-settings).

#### BUSINESS TIP
## Business Tip

Do you want to reap the benefits of the new digital commerce trend? Learn more about the <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B online marketplace</a> and how it can help you expand into a new market.
