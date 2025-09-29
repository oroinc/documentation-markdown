<a id="configuration-guide-commerce-configuration-consents"></a>

# Configure Global Consents Settings

#### HINT
Read more on this topic in [Data Protection and Consent Management](../../../../../concept-guides/consents/index.md#user-guide-consents).

If your company processes, stores and transmits personal data belonging to EU residents, you may be required to [comply with the General Data Protection Regulations (GDPR)](../../../../../concept-guides/consents/index.md#user-guide-consents). OroCommerce can assist you in observing these regulations by providing consent management mechanisms that enable you to create and manage new consents, and help your buyers view, manage and revoke consents applicable to them.

#### IMPORTANT
You can find more information on data protection regulations in the official <a href="https://www.eugdpr.org/" target="_blank">GDPR</a> portal and the <a href="https://ec.europa.eu/info/law/law-topic/data-protection_en" target="_blank">EU Commission web page</a>, or see the <a href="https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr" target="_blank">ICO's Guide to the GDPR</a> before you proceed.

Consents are disabled by default, but you can enable them globally in the system configuration. If you have more than one website, you can add corresponding consents to specific [websites](../../../websites/web-configuration/commerce/customers/website-consents.md#admin-guide-commerce-configuration-customers-consents-enable-website), once consents are enabled and created globally.

<a id="admin-guide-commerce-configuration-customers-consents-enable-globally"></a>

## Enable Consents for the Back-Office

Consents in OroCommerce can be enabled on the global configuration level only.

To enable consents:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Customers > Consents** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).
3. Next to the **Enable User Consents** field, clear the **Use Default** check box.
4. Select the **Enable User Consents** check box.
   ![Enable consents checkbox on global level](user/img/system/config_commerce/customer/enable_consents_globally.png)
5. Click **Save Settings**.

   Enabling consents adds the **Consent Management** menu under **System**.
   ![Consent management menu](user/img/system/config_commerce/customer/consent_management_menu.png)
6. Next to the **Contact Reason** field, clear the **Use Default** check box.
7. If the consent is declined in the storefront, a notification is created in the back-office as [a contact reason](../../../contact-reasons/index.md#admin-guide-contact-reasons). Select the contact reason from the list for a declined consent notification.
   ![Contact reason configuration option](user/img/system/config_commerce/customer/contact_reason_config.png)

## Enable Consents for the Storefront

Once the consents are enabled, you can add all or selected consents to the list of **Enabled User Consents** to display them in the storefront:

#### NOTE
If there are no consents in the application yet, create them under **System > Consent Management**, as described in the [Create Consents](../../../consent-management/index.md#user-guide-consents-create) topic.

To add consents to the list of enabled consents:

1. Next to the **Enabled User Consents** field, clear the **Use Default** check box.
2. Click **Add Consent** and select the required consent(s) from the list.

   Alternatively, click on the hamburger menu and select the consent(s) from its list.
3. If more than one consent is added to the **Enabled User Consents** list, you can drag and drop them to set the order in which these consents will be displayed in the storefront.

   #### NOTE
   The number of consents that can be added to the list equals the number of consents created in the application. In addition, one consent cannot be added twice.
4. To delete a consent from the list of enabled consents, click **x** next to it.
5. Click **Save Settings** on the top right.
   ![Enable consents for storefront](user/img/system/config_commerce/customer/enable_consents_for_storefront.png)

**Related Topics**

* [Data Protection and Consent Management](../../../../../concept-guides/consents/index.md#user-guide-consents)
* [View and Accept Consents in the Storefront](../../../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../../../activities/contact-requests/index.md#user-guide-activities-requests)
