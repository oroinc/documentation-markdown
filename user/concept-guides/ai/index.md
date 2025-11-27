<a id="concept-guide-ai"></a>

# AI and Automation

#### NOTE
Please <a href="https://oroinc.com/contact-us/" target="_blank">contact our support team</a> to learn more about OroCommerce AI features, discuss how they can meet your business needs, and get started with implementation.

Artificial Intelligence (AI) is rapidly transforming industries, and B2B eCommerce is no exception. In today’s highly competitive market, businesses need tools that enable smarter decision-making, improve operational efficiency, and provide exceptional customer experiences. OroCommerce is at the forefront of this transformation, introducing AI-powered tools such as AI Smart Agent and AI Smart Order, tailored specifically to the complex needs of B2B eCommerce to help you enhance business operations and customer experiences.

<a id="concept-guide-ai-smart-agent"></a>

## AI Smart Agent

The Oro AI Smart Agent is an innovative virtual assistant designed to enhance and simplify the B2B buying experience on OroCommerce. Seamlessly integrated into the OroCommerce Enterprise storefront UI, this AI-powered assistant allows logged-in buyers to engage with the platform using natural spoken or written language, just as they would with a sales representative.

![Illustration of an AI Agent in the OroCommerce storefront](user/img/concept-guides/ai/agent-storefront.png)

With the Oro AI Smart Agent, buyers can efficiently complete essential e-commerce tasks without requiring extensive training or technical expertise, such as:

* **Order Management** – Create, update, and check order statuses.
* **Product Information** – Find product details, pricing, inventory levels, and compare products.
* **Shopping Lists** – Manage shopping lists, add products, and create orders from them.
* And more.

The Smart Agent also supports multi-website environments. Responses, product data, and links are always generated for the specific website a buyer is currently using.

Once integrated by the Oro team and configured via the [back-office](../../back-office/system/configuration/system/integrations/ai-agent.md#admin-configuration-ai-agent-settings), any logged-in buyer can access the Oro AI Smart Agent by clicking its icon in the storefront. The agent interface includes three sections:

* **Threads** – Saves previous inquiries for easy reference.
* **Suggestions** – Displays example questions and prompts to guide users.
* **Chat** – Enables real-time interaction through messaging.

Beyond basic inquiries, the AI Smart Agent possesses reasoning capabilities, allowing it to handle complex requests and take actions similar to a sales representative. For instance, users can compare products by asking which is more durable or frequently purchased based on their order history. This functionality reduces operational overhead by minimizing the need for phone calls and emails, enabling buyers to handle their needs directly within the platform.

![image](user/img/concept-guides/ai/ai-agent-question.png)

With its intuitive design and AI-driven efficiency, the Oro AI Smart Agent transforms B2B e-commerce interactions, making them smarter, faster, and more user-friendly.

<a id="concept-guide-ai-smart-order"></a>

## AI Smart Order

The AI Smart Order tool modernizes and enhances the purchase order process for distributors and manufacturers, addressing inefficiencies caused by traditional methods like fax or email. In B2B commerce, many buyers still rely on these outdated processes, leading to manual data entry errors and delays. AI Smart Order eliminates these challenges by automating the capture and processing of purchase orders directly within OroCommerce, improving accuracy and operational efficiency.

Using advanced recognition technology, AI Smart Order adapts to any purchase order template or format, accurately capturing key details and validating them against existing system records. This ensures product information, pricing, and inventory levels are correct before processing, minimizing errors and reducing administrative workload. Businesses can save time, lower overhead costs, and focus on scaling operations without the burden of manual order entry.

![Illustration of the dashboard with a Smart Order widget](user/img/concept-guides/ai/ai-smart-order-widget.png)

The AI Smart Order functionality is accessible through a dashboard widget and mailbox automation, making purchase order management even more efficient.

### Smart Order Widget

The Smart Order dashboard [widget](../../back-office/dashboards/widgets/ai-smart-order.md#user-guide-dashboards-widgets) provides an intuitive interface for users to manually upload purchase order files or images for processing. This feature allows businesses to digitize and convert orders received through offline channels, ensuring all critical order details are accurately extracted and recorded in OroCommerce.

![Illustration of the dashboard with a Smart Order widget](user/img/concept-guides/ai/ai-smart-order-flow.png)

### Smart Order Automation

For businesses aiming to fully [automate](../../back-office/system/configuration/system/general-setup/global-email.md#admin-configuration-system-mailboxes) purchase order processing, OroCommerce provides the AI Smart Order functionality. It can scan incoming emails with attached purchase orders in JPG, PNG, or PDF format, extract relevant data, and automatically create a draft order in the back-office. This reduces manual uploads and data entry and minimizes the risk of errors.

For more information on how to set up Smart Order automation, see [Create an Order via AI Smart Order Automation](../../back-office/sales/orders/create.md#user-guide-sales-orders-create-from-ai-smart-order).

![image](user/img/concept-guides/ai/so-illustration.png)

**Related Articles:**

* [OroCommerce AI Content Generation Widget](../content-management/wysiwyg.md#getting-started-wysiwyg-editor-field-ai)
* [Integration with AI Clients: OpenAI and Vertex AI](../../integrations/pre-built/ai/ai-generation.md#integrations-ai-generation)
* [Product recommendations with AI](../../integrations/pre-built/ai/google-retail.md#integrations-misc-google-retail-recommendations)
* [Create an Order via AI Smart Order Automation](../../back-office/sales/orders/create.md#user-guide-sales-orders-create-from-ai-smart-order)
* [AI Smart Order Widget](../../back-office/dashboards/widgets/ai-smart-order.md#user-guide-dashboards-widgets)
