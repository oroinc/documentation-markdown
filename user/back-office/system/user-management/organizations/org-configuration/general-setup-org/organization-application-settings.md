<a id="admin-configuration-application-org"></a>

# Configure Application Settings per Organization

In this section, you can configure the Web API feature both for the back-office and storefront. By default, the API feature is disabled.

To change the default settings per organization:

1. Navigate to **System > User Management > Organization** in the main menu.
2. For the necessary organization, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the <i class="fas fa-cog" aria-hidden="true"></i> **Configure** icon to start editing the configuration.
3. Select **System Configuration > General Setup > Application Settings** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
4. Clear the **Use System** checkbox to change the system-wide setting.
5. In the **Web API** section, select the required options:
   * **Enable API** — enables the back-office API feature for an organization.
   * **Enable Storefront API** — enables the storefront API feature for an organization.
   * **Enable Guest Storefront API** — grants access to some storefront API resources of an organization to non-authenticated visitors (available starting from v5.1.3). This option is activated when the storefront API feature is enabled.

   #### NOTE
   The back-office API feature can be toggled on the [global](../../../../configuration/system/general-setup/application.md#admin-configuration-application) and organization levels, while the storefront API configuration is available on three levels - globally, per organization, and per [website](../../../../websites/web-configuration/general-sys-config/general/website-application-settings.md#admin-configuration-application-website).
6. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
