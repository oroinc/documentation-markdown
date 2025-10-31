<a id="system-workflows-conversations-backoffice-workflow"></a>

# Configure Backoffice Conversations Workflow in the Back-Office

#### NOTE
The conversations feature is available as of OroCommerce version 6.0.4 as a <a href="https://extensions.oroinc.com/orocommerce/extension/oro-conversations/" target="_blank">Conversations extension</a>, which you can download from the Oro Extensions Store. Next, use the composer to [install it on your application](../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

Oro offers a [conversation feature](../../../activities/conversations/index.md#doc-activities-conversations) for easy communication between back-office and storefront users. Conversations allow back-office staff to share information and communicate with other back-office users or customer users in the storefront. The Conversations Workflow is a system workflow that provides the following default statuses for the conversation feature: Active, Inactive, Closed.

![Illustration of the workflow transition on a view page of a conversation](user/img/system/workflows/conversations/activities-conversations-view.png)

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.
2. Click **Conversation Workflow** to open it.

![Conversations workflow in the Workflow grid](user/img/system/workflows/conversations/conversation-flow-grid.png)

By default, the Conversation workflow is active. On its view page, you have an option to disable the workflow by clicking **Deactivate** on the top right. As it is a system workflow, it cannot be edited or deleted.

## Steps and Transitions

The following table describes which options are available for each of the statuses of the conversation:

| Status   | Options   |
|----------|-----------|
| Active   | Close     |
| Closed   | Reopen    |
![View page of the conversation workflow showing the workflow diagram with transitions and a button to deactivate the workflow](user/img/system/workflows/conversations/conversations-wf-view-page.png)

**Related Topics**

* [Manage Conversations in the Back-Office](../../../activities/conversations/index.md#doc-activities-conversations)
* [Enable the Conversations Feature](../../configuration/commerce/customer/global-interactions.md#configuration-guide-commerce-configuration-interactions)
