<a id="user-guide-dashboards-widgets"></a>

# AI Smart Order

#### NOTE
This feature is available as of OroCommerce version 6.0.7.

The AI Smart Order widget in OroCommerce is an AI-powered tool designed to automate the processing of offline purchase orders, such as PDFs or email attachments. By converting these documents into digital drafts within the system, it eliminates manual data entry, thereby speeding up order processing and reducing errors.

#### NOTE
For how to add widgets to the dashboard and manage them, see the relevant topics:

* [Add Widgets to the Dashboard](index.md#user-guide-business-intelligence-widgets-add)
* [Manage Widgets on the Dashboard](index.md#user-guide-business-intelligence-widgets-manage)

Once the widget is added to the dashboard, you can upload a file of an image of a purchase order you want to add to the system by clicking once within the dotted lines of the widget and then clicking on the *Process with Smart Order* button. Once OroCommerce processes the file, you will be redirected to the page with a draft order where you can check and amend the information, if required. You will be notified if any fields require your attention and manual input.

![Illustration of the dashboard with a Smart Order widget](user/img/concept-guides/ai/ai-smart-order-flow.png)

Any draft created using the AI smart order feature includes a preview of the original uploaded document. You can turn this preview on or off using the Display/Hide Preview button. When the preview is displayed, you can zoom in and out using the controls above the image and move it horizontally by holding the Ctrl (or Command) key while dragging it.

Once you manually amend the fields that require your attention, click the green checkbox near the field to confirm your changes, and then **Save and Close** to close the order edit page. The order will now be available under **Sales > Orders** in the main menu.

![Illustration of the system making areas of the order as requiring attention](user/img/concept-guides/ai/ai-smart-order-manual-update.png)

#### NOTE
You can also automate conversion of purchase orders into draft orders by configuring your system mailbox to allow the AI Smart Order feature to scan incoming emails and extract order details automatically. For more information, please see the [Email Configuration](../../system/configuration/system/general-setup/global-email.md#admin-configuration-system-mailboxes) guide.
