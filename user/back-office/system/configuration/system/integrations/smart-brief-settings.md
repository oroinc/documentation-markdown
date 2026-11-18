<!-- meta: description = Learn how to enable AI Smart Brief on customer and request for quote view pages, select the AI integration, and configure the summary cache in the OroCommerce back-office. -->

<a id="admin-configuration-smart-brief-settings"></a>

# Configure Global AI Smart Brief Settings

#### NOTE
Please <a href="https://oroinc.com/contact-us/" target="_blank">contact our support team</a> to learn more about OroCommerce Enterprise AI features, discuss how they can meet your business needs, and get started with implementation.

[AI Smart Brief](../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief) is available for OroCommerce Enterprise and shows a short summary at the top of the back-office customer and request for quote view pages. The block shows a short AI-written paragraph with a list of key facts next to it. OroCommerce computes the facts from its own data. The AI integration only turns these facts into a short paragraph.

You can configure AI Smart Brief settings globally and [per organization](../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-smart-brief.md#organization-smart-brief-settings). The cache settings are available only at the global level.

Create an [integration with OpenAI or Vertex AI](../../../integrations/ai/index.md#user-guide-ai-integrations) under **System > Integrations > Manage Integrations** before you begin.

#### WARNING
OroCommerce sends business facts about customers and requests for quote to the selected AI provider. Review the [data sent to the AI provider](../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief-data) before you enable the feature.

## Enable AI Smart Brief

To enable AI Smart Brief globally:

1. Navigate to **System > Configuration** in the main menu.
2. In the menu to the left, click **System Configuration > Integrations > AI Smart Brief**.
3. In the **AI Smart Brief Settings** section, clear the **Use Default** checkbox next to **Enable AI Smart Brief** and select the **Enable AI Smart Brief** checkbox.
4. Click **Save Settings**.

The page reloads. While the feature is disabled, the other options of the section are hidden. They appear after you enable the feature and save the settings.

![The AI Smart Brief global settings](user/img/concept-guides/ai/ai-smart-brief-settings-global.png)
1. Configure the following options. To change an option, clear the **Use Default** checkbox next to it first.

* **AI Integration** — Select the OpenAI or Vertex AI integration that writes the summaries. If no integration is selected, or if the selected integration is disabled, no summary is shown.
* **Customer Summary** — Select this checkbox to show the summary on customer view pages. This option is disabled by default.
* **Request For Quote Summary** — Select this checkbox to show the summary on request for quote view pages. This option is disabled by default.
* **Cache Lifetime (seconds)** — Enter how long a generated summary is reused before it is written again. The value must be a positive whole number. The default value is 14400 seconds (4 hours).
* **Refresh on Data Change** — Select this checkbox to write a summary again as soon as the facts it is based on change. This option is enabled by default. For details, see [Choose the Refresh Mode]().
* **Show Regenerate Button** — Select this checkbox to show the <i class="fas fa-sync-alt" aria-hidden="true"></i> **Regenerate** button in the block. The button lets users request a new summary immediately. Each click sends a new request to the AI provider. This option is disabled by default.
* **Expand by Default** — Select this checkbox to open the block expanded on record pages. When a user expands or collapses the block, it keeps that state for the record until the facts of the record change. Users can change this option for themselves in the **Display Settings** section of [My Configuration](../../../../getting-started/user-menu/my-configuration.md#doc-my-user-configuration-profile). This option is enabled by default.

1. Click **Save Settings**.

<a id="admin-configuration-smart-brief-settings-refresh-mode"></a>

## Choose the Refresh Mode

The **Refresh on Data Change** option controls how fresh the summaries are and how much work each page view costs.

* **Refresh on Data Change** is enabled — OroCommerce collects the facts on every page view. If the facts have changed since the summary was written, OroCommerce requests a new summary from the AI provider. As a result, the summary always matches the current data, but every page view runs the fact queries.
* **Refresh on Data Change** is disabled — OroCommerce reuses a cached summary without collecting the facts again. As a result, OroCommerce shows a cached summary without fact queries or an AI call, but the summary text and the facts in the block can be up to one cache lifetime old. Each user has their own cached summary in this mode because the facts depend on the user’s permissions.

In both modes, a new summary requires a call to the AI provider. A shorter cache lifetime makes summaries fresher but increases the number of AI calls and the related provider costs.

#### NOTE
When **Refresh on Data Change** is disabled, changes to user permissions take effect in the summaries only after the cached summaries expire. For more information, see [Summaries and Permissions](../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief-permissions).

**Related Articles**

* [AI Smart Brief Concept Guide](../../../../../concept-guides/ai/smart-brief.md#concept-guide-ai-smart-brief)
* [AI and Automation Concept Guide](../../../../../concept-guides/ai/index.md#concept-guide-ai)
* [Configure AI Smart Brief Settings per Organization](../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-smart-brief.md#organization-smart-brief-settings)
* [Configure AI Integrations in the Back-Office](../../../integrations/ai/index.md#user-guide-ai-integrations)
* [OroSmartBriefBundle](../../../../../../bundles/extensions/SmartBriefBundle/index.md#bundle-docs-extensions-smart-brief)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
