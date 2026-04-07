<a id="admin-configuration-orders-ai-smart-order-settings"></a>

# Configure Global AI Smart Order Settings

#### HINT
Please <a href="https://oroinc.com/contact-us/" target="_blank">contact our support team</a> to learn more about OroCommerce AI features, discuss how they can meet your business needs, and get started with implementation.

#### NOTE
This feature is available as of OroCommerce version 5.1.14.

AI Smart Order is available for OroCommerce Enterprise and is aimed at simplifying the process of handling purchase orders. With the AI Smart Order dashboard widget, you can have emailed PDFs and other document types converted directly into draft orders in your OroCommerce application.

![AI Smart Order configuration settings and dashboard widget](user/img/system/config_commerce/order/ai-smart-order-config-global.png)

To enable this feature globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **System > Integrations > AI Smart Order** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

1. To manage any of the available options, clear the **Use Default** next to them first.
2. In the **AI Smart Order** section, select the checkbox next to *Enable AI Smart Order* to enable the feature.
3. Select the **Enable Async Processing** checkbox to process purchase orders asynchronously via the message queue, improving performance and accuracy for large or complex orders.
4. Information for the **Smart Order API Key** and **Smart Order URL** fields is provided by the Oro Team upon request during the setup of the Smart Order microservice.
5. If you have a <a href="https://extensions.oroinc.com/orocommerce/extension/customer-part-number/" target="_blank">Customer Part Number</a> extension installed, select the **Use CPN in Smart Order** check box to allow customer part numbers to be used and managed for line items during [smart order draft creation](../../../../dashboards/widgets/ai-smart-order.md#user-guide-dashboards-widgets). Please make sure that the **Customer Part Number** [feature is enabled](../../commerce/product/global-customer-settings.md#sys-commerce-product-customer-settings) under **System > Commerce > Product > Customer Settings**.
6. Click **Save Settings**.
