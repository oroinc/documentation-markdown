<a id="user-guide-hangouts-org"></a>

<a id="organization-google-settings"></a>

# Configure Google Settings per Organization

#### WARNING
Google has retired Google Hangouts and associated services, and this integration is no longer supported.

#### NOTE
Google Hangouts are configured [globally](../../../../../configuration/system/integrations/google-settings/hangouts.md#user-guide-hangouts) and per organization,

Google Tag Manager is configured [globally](../../../../../configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google), per organization, and [website](../../../../../websites/web-configuration/general-sys-config/integrations/index.md#website-google-settings).

To configure Google Tag Manager and Hangouts settings per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Click **System Configuration > Integrations > Google Settings** in the menu to the left.
4. In the **Google Tag Manager Settings** section:
   > * Clear the **Use System** checkbox.
   > * For the **Google Tag Manager** Integration filed, select the [GTM integration](../../../../../integrations/gtm-ga4/index.md#gtm-ga-4-integration) you have configured for the application. Click **Save** to display an additional option.
   > * For **Data Collection For**, select the Google Analytics type (Universal, GA4, or both) that connects to your GTM account to enable data mapping.
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
