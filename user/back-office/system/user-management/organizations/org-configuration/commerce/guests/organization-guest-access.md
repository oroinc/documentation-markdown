<a id="guest-access-org"></a>

<a id="sys-conf-commerce-guest-access-org"></a>

# Configure Guest Website Access Settings per Organization

#### HINT
This section is part of the [Guest Functions](../../../../../../../concept-guides/administration/guests/index.md#sys-conf-commerce-guest) topic that provides a general understanding of the guest access concept in OroCommerce.

#### NOTE
Guest access can be enabled [globally](../../../../../configuration/commerce/guests/global-guest-access.md#sys-conf-commerce-guest-access-global), per organization, and [per website](../../../../../websites/web-configuration/commerce/guests/website-guest-access.md#sys-conf-commerce-guest-access-website).

![Guest access configuration per organization](user/img/system/user_management/org_configuration/guests/GuestAccessOrg.png)

To manage guest access per organization:

1. Navigate to **System > User Management > Organizations**.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization, and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Guests > Website Access** in the menu on the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

1. Clear the **Use System** checkbox to change the system-wide settings.
2. In the Website Access section, toggle the **Enable Guest Access** checkbox to enable or disable guest users from browsing the website.

   When **Enable Guest Access** is disabled, the storefront becomes inaccessible to guest users except for the login/forgot/reset password page and any system or landing pages explicitly allowed by the administrator.

   In this case, the following additional options become available (available starting from OroCommerce version 6.1.7):
   * **Allow Guest Access to System Pages** — Select the system pages that should remain available to guest users.
   * **Allow Guest Access to Landing Pages** — Select the landing (CMS) pages that should remain available to guest users.
3. In the **Anonymous Customer Group Access** section, select a customer user group to represent **Non-authenticated Visitors (guests)** in the storefront. This group is used to define product and catalog visibility rules, as well as other features that depend on customer group settings.
4. Click **Save Settings**.

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
