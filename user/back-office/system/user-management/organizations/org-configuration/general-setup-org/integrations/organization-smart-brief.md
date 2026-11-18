<a id="organization-smart-brief-settings"></a>

# Configure AI Smart Brief Settings per Organization

#### IMPORTANT
Organization-level configuration is only available in the Enterprise edition.

[AI Smart Brief](../../../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief) shows a short AI-written summary with a list of key facts at the top of the back-office customer and request for quote view pages. You can configure AI Smart Brief settings [globally](../../../../../configuration/system/integrations/smart-brief-settings.md#admin-configuration-smart-brief-settings) and per organization. The organization-level settings take precedence over the global settings for the selected organization.

The cache settings, **Cache Lifetime (seconds)** and **Refresh on Data Change**, are available only at the [global level](../../../../../configuration/system/integrations/smart-brief-settings.md#admin-configuration-smart-brief-settings).

Create an [integration with OpenAI or Vertex AI](../../../../../integrations/ai/index.md#user-guide-ai-integrations) under **System > Integrations > Manage Integrations** before you begin.

#### WARNING
OroCommerce sends business facts about customers and requests for quote to the selected AI provider. Review the [data sent to the AI provider](../../../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief-data) before you enable the feature.

To configure AI Smart Brief per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Click **System Configuration > Integrations > AI Smart Brief** in the menu to the left.
4. In the **AI Smart Brief Settings** section, clear the **Use System** checkbox next to **Enable AI Smart Brief** and select or clear the **Enable AI Smart Brief** checkbox.
5. Click **Save Settings**.

The page reloads. While the feature is disabled, the other options of the section are hidden. They appear after you enable the feature and save the settings.

1. Configure the following options. To change an option, clear the **Use System** checkbox next to it first.
   * **AI Integration** — Select the OpenAI or Vertex AI integration that writes the summaries for this organization. If no integration is selected, or if the selected integration is disabled, no summary is shown.
   * **Customer Summary** — Select this checkbox to show the summary on customer view pages.
   * **Request For Quote Summary** — Select this checkbox to show the summary on request for quote view pages.
   * **Show Regenerate Button** — Select this checkbox to show the <i class="fas fa-sync-alt" aria-hidden="true"></i> **Regenerate** button in the block. Each click sends a new request to the AI provider.
   * **Expand by Default** — Select this checkbox to open the block expanded on record pages. Users can change this option for themselves in the **Display Settings** section of [My Configuration](../../../../../../getting-started/user-menu/my-configuration.md#doc-my-user-configuration-profile).
2. Click **Save Settings**.

**Related Articles**

* [AI Smart Brief Concept Guide](../../../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief)
* [AI and Automation Concept Guide](../../../../../../../concept-guides/ai/index.md#concept-guide-ai)
* [Configure Global AI Smart Brief Settings](../../../../../configuration/system/integrations/smart-brief-settings.md#admin-configuration-smart-brief-settings)
* [Configure AI Integrations in the Back-Office](../../../../../integrations/ai/index.md#user-guide-ai-integrations)
* [OroSmartBriefBundle](../../../../../../../../bundles/extensions/SmartBriefBundle/index.md#bundle-docs-extensions-smart-brief)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
