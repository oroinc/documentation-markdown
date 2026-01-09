<a id="sys-conf-commerce-guest-access-global"></a>

<a id="sys-conf-commerce-guest-enable-access"></a>

# Configure Global Website Access Settings

<!-- begin -->

#### HINT
This section is part of the [Guest Functions](../../../../../concept-guides/administration/guests/index.md#sys-conf-commerce-guest) topic that provides a general understanding of the guest access concept in OroCommerce.

To prevent non-registered customers from accessing the OroCommerce storefront, you can disable website access by non-authenticated visitors. This can be done globally, [per organization](../../../user-management/organizations/org-configuration/commerce/guests/organization-guest-access.md#sys-conf-commerce-guest-access-org) and [per website](../../../websites/web-configuration/commerce/guests/website-guest-access.md#sys-conf-commerce-guest-access-website):

When guest access is disabled:

* New users can register if self-registration is enabled in **Commerce > Customer > Customer Users > Registration Allowed**.
* Guest users can register if self-registration is allowed, even if the website access is closed.
* Guest users cannot access any website pages, except for the login/forgot/reset password page and any system or landing pages explicitly allowed by the administrator.
* Guest users are redirected to the login page when they try to access the homepage.

![The storefront login page displayed for guest users](user/img/concept-guides/guests/sign_in.png)

To manage guest access globally:

1. Navigate to **System > Configuration > Commerce > Guests > Website Access**.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Guest access system configuration](user/img/system/config_commerce/guests/GuestAccessSysConfig.png)
1. Clear the **Use Default** check box to manage website access settings.
2. To enable guest access to the storefront, select the **Enable Guest Access** checkbox.
3. To disable guest access globally, clear the **Enable Guest Access** checkbox.

   When the option is disabled, the following additional configuration options become available (available starting from OroCommerce version 6.1.7):
   * **Allow Guest Access to System Pages** — Select the system pages that should remain available to guest users when guest access is disabled.
   * **Allow Guest Access to Landing Pages** — Select the landing (CMS) pages that should remain available to guest users when guest access is disabled.

   Pages selected in these options remain accessible to guest users even when guest access is disabled, while all other storefront pages remain restricted.
4. Click **Save Settings**.

<!-- finish -->
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
