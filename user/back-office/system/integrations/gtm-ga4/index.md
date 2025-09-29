<a id="gtm-ga-4-integration"></a>

# Configure Google Tag Manager Integration in the Back-Office (Google Analytics 4)

#### HINT
The configuration of Google Tag Manager with Google Analytics 4 is available starting from OroCommerce v4.2.13. To check which application version you are running, see the [system information](../../system-information/index.md#system-information).

Integration between your Oro application and <a href="https://support.google.com/tagmanager/answer/2574372?hl=en&topic=2574304&ctx=topic" target="_blank">Google Tag Manager</a> enables you to add tracking tags to your OroCommerce web store pages and collect information on customer behavior, purchases, product clicks, page views, etc. All this information can subsequently be shared with Google Analytics 4 (GA4), enabling you to monitor various user interactions with products on your website. This can help you get a complete picture of on-page visitor behavior, how well your marketing strategies work, and how to target your audience better.

#### HINT
This feature requires a <a href="https://marketplace.oroinc.com/orocommerce/extension/google-tag-manager-w-enhanced-ecommerce/" target="_blank">Google Tag Manager extension</a>, which you can download from the Oro Extensions Store. Next, use the composer to [install it on your application](../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

#### HINT
Please, be aware that you must have <a href="https://support.google.com/tagmanager/answer/6103696?hl=en" target="_blank">Google Tag Manager</a> and <a href="https://support.google.com/analytics/answer/9306384?hl=en&ref_topic=9303319" target="_blank">Google Analytics 4</a> accounts already created to proceed with the integration between your Oro application and Google Tag Manager and pass data to Google Analytics 4.

## On the Google Analytics Side

### Switch from Google Analytics Universal to Google Analytics 4

Google Universal Analytics (GA-UA) is deprecated on July 1, 2023 and is replaced with Google Analytics 4 (GA4). As the transition to GA4 comes with significant changes, including how data is viewed, collected, and tracked, we recommend that you create a GA4 integration well in advance of the deprecation date to ensure a seamless migration from GA-UA to GA4.

You can configure a new GA4 property alongside the existing GA-UA one. These two properties work alongside each other simultaneously, with your existing GA-UA property seeing no changes and continuing to collect data as usual. You can access both properties from the **Admin** menu panel (1) or via the property switcher on the top left of the home page (2).

![Accessing both Google Universal and Google Analytics 4 properties from the Admin panel and from the property switcher](user/img/system/integrations/gtm4/property-selector.png)

### Create a Google Analytics 4 Property

To create a GA4 property, navigate to your Google Analytics account.

There are two ways to create a new property.

**Method 1**

This method enables you to create a GA4 property in one click, copying the property name, website URL, timezone, and currency from the existing Google Universal Analytics property.

1. Click <i class="fa fa-cog" aria-hidden="true"></i> **Admin** on the bottom left.
2. Under the **Property** column, select the **Google Universal Analytics** property to copy the initial data from (e.g., name, URL, timezone, currency).
3. Click **GA4 Setup Assistant**.
4. Click **Get Started > Create Property** under *I want to create a new Google Analytics 4 property*.

Your new Google Analytics 4 property should now be created.

![Illustrating the steps to be followed to create a new GA4 property based on method 1](user/img/system/integrations/gtm4/create-GA4-property-1.png)

**Method 2**

With this method, you can create a new GA4 property from scratch, regardless of whether you are new to Google Analytics.

1. Click <i class="fas fa-cog" aria-hidden="true"></i> **Admin** on the bottom left.
2. Click **+ Create Property** under the **Property** column.
3. Provide a name for the property, select the reporting time zone and the currency. Keep in mind that Google Analytics tracks only one currency at a time. This means that if, for example, your default currency is set to **US Dollar**, but you have a multi-currency web store (available for the Enterprise edition only), a purchase of 100EUR will be tracked in the converted dollar amount of 107USD (depending on the currency rate that day).
4. Click **Next**. Select your industry category and business size.
5. Click **Create**.

![Illustrating the steps to be followed to create a new GA4 property based on method 2](user/img/system/integrations/gtm4/create-GA4-property-2.png)

#### NOTE
Remember that, unlike your GA-UA property number, which goes with the **UA** prefix as in *UA-XXXX*, your new GA4 property number is created as *XXXX* without the prefix.

![Illustrating the difference between the GA-UA and GA4 property names](user/img/system/integrations/gtm4/GAUA-vs-GA4-number.png)

### Set up a Data Stream

Once you created a property, the next step is to set up a data stream to start collecting data.

1. In your **Admin** menu, make sure you have selected the required property under the **Property** column.
2. Click **Data Streams** and select the platform (Web, Android app, or IOS app) to add a data stream. You can add as many data streams as required.

![Illustrating the steps to be performed to add a data stream](user/img/system/integrations/gtm4/add-data-stream.png)
1. For Web, provide the URL of your website (e.g., “mywebsite.com”) and a stream name. Click **Create stream**.
2. For IOS app or Android app, add the Android package name, the app name, or the App Store ID, then click **Register app**. Follow the provided instructions to finish the configuration of data streams.

Once a data stream is set, add tags to your web pages via Google Tag Manager.

![Illustrating the data stream details page](user/img/system/integrations/gtm4/data-stream-details.png)

<a id="data-stream-measurement-id"></a>

#### HINT
Keep the Measurement ID at hand, as you will need it when configuring tags in Google Tag Manager.

![Highlighting the data stream's measurement ID](user/img/system/integrations/gtm4/data-stream-measurement-id.png)

## On the Google Tag Manager Side

### Create Tags via GTM

To collect information (events) from your web store, you need to create tags in your Google Tag Manager account for each event you want to track.

There are two ways to create tags:

* [By importing our preconfigured container with the tags](#import-container-to-gtm) for all collected events. Importing pre-defined tags requires minimal effort, as each tag has already been pre-configured with triggers and variables to enable you to connect to your OroCommerce website.

Or

* [By configuring tags for all required events manually](#gtm4-create-tags-manually). Creating tags from scratch is more time-consuming but allows you to provide custom data during configuration or create tags only for specific events.

<a id="import-container-to-gtm"></a>

#### Option 1: Import a Container

We have prepared a .json file with a container that includes pre-configured tags to simplify your tag configuration process. You need to import this file into your Google Tag Manager account and substitute the dummy Measurement ID in the **GA4 var** variable with the data stream’s Measurement ID of your Google Analytics 4 account.

For that:

1. <a href="https://academy.oroinc.com/wp-content/uploads/sites/21/2023/05/oroGa4Container-24-05-23.zip" target="_blank">Download the .json file</a> with a pre-configured container.
2. Save and extract the archive on your computer.
3. In your Google Tag Manager account, navigate to **Admin > Import Container**.

![Import container in GTM](user/img/system/integrations/gtm4/import-container.png)
1. Click **Choose container file** to import the extracted .json file. The file contains 12 tags, 11 triggers, and 11 variables.
2. Choose the workspace and <a href="https://support.google.com/tagmanager/answer/6106997?hl=en" target="_blank">import</a> option.
3. Click **Confirm** to start file import.

![Confirm container import](user/img/system/integrations/gtm4/confirm-container-import.png)

The container that you have imported contains a dummy data stream’s Measurement ID for the **GA4 var** variable. You need to change the ID to be able to transfer correct data to Google Analytics 4.

To change the measurement ID for the imported variable:

1. In your Google Tag Manager Account, click **Variables** in the menu to the left.
2. In the **User-Defined Variables** section, click **GA4 var** to open its configuration page.
3. Click the **Edit** icon.

![Edit imported variable configuration](user/img/system/integrations/gtm4/edit-GA4-var-tag.png)
1. Provide the [measurement ID](#data-stream-measurement-id) of your Google Analytics data stream that follows the **G-XXXXX** pattern instead of the dummy number.
2. Click **Save** to save variable settings.
3. Click **Submit** and then **Publish** on the top right to apply the changes.

Except for the GA4 tag, the imported container also includes several pre-configured event tags.

Find the full tag list in the table below. The table compares the Google Analytics 4 tags to those of Google Universal Analytics. To customize the pre-defined parameters, refer to the <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events" target="_blank">Google Analytics 4 Event</a> developer documentation for the list of the recommended event parameters.

<a id="ga4-ga-tag-table"></a>

| Google Analytics 4 Event tag                                                                                                              | Google Universal Analytics tag                                                                                                                             |
|-------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [add_to_cart](#gtm-ga4-add-to-cart)                                                                                                       | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#add" target="_blank">addToCart</a>                         |
| [remove_from_cart](#gtm-ga4-remove-from-cart)                                                                                             | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#remove" target="_blank">removeFromCart</a>                 |
| [begin_checkout](#gtm-ga4-begin-checkout), [add_shipping_info](#gtm-ga4-add-shipping-info), [add_payment_info](#gtm-ga4-add-payment-info) | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#checkoutstep" target="_blank">checkout</a>                 |
| [select_item](#gtm-ga4-select-item)                                                                                                       | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#product-clicks" target="_blank">productClick</a>           |
| [view_item](#gtm-ga4-view-item)                                                                                                           | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#details" target="_blank">productDetail</a>                 |
| [view_item_list](#gtm-ga4-view-item-list)                                                                                                 | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#product-impressions" target="_blank">productImpression</a> |
| [select_promotion](#gtm-ga4-select-promotion)                                                                                             | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#promo-clicks" target="_blank">promotionClick</a>           |
| [view_promotion](#gtm-ga4-view-promotion)                                                                                                 | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#promo-impressions" target="_blank">promotionImpression</a> |
| [purchase](#gtm-ga4-purchase)                                                                                                             | <a href="https://developers.google.com/analytics/devguides/collection/ua/gtm/enhanced-ecommerce#purchases" target="_blank">purchase</a>                    |
| pageView                                                                                                                                  | pageView                                                                                                                                                   |

#### NOTE
Be aware that the begin_checkout, add_shipping_info, and add_payment_info GA4 tags fire after the related events occur, unlike the GA-UA checkout tag which is triggered on any checkout step, and each time a user refreshes the page.

<a id="gtm4-create-tags-manually"></a>

#### Option 2: Create Tags Manually

Google Tag Manager enables you to create one of the two tags that are passed to Google Analytics 4. Those are **Google Analytics: GA4 Configuration** as the principal configuration tag and **Google Analytics: GA4 Event**, which enables you to track custom events.

To create a **Google Analytics: GA4 Configuration** tag:

1. Navigate to the left menu of the Workspace page and click **Tags > New**.
2. Click **Tag Configuration**.
3. Select **Google Analytics: GA4 Configuration** from the tag list.
4. Enter the [measurement ID](#data-stream-measurement-id) of your Google Analytics data stream.
5. Optionally, add the parameters to configure the **Fields to Set**, **User Properties**, and **Advanced Settings** fields.
6. Click **Triggering** and select the necessary events that would fire the tag when they occur.
7. Save the tag configuration and publish it.

![The steps to be performed to configure a GA4 tag](user/img/system/integrations/gtm4/configure-GA4-tag.png)

To create a **Google Analytics: GA4 Event** tag for custom events:

1. Navigate to the left menu of the Workspace page and click **Tags > New**.
2. Click **Tag Configuration**.
3. Select **Google Analytics: GA4 Event** from the tag list.
4. For **Configuration Tag**, select the *GA4 tag* configuration tag you have just created.
5. For **Event Name**, provide the name for the event (e.g., add_to_cart). See the <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events" target="_blank">Google Analytics 4 Event</a> developer documentation for the list of recommended event parameters.
6. Under **Event Parameters**, click **Add Row**, and provide a name and a value for the parameter. Add as many parameters as required for a particular event. See the <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events" target="_blank">Google Analytics 4 Event</a> developer documentation for the list of recommended event parameters.
7. Optionally, add the parameters to configure the **User Properties** and **Advanced Settings** fields.
8. Click **Triggering** and select the necessary events that would fire the tag when they occur.
9. Save the tag configuration and publish it.

![The steps to be performed to create an add_to_cart GA4 event tag manually](user/img/system/integrations/gtm4/create-GA4-event-tag.png)

Google Analytics 4 requires the event names and parameters to comply with their regulations. To configure the manually-added tags correctly, provide the following parameters and triggers for each tag:

<a id="gtm-ga4-add-to-cart"></a>

##### add_to_cart

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#add_to_cart" target="_blank">add_to_cart</a> tag signifies that a customer user has added an item to a shopping list or submitted a request for quote.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — add_to_cart
* **Event Parameters**

| Parameter Name   | Value                  |
|------------------|------------------------|
| currency         | {{ecommerce.currency}} |
| items            | {{ecommerce.items}}    |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — add_to_cart
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-remove-from-cart"></a>

##### remove_from_cart

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#remove_from_cart" target="_blank">remove_from_cart</a> tag signifies that a customer user has removed an item from a shopping list.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — remove_from_cart
* **Event Parameters**

| Parameter Name   | Value                  |
|------------------|------------------------|
| currency         | {{ecommerce.currency}} |
| items            | {{ecommerce.items}}    |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — remove_from_cart
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-begin-checkout"></a>

##### begin_checkout

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#begin_checkout" target="_blank">begin_checkout</a> tag signifies that a customer user has started a checkout process.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — begin_checkout
* **Event Parameters**

| Parameter Name   | Value                  |
|------------------|------------------------|
| currency         | {{ecommerce.currency}} |
| items            | {{ecommerce.items}}    |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — begin_checkout
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-add-shipping-info"></a>

##### add_shipping_info

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#add_shipping_info" target="_blank">add_shipping_info</a> tag signifies that a customer user has selected a shipping method at checkout.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — add_shipping_info
* **Event Parameters**

| Parameter Name   | Value                       |
|------------------|-----------------------------|
| currency         | {{ecommerce.currency}}      |
| items            | {{ecommerce.items}}         |
| shipping_tier    | {{ecommerce.shipping_tier}} |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — add_shipping_info
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-add-payment-info"></a>

##### add_payment_info

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#add_payment_info" target="_blank">add_payment_info</a> tag signifies that a customer user has selected a payment method at checkout.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — add_payment_info
* **Event Parameters**

| Parameter Name   | Value                      |
|------------------|----------------------------|
| currency         | {{ecommerce.currency}}     |
| items            | {{ecommerce.items}}        |
| payment_type     | {{ecommerce.payment_type}} |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — add_payment_info
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-select-item"></a>

##### select_item

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#select_item" target="_blank">select_item</a> tag signifies that a customer user has clicked a product.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — select_item
* **Event Parameters**

| Parameter Name   | Value                        |
|------------------|------------------------------|
| items            | {{ecommerce.items}}          |
| item_list_name   | {{ecommerce.item_list_name}} |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — select_item
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-view-item"></a>

##### view_item

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#view_item" target="_blank">view_item</a> tag signifies that a customer user has reviewed a product details page.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — view_item
* **Event Parameters**

| Parameter Name   | Value                  |
|------------------|------------------------|
| currency         | {{ecommerce.currency}} |
| items            | {{ecommerce.items}}    |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — view_item
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-view-item-list"></a>

##### view_item_list

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#view_item_list" target="_blank">view_item_list</a> tag signifies that a customer user has looked over a list of products in a product block (top selling, featured, new arrivals, related, upsell).

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — view_item_list
* **Event Parameters**

| Parameter Name   | Value                  |
|------------------|------------------------|
| currency         | {{ecommerce.currency}} |
| items            | {{ecommerce.items}}    |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — view_item_list
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-select-promotion"></a>

##### select_promotion

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#select_promotion" target="_blank">select_promotion</a> tag signifies that a customer user has clicked a slider from the homepage slider [content block](../../../marketing/content-blocks/index.md#user-guide-landing-pages-marketing-content-blocks) on your main website page.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — select_promotion
* **Event Parameters**

| Parameter Name   | Value               |
|------------------|---------------------|
| items            | {{ecommerce.items}} |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — select_promotion
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-view-promotion"></a>

##### view_promotion

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#view_promotion" target="_blank">view_promotion</a> tag signifies that a customer user has reviewed a slider from the homepage slider block.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — view_promotion
* **Event Parameters**

| Parameter Name   | Value               |
|------------------|---------------------|
| items            | {{ecommerce.items}} |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — view_promotion
* **This trigger fires on** — All Custom Events

<a id="gtm-ga4-purchase"></a>

##### purchase

The <a href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events#purchase" target="_blank">purchase</a> tag signifies that a customer user has submitted an order.

**Tag Configuration**

* **Configuration Tag** — GA4 tag (refers to your **Google Analytics: GA4 Configuration** tag)
* **Event Name** — purchase
* **Event Parameters**

| Parameter Name   | Value                        |
|------------------|------------------------------|
| currency         | {{ecommerce.currency}}       |
| items            | {{ecommerce.items}}          |
| transaction_id   | {{ecommerce.transaction_id}} |
| affiliation      | {{ecommerce.affiliation}}    |
| coupon           | {{ecommerce.coupon}}         |
| shipping         | {{ecommerce.shipping}}       |
| tax              | {{ecommerce.tax}}            |
| shipping_tier    | {{ecommerce.shipping_tier}}  |
| payment_type     | {{ecommerce.payment_type}}   |

**Triggering**

* **Trigger Type** — Custom Event
* **Event name** — purchase
* **This trigger fires on** — Some Custom Events. For this trigger, add the following condition: *ecommerce.items > does not equal > undefined*.

## On the Oro Side

### Configure a Google Tag Manager Integration in the Back-Office

To configure a Google Tag Manager integration:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** on the top right.
3. In the **Type** field, select **Google Tag Manager**.
4. In the **Name** field, provide the name for the integration you are creating to refer to it in the Oro application. Since you can create many Google Tag Manager integrations, make sure the name is meaningful.
5. In the **Container ID** field, provide the <a href="https://support.google.com/tagmanager/answer/6103696?hl=en" target="_blank">Google Tag Manager Container ID</a>. The Container ID is located in your Google Tag Manager account on the top right of the workspace page. It is formatted as *GTM-XXXXXX*.
6. In the **Status** field, set the integration to *Active* to enable it. Should you need to disable it, select *Inactive* from the list.
7. In the **Default Owner**, select the owner of the integration.
8. Click **Save and Close**.

![Google tag manager integration creation form](user/img/system/integrations/gtm4/gtm-configuration.png)

**Next Steps**

Once the GTM integration is configured, you must connect it to the application in the system settings on the required level:

* [Enable the Google Tag Manager integration globally](../../configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google)
* [Enable the Google Tag Manager integration per organization](../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-google.md#organization-google-settings)
* [Enable the Google Tag Manager integration per website](../../websites/web-configuration/general-sys-config/integrations/index.md#website-google-settings)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
