<a id="admin-configuration-user-settings-org"></a>

# Configure User Settings per Organization

#### NOTE
You can configure SCIM synchronization [globally](../../../../configuration/system/general-setup/user.md#admin-configuration-user-settings) or per organization.

#### NOTE
The SCIM synchronization is only available in the Enterprise edition.

The User Settings section enables you to configure the SCIM (System for Cross-domain Identity Management) protocol in the Oro application. This setup allows you to import and synchronize users from external identity systems, such as Microsoft Entra ID, into Oro. Once imported, these users can log in to Oro via [Microsoft 365 Single Sign-On](../../../../configuration/system/integrations/microsoft-settings/microsoft-single-sign-on.md#user-guide-integrations-microsoft-single-sign-on).

To set the user provisioning settings per specific organization:

1. Navigate to **System > Configuration > User Management > Organizations** in the main menu.
2. For the necessary organization, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the <i class="fas fa-cog" aria-hidden="true"></i> **Configure** icon to start editing the configuration.
3. Select **System Configuration > General Setup > User Settings** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![User settings on organization level](user/img/system/user_management/org_configuration/general/user_org.png)
4. Under **User Provisioning**, set the following options:

* **Enable SCIM** — Enable or disable the SCIM integration on the global level.
* **Default Access to Organization Business Units** — Select the organizations and business units that will be automatically assigned to newly synchronized users.
* **Default Roles** — Select the user roles that new users will receive upon synchronization.
* **Extra fields handling** — Choose how the system should handle cases when the identity provider send extra fields. The available options are:
  > * **Return error** (default) — If selected, and the identity provider sends extra fields to Oro, the system will return an error.
  > * **Ignore extra fields** — If selected, and the identity provider sends extra fields to Oro, the system will ignore these fields.
* **Empty name values handling** — Choose how the system should handle cases when the identity provider does not send first or last name values. The available options are:
  > * **Leave as is and expect validation errors** — If selected, and the identity provider sends no first or last name to Oro, the system will return an error without generating any replacement values.
  > * **Generate based on user name** (default) — If selected, the first and last name values will be copied from the username field.
  > * **Use random string** — If selected, the first and last name values will be automatically generated as random strings.

1. Click **Save settings** to apply the changes.
2. Once enabled, you can configure a user provisioning service, following the steps described in the [Configure Okta Provisioning Service](../../../../configuration/system/general-setup/user.md#okta-provisioning-service) or the [Configure Microsoft Entra Provisioning Service](../../../../configuration/system/general-setup/user.md#microsoft-entra-provisioning-service).

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
