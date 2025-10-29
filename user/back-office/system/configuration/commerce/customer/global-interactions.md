<a id="configuration-guide-commerce-configuration-interactions"></a>

# Configure Global Interactions Settings

The Interactions settings allow you to interact with your customer users, enabling conversations between back-office users and customer users, provide the option to display the *Contact Us* form in the storefront, and manage user consents, ensuring a smooth and compliant user experience.

Interactions can be configured globally, [per organization](../../../user-management/organizations/org-configuration/commerce/customers/organization-interactions.md#sys-conf-commerce-customer-interactions-organization), and [per website](../../../websites/web-configuration/commerce/customers/website-interactions.md#system-website-configuration-commerce-customers-interactions).

To configure the interactions settings globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Customer > Interactions** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global interactions config settings](user/img/system/config_commerce/customer/interactions-settings.png)

## Enable the Conversations Feature

Conversations enable communication between back-office users and customer users.

1. Clear the **Use Default** checkbox to adjust the system settings.
2. Toggle the **Enable Conversations** checkbox to activate or deactivate the feature.
3. Click **Save Settings**.

Enabling conversations adds the [Conversations](../../../../activities/conversations/index.md#doc-activities-conversations) menu under **Activities**.

![New Conversations menu that appears under Activities once being enabled](user/img/system/config_commerce/customer/conversations_activity.png)

<a id="sys-conf-commerce-customer-contact-request-global"></a>

## Configure Global Contact Requests Settings

To enable or disable the display of the **Contact Us** form in the storefront globally:

1. Clear the **Use Default** checkbox to adjust the system settings.
2. In **Contact Requests**, toggle the **Allow Contact Requests** checkbox to enable or disable the **Contact Us** form in the storefront.
3. If the form is disabled, you can still use the [Contact Us widget](../../../../marketing/landing-pages/index.md#user-guide-landing-pages-create) in your web catalog pages.
4. Click **Save Settings**.

<a id="configuration-guide-commerce-configuration-consents"></a>

<a id="admin-guide-commerce-configuration-customers-consents-enable-globally"></a>

## Enable The Consents Feature

#### HINT
Read more on this topic in [Data Protection and Consent Management](../../../../../concept-guides/administration/consents/index.md#user-guide-consents).

If your company processes, stores and transmits personal data belonging to EU residents, you may be required to [comply with the General Data Protection Regulations (GDPR)](../../../../../concept-guides/administration/consents/index.md#user-guide-consents). OroCommerce can assist you in observing these regulations by providing consent management mechanisms that enable you to create and manage new consents, and help your buyers view, manage and revoke consents applicable to them.

#### IMPORTANT
You can find more information on data protection regulations in the official <a href="https://www.eugdpr.org/" target="_blank">GDPR</a> portal and the <a href="https://ec.europa.eu/info/law/law-topic/data-protection_en" target="_blank">EU Commission web page</a>, or see the <a href="https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr" target="_blank">ICO's Guide to the GDPR</a> before you proceed.

Consents are disabled by default, but you can enable them globally in the system configuration. If you have more than one website, you can add corresponding consents to specific [websites](../../../websites/web-configuration/commerce/customers/website-interactions.md#admin-guide-commerce-configuration-customers-consents-enable-website), once consents are enabled and created globally.

To enable consents:

1. Under **Consents**, toggle the **Enable User Consents Feature** checkbox to activate or deactivate the feature.

Enabling consents adds the **Consent Management** menu under **System**.

![Consent management menu](user/img/system/config_commerce/customer/consent_management_menu.png)
1. Under the **Contact Reason** field, specify the [a contact reason](../../../contact-reasons/index.md#admin-guide-contact-reasons) for a notification generated when a customer declines consent in the storefront. When a consent is declined, the system automatically creates a notification in the back-office, and this field allows you to categorize that notification by selecting the appropriate reason from a predefined list.
2. Under the **Enabled User Consents** field, add consents to the list of enabled consents to display them in the storefront. If there are no consents in the application yet, create them under **System > Consent Management**, as described in the [Create Consents](../../../consent-management/index.md#user-guide-consents-create) topic.
   * Clear the **Use Default** checkbox.
   * Click **Add Consent** and select the required consent(s) from the list. Alternatively, click on the hamburger menu and select the consent(s) from its list.
   * If more than one consent is added to the **Enabled User Consents** list, you can drag and drop them to set the order in which these consents will be displayed in the storefront.
   * To delete a consent from the list of enabled consents, click **x** next to it.

![Enable consents for storefront](user/img/system/config_commerce/customer/enable_consents_for_storefront.png)

#### NOTE
The number of consents that can be added to the list equals the number of consents created in the application. In addition, one consent cannot be added twice.

1. Click **Save Settings** on the top right.

**Related Topics**

* [Data Protection and Consent Management](../../../../../concept-guides/administration/consents/index.md#user-guide-consents)
* [View and Accept Consents in the Storefront](../../../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../../../activities/contact-requests/index.md#user-guide-activities-requests)
