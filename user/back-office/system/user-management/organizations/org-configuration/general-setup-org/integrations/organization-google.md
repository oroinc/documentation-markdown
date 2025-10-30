<a id="user-guide-hangouts-org"></a>

<a id="organization-google-settings"></a>

# Configure Google Settings per Organization

#### WARNING
Google has retired Google Hangouts and associated services, and this integration is no longer supported.

#### NOTE
Google Hangouts are configured [globally](../../../../../configuration/system/integrations/google-settings/hangouts.md#user-guide-hangouts) and per organization,

Google Tag Manager is configured [globally](../../../../../configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google), per organization, and [website](../../../../../websites/web-configuration/general-sys-config/integrations/website-google-settings.md#website-google-settings).

To configure Google Tag Manager and Hangouts settings per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Click **System Configuration > Integrations > Google Settings** in the menu to the left.
4. In **Google Tag Manager Settings**, clear the **Use System** checkbox and select a [Google Tag Manager Integration](../../../../../integrations/gtm/index.md#gtm-ga-4-integration) from the list to configure it for the application and enable data mapping.

   #### NOTE
   You can enable cross-domain tracking to be able to track user interactions across multiple domains using a single GA4 property. See the <a href="https://developers.google.com/tag-platform/devguides/cross-domain#when_to_implement_cross-domain_measurement" target="_blank">Implement Cross-Domain Measurement</a> article on the Google website for more information.
5. In the **Google Hangouts** section, provide the following details:
   * **Enable For Emails** — Check the box to enable Google Hangouts for emails.
   * **Enable For Phones** — Check the box to enable Google Hangouts for phones.

By default, **Enable For Emails** and **Enable For Phones** are enabled.

1. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
