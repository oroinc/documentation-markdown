<a id="admin-configuration-integration-flow-designer-settings"></a>

# Configure Global Integration Flow Designer Settings

#### NOTE
This feature is available in the OroCommerce Enterprise Edition.

Integration Flow Designer embeds Activepieces, a third-party automation platform, in the OroCommerce back-office. Integration Flow Designer is disabled by default. Enable it in the system configuration to build and manage [integration flows](../../../integrations/activepieces-integration.md#user-guide-integrations-activepieces).

You can configure the settings globally, as described in this topic, and [per organization](../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-integration-flow-designer.md#organization-integration-flow-designer-settings).

## Enable Integration Flow Designer

To enable Integration Flow Designer globally:

1. Navigate to **System > Configuration** in the main menu.
2. In the menu to the left, click **System Configuration > Integrations > Integration Flow Designer**.
3. In the **Integration Flow Designer Settings** section, clear the **Use Default** checkbox next to **Enable Integration Flow Designer**.
4. Select the **Enable Integration Flow Designer** checkbox.
5. Click **Save settings**.

![Integration Flow Designer settings in the global system configuration](user/img/system/integrations/activepieces/integration-flow-designer-global.png)

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

## Settings

The following settings are available:

* **Enable Integration Flow Designer** — Select the checkbox to enable the feature.
* **Activepieces User ID (System Flows)** — Contains the ID of the Activepieces user that owns the [system flows](../../../integrations/activepieces-integration.md#user-guide-integrations-activepieces-system-flows). The application fills in this value automatically when the setup command runs. The setup command creates the user and a connection from this user to OroCommerce. Do not change the value manually.
* **Enable Connection Autocreation For Users** — Select the checkbox to let the application create the connection from Activepieces to OroCommerce for each user automatically. For more information, see [Connection Autocreation for Users]().

## Connection Autocreation for Users

Users create their own [user flows](../../../../getting-started/user-menu/my-integrations.md#user-guide-my-integrations) in **My Integrations**. To work with OroCommerce data, each user needs an Activepieces user and a connection from Activepieces to OroCommerce.

The application creates an Activepieces user for each user automatically the first time they open **My Integrations**. This does not depend on the **Enable Connection Autocreation For Users** setting.

When the setting is enabled, the application also creates the connection from Activepieces to OroCommerce at that time. The application does the following:

1. Creates an [OAuth application](../../../user-management/oauth-app.md#oauth-applications) in OroCommerce on behalf of the user.
2. Uses the credentials of the OAuth application to create a connection from Activepieces to OroCommerce.

As a result, the flows of the user run on behalf of this user and with the permissions of this user. A flow cannot access any data that the user is not permitted to access.

To review the OAuth applications that the application creates, navigate to **System > User Management > OAuth Applications** in the main menu.

**Related Articles**

* [Integration with Activepieces](../../../integrations/activepieces-integration.md#user-guide-integrations-activepieces)
* [Integration Flows Concept Guide](../../../../../concept-guides/administration/integration-flows/index.md#concept-guide-integration-flows)
* [My Integrations](../../../../getting-started/user-menu/my-integrations.md#user-guide-my-integrations)
* [Configure Integration Flow Designer Settings per Organization](../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-integration-flow-designer.md#organization-integration-flow-designer-settings)
* [Configure OAuth Applications for Users](../../../user-management/oauth-app.md#oauth-applications)
* [Webhooks](../../../integrations/webhooks.md#back-office-integrations-webhooks)
* [Edit a Role](../../../user-management/roles/create-manage-roles.md#user-guide-user-management-permissions-roles-edit)
