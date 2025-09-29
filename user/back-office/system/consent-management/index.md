<a id="system-consent-management"></a>

# Configure Consent Management in the Back-Office

#### HINT
Read more on this topic in the [Consent Management Concept Guide](../../../concept-guides/consents/index.md#user-guide-consents).

<a id="user-guide-consents-create"></a>

## Create Consents

<!-- begin_create_consents -->

To create a [consent](../../../glossary.md#term-Consent) in OroCommerce:

1. Navigate to **System > Consent Management** in the main menu.
2. Click **Create Consent** on the top right.
   ![Create a new consent](user/img/system/consents/create_new_consent.png)
3. Provide the following information:
   * **Owner** — The owner is pre-populated with the user creating the consent but this value can be changed to another user of the system by clicking <i class="fa fa-bars fa-lg" aria-hidden="true"></i> and selecting a user from the list.
   * **Name** — The name of the consent displayed in the back-office and storefront. Use the folder icon next to the option to provide a localized name for the consent.
   * **Type** — Define whether the user can proceed without giving their consent. The mandatory consents must be accepted by customer users in the storefront to be able to register, proceed to the checkout and create an RFQ.
   * **Declined Consent Notification** — When the check box is enabled, a notification is created in the back-office as a [contact request](../../activities/contact-requests/index.md#user-guide-activities-requests) if a consent is declined by a customer user in the storefront.
   * **Web Catalog** — Select the web catalog where you intend to use this consent.
   * **Content Node** — Content nodes are added to web catalogs as landing pages, and linked as content variants to the catalog nodes. The selected web сatalog node can be configured to display different landing pages (content variants) in different languages. To link the consent to the required node, click on the required node in the tree to select it.

     #### NOTE
     It is recommended to have the required web catalog and the node created prior to creating a new consent. Read more on catalogs in the [Web Catalogs](../../marketing/web-catalogs/index.md#user-guide-web-catalog) topic.

     ![Link the consent to a web catalog node](user/img/system/consents/link_consent_to_node.png)
4. Click **Save and Close**.

#### IMPORTANT
Keep in mind that for the consents to be displayed in the storefront, you need to [add them to the list of enabled consents](../configuration/commerce/customer/global-consents.md#admin-guide-commerce-configuration-customers-consents-enable-globally) in the system configuration.

#### IMPORTANT
Be aware that if a consent is accepted by at least one person in the OroCommerce storefront, it becomes uneditable and unremovable. The associated landing page becomes uneditable and unremovable as well.

#### IMPORTANT
You can view all consents accepted by your customer users in the **Consents** section of their pages under **Customers > Customer Users**.

![Consents section under a customer user record](user/img/system/consents/consents_section_customer_user_page.png)

**Related Topics**

* [Data Protection in the OroCommerce Storefront](../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Configure Consents](../configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents)
* [Declined Consents as Contact Requests](../../activities/contact-requests/index.md#user-guide-activities-requests)
* [Add a Consent Landing Page to a Web Catalog](../../../concept-guides/consents/add-consent.md#user-guide-consents-add)
* [View and Accept Consents in the Storefront](../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../activities/contact-requests/index.md#user-guide-activities-requests)
* [Build Reports with Accepted Consents](../../../concept-guides/consents/accepted-consents-report.md#user-guide-reports-accepted-consents)
* [Add a Cookie Banner to the Website](../../../../bundles/commerce/CookieConsentBundle/index.md#bundle-docs-commerce-cookie-consent-bundle)
* [Cookie Consent Banner](../../../storefront/cookie-consent-banner/index.md#frontstore-guide-cookie-banner)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
