<a id="user-guide-customers-customer-users-settings"></a>

# Configure Customer User Settings per Customer

You can configure JIT provisioning of customer users per customer or customer user invitations [globally](../../../../../system/configuration/commerce/customer/global-customer-users.md#sys-config-configuration-commerce-customers-customer-users) and per [organization](../../../../../system/user-management/organizations/org-configuration/commerce/customers/organization-customer-users.md#system-user-mngm-organization-configuration-commerce-customers-customer-users), [website](../../../../../system/websites/web-configuration/commerce/customers/website-customer-users.md#system-website-configuration-commerce-customers-customer-users), [customer group](../../../../customer-groups/customer-group-configuration/commerce/customer/index.md#user-guide-customer-groups-customer-users-settings), and customer. The customer-level setting overrides the settings configured at the higher levels.

To configure customer user settings per customer:

1. Navigate to **Customers > Customers** in the main menu.
2. For the necessary customer, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.
3. Select **Commerce > Customer > Customer Users** in the menu to the left.

![Customer user settings configuration](user/img/customers/customers/configuration/customer-users-configuration.png)

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../system/configuration/quick-search.md#user-guide-system-configuration-quick-search).

1. In the **Customer Users Registration** section, configure the following options:

#### NOTE
JIT provisioning of customer users is available as of OroCommerce version 7.0.3.

* **Enable Just-In-Time (JIT) provisioning** — Enable the feature for the customer. The feature automatically approves registration and single sign-on (SSO) requests from users whose email domains match the approved domains. The system assigns the default roles to these users and does not require a manual invitation. When you enable the feature, the **Approved Domains** and **Default Roles** options become available. The setting is available only when JIT provisioning is enabled in the [system configuration](../../../../../system/configuration/commerce/customer/global-customer-users.md#sys-config-configuration-commerce-customers-customer-users).
* **Approved Domains** — Specify the email domains whose customer users the system registers automatically. Registration and single sign-on (SSO) requests from these domains are approved without manual review. Requests from all other domains are blocked.
* **Default Roles** — Select the customer user roles that the system assigns to every newly provisioned customer user.

1. In the **Customer User Invitations** section, clear the **Use Customer Group** checkbox and configure the following option:

* **Enable Customer User Invitations** — Enables/disables [customer user invitations](../../../../customer-users/invitations.md#user-guide-customers-customer-user-invitations) for the customer in the back-office and the storefront. When invitations are disabled, the invitation pages and actions are hidden. Enabled by default.

1. Click **Save Settings**.

**Related Topics**

* [Manage Customer User Invitations in the Back-Office](../../../../customer-users/invitations.md#user-guide-customers-customer-user-invitations)
* [Enable JIT provisioning globally in the Back-Office](../../../../../system/configuration/commerce/customer/global-customer-users.md#sys-config-configuration-commerce-customers-customer-users)
* [Invite a User in the Storefront](../../../../../../storefront/register/accept-invitation.md#frontstore-guide-users-roles-invite-user)

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
