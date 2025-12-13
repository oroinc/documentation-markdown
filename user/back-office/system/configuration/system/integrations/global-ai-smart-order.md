<a id="admin-configuration-orders-ai-smart-order-settings"></a>

# Configure Global AI Smart Order Settings

#### NOTE
Please <a href="https://oroinc.com/contact-us/" target="_blank">contact our support team</a> to learn more about OroCommerce AI features, discuss how they can meet your business needs, and get started with implementation.

#### HINT
This section is part of the [AI and Automation Concept Guide](../../../../../concept-guides/ai/index.md#concept-guide-ai) topic that provides an overview of OroCommerce’s AI-powered tools AI Smart Agent and AI Smart Order.

AI Smart Order is available for OroCommerce Enterprise and is aimed at simplifying the process of handling purchase orders. With AI Smart Order feature that includes a [dashboard widget](../../../../dashboards/widgets/ai-smart-order.md#user-guide-dashboards-widgets) and [an email automation](../../../../sales/orders/create.md#user-guide-sales-orders-create-from-ai-smart-order), you can have emailed PDFs and other document types converted directly into draft orders in your OroCommerce application.

![AI Smart Order configuration settings and dashboard widget](user/img/system/config_commerce/order/ai-smart-order-config-global.png)

To enable this feature globally:

1. Navigate to **System > Configuration** in the main menu.
2. In the menu to the left, click **System Configuration > Integrations > AI Smart Order**.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

1. In the **AI Smart Order** section, clear the **Use Default** checkbox and select the checkbox next to *Enable AI Smart Order* to enable the feature.
2. Select the **Enable Async Processing** checkbox to process purchase orders asynchronously via the message queue, improving performance and accuracy for large or complex orders.
3. Information for the **Smart Order API Key** and **Smart Order URL** fields is provided by the Oro Team upon request during the setup of the Smart Order microservice.
4. Click **Save Settings**.

#### HINT
You can also enable Smart Order [per organization](../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-ai-smart-order.md#organization-ai-smart-order-settings).
