<a id="mc-system-configuration"></a>

# Global Configuration Settings

Settings under the **System > Configuration** menu enable you set up your Oro application specifically to your business needs. Settings located here are [system-wide (or global)](../index.md#doc-system-configuration). Configuring these settings globally means that they are by default applied throughout all organizations, websites and users in your system. This is the base configuration level and you can customize some of its options [per organization](../user-management/organizations/org-configuration/index.md#doc-organization-configuration), [website](../websites/web-configuration/index.md#doc-website-configuration), or [user](../user-management/users/configuration/index.md#doc-my-user-configuration) later on. Selected settings are also available on [customer group](../../customers/customer-groups/customer-group-configuration/commerce/product/customer-group-product-customer-settings.md#user-guide-customer-groups-customer-settings) and [customer](../../customers/customers/customer-configuration/commerce/product/customer-product-settings.md#user-guide-customers-customer-settings) levels.

Based on the level where configuration has taken place, settings can fall back to other levels following the pattern below:

* [User settings](../user-management/users/configuration/index.md#doc-my-user-configuration) fall back to the [organization settings](../user-management/organizations/org-configuration/index.md#doc-organization-configuration).
* [Website settings](../websites/web-configuration/index.md#doc-website-configuration) fall back to the [organization settings](../user-management/organizations/org-configuration/index.md#doc-organization-configuration).
* [Organization settings](../user-management/organizations/org-configuration/index.md#doc-organization-configuration) fall back to the [system settings](system/index.md#configuration-guide-system-configuration).
* [Customer Group settings](../../customers/customer-groups/customer-group-configuration/commerce/product/customer-group-product-customer-settings.md#user-guide-customer-groups-customer-settings) fall back to the [website settings](../websites/web-configuration/index.md#doc-website-configuration).
* [Customer](../../customers/customers/customer-configuration/commerce/product/customer-product-settings.md#user-guide-customers-customer-settings) settings fall back to the [customer group settings](../../customers/customer-groups/customer-group-configuration/commerce/product/customer-group-product-customer-settings.md#user-guide-customer-groups-customer-settings).

![A fallback pattern of the configuration levels](user/img/system/configuration/ConfigLevels.png)

Be aware that:

* When **Use System** checkbox is enabled on the configuration page of the required option, system settings override website or organization. Clearing this checkbox next to the required option and changing its value means that you are configuring this particular option specifically for the selected organization.
  ![Organization configuration settings](user/img/system/configuration/system_checkbox.png)
* When **Use Organization** checkbox is enabled on the configuration page of the required option, organization settings override system. Clearing this checkbox next to the required option and changing the default value means that your are introducing changes for a specific user.
  ![User configuration settings](user/img/system/configuration/org_checkbox.png)
* When **Use Website** checkbox is enabled on the configuration page of the required option, website settings prevail. Clearing this checkbox next to the required option and changing the default value means that you are introducing changes for a specific customer group.
  ![Customer group configuration settings](user/img/system/configuration/website-check-box.png)
* When **Use Customer Group** checkbox is enabled on the configuration page of the required option, customer group settings prevail. Clearing this checkbox box next to the required option and changing the default value means you are introducing changes at customer level.
  ![Customer configuration settings](user/img/system/configuration/customer-group-checkbox.png)

#### HINT
To help you find the specific configuration option faster, use [Quick Search](quick-search.md#user-guide-system-configuration-quick-search) located in the configuration panel on the left (on all configuration levels).

![Quick search under System Configuration](user/img/system/configuration/quick_search.png)
