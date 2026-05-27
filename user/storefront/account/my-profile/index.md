<a id="frontstore-guide-profile"></a>

# Manage My Profile in the Storefront

<!-- begin -->

Once you are logged in to the OroCommerce storefront, you can access your profile by clicking on your name in the top navigation bar, and selecting **My Profile** from the dropdown.

My Profile has three sections, Account Info, Sign In & Security, and Default Addresses.

![image](user/img/storefront/profile/MyProfilePage.png)

<a id="frontstore-guide-profile-account"></a>

## Account Info

In the **Account Info** section, you can view your name, role, and company information. To edit your profile details, click ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) next to **Account Info**. In the editing mode, you can amend the following details:

* Company
* Name Prefix
* First Name
* Middle Name
* Last Name
* Name Suffix
* Birthday
* Data protection (accept or revoke mandatory or optional consents to process personal data)

![image](user/img/storefront/profile/MyProfilePageEdit.png)

#### NOTE
Please note that the ability to edit your account information depends on the permissions that correspond to your role. These are defined by the administrator.

## Sign In & Security

In the **Sign In & Security** section, you can view and update your email address and password. To make changes, click ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) next to the relevant field and save your updates.

#### NOTE
Depending on the [back-office email configuration](../../../back-office/system/configuration/commerce/customer/customer-user-login.md#customer-user-login-change-email), changing your email address may either take effect immediately after saving or require confirmation via a verification link sent to your current email address.

![image](user/img/storefront/profile/email-change.png)

<a id="frontstore-guide-profile-default-addresses"></a>

## Default Addresses

The **Default Addresses** section displays the addresses associated with the signed-in user. The primary addresses are shown by default.

For each listed address, you can perform the following actions:

* Edit ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg)
* Delete ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg)

To [manage default addresses in the address book](../address-book/index.md#frontstore-guide-company-address), click **Go to Personal Addresses** or navigate to the **Address Book** section in the menu on the left.

![image](user/img/storefront/profile/MyProfileManageAddresses.png)

#### NOTE
Depending on the storefront settings, the address book lists may appear in the compact format with a map displayed on the right. Please be aware that a valid Google API key is required to display maps in the storefront. Please see [the back-office settings](../../../back-office/system/configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google) for more information.

<a id="frontstore-guide-profile-consents"></a>

## Data Protection

#### HINT
Read more on this topic in [Data Protection and Consent Management](../../../concept-guides/administration/consents/index.md#user-guide-consents).

To comply with the [data protection regulations (such as CPPA, GDPR, etc.)](../../../concept-guides/administration/consents/index.md#user-guide-consents), explicit consent for the application to process your personal data may be required. All applicable consents are located under **My Profile** in the **Sign In & Security** section.

Consents can be mandatory and optional:

* **Mandatory consents** restrict you from proceeding to the checkout or creating RFQs, unless you accept them. Mandatory consents are marked with a red asterisk.
* **Optional consents** do not restrict you from working with the application and are usually used to retrieve permissions to send them email newsletters, inform about upcoming sales or seasonal discounts, etc.

The following key rules apply to consents in OroCommerce:

* **All consents are obtained through explicit actions**

  The checkboxes next to consents are never pre-selected and you can opt in only by explicitly clicking **Agree** under the consent.
  ![image](user/img/storefront/profile/explicit_accept_consent1.png)
* **Consents are informed**

  You can be aware of how exactly your data is going to be processed and shared, and what marketing communications you can expect once you provide your consent. Therefore, you can view all your accepted and pending consents (and their detailed description) in your profile under **My Profile > Sign In & Security** in the storefront.
  ![image](user/img/storefront/profile/accepted-consent-profile.png)
* **Consents can be revoked**

  If you are no longer happy with a consent, you can revoke it in the storefront when editing your **Account Info** in the **My Profile** section.
  ![image](user/img/storefront/profile/revoke_consent.png)

<a id="frontstore-guide-profile-consents-accept"></a>

### Accept a Consent

You can be asked to accept consents when:

* [Registering (creating and account in the OroCommerce store)](../../register/create-account.md#frontstore-guide-getting-started-overview-create-account)
* [When editing](#frontstore-guide-profile-account) your **Account Info** in the **My Profile** section
* [When requesting a quote](../rfq/index.md#frontstore-guide-rfq)
* At checkout

You can accept a [consent](#frontstore-guide-profile-consents) from the page of your profile, by clicking ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) **Edit** next to the **Account Info** section.

#### NOTE
You can view the description of the available consents in the **Account Info** by clicking on the consent links. The ![MinusCircle-SVG](_themes/sphinx_rtd_theme/static/svg-icons/minus-circle.svg) icon indicates that the consent has not been accepted, while the ![Check-SVG](_themes/sphinx_rtd_theme/static/svg-icons/check.svg) indicates that it has been read, understood and accepted.

In the **Data Protection** section, select the checkbox next to the consent that you want to accept. At this point you are prompted to read the text of the consent. Click **Accept** to agree to the terms of the consent and Click **Save** on the bottom left.

![image](user/img/storefront/profile/revoke_consent.png)![image](user/img/storefront/profile/explicit_accept_consent1.png)

<a id="frontstore-guide-profile-consents-revoke"></a>

### Revoke a Consent

You can decline the [consent](#frontstore-guide-profile-consents) that you have previously accepted, by clicking ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) **Edit** next to the **Account Info** section.

#### NOTE
You can view the description of the available consents in the **Account Info** section by clicking on the consent links. The ![MinusCircle-SVG](_themes/sphinx_rtd_theme/static/svg-icons/minus-circle.svg) icon indicates that the consent has not been accepted, while the ![Check-SVG](_themes/sphinx_rtd_theme/static/svg-icons/check.svg) indicates that it has been read, understood and accepted.

In the **Data Protection** section, clear the checkbox next to the consent that you want to revoke and click **Save** on the bottom left of the page.

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
<!-- finish -->
