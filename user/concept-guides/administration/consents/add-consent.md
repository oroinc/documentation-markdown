<a id="user-guide-consents-add"></a>

# Add a Consent Landing Page to a Web Catalog

#### NOTE
To add the consents to a web catalog, make sure that consents are [enabled in the application](../../../back-office/system/configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents).

To be able to display the text of the consent to customers in the storefront, you need to create a consent landing page with the corresponding description and add it as a content variant for a specific node in a web catalog.

#### IMPORTANT
Please be aware that if your consent does not require any descriptive text, or if your consent is optional, you do not have to add it to the web catalog node as a landing page. However, if you need to [comply with the GDPR](index.md#user-guide-consents), make sure that the mandatory consent has detailed description of the terms that the buyer should agree to, in which case you do need to add this consent as a landing page to the selected web catalog node.

To add a consent landing page to a web catalog content node:

1. Navigate to **Marketing > Web Catalogs** in the main menu.
2. For the necessary catalog, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary catalog, and click <i class="fa fa-sitemap fa-lg" aria-hidden="true"></i> to start editing the catalog content tree.
3. Click on the required root content node where you want the consent to be displayed.

   #### NOTE
   If you do not want the consent to be displayed in the storefront menu, add it to the 5th menu level to hide it from the storefront, or apply appropriate [restrictions](../../../back-office/marketing/web-catalogs/edit-content-tree/visibility.md#user-guide-marketing-web-catalog-content-visibility).

> <!-- since by default only the first 4 levels are visible in the storefront -->
1. In the **Content Variants** section, click **Add Landing Page** in the Content Variants list.
   > ![Add a landing page with a consent as a content variant to a web catalog](user/img/system/consents/add_landing_page_with_consent.png)
2. Select a landing page with the consent description from the list, if such landing page has been created previously under **Marketing > Landing Pages**.

   To create a new landing page from within the web catalog, click **+** next to the hamburger menu in the Landing Page field.
   > ![Create a new landing page from the web catalog page](user/img/system/consents/add_landing_page_from_web_catalog_page.png)
3. In the dialog that opens, provide the following key details:
   * **Titles** — Provide the name for the consent.
   * **Content** — Provide the consent description. The text that you enter will be displayed to customers in the storefront.

     #### NOTE
     To localize the consents, you need to create separate landing pages for each target language and add all related landing pages to the content node. Set the proper restrictions to limit the consent visibility to a certain localization when it is selected in the storefront. See the [Localize Consents](localize-consents.md#user-guide-consents-localizing-consents) guide for more details on how to translate consents into different languages.

   ![Add landing pages with localized consents to a content node](user/img/system/consents/add_landing_pages_to_consents.png)

   #### NOTE
   You can read more on creating and managing landing pages in the corresponding [Landing Pages](../../../back-office/marketing/landing-pages/index.md#user-guide-landing-pages) topic.
4. Click **Save** at the bottom of the dialog to save consent details.

   The consent is now added to the Landing Page content variant field.

   #### IMPORTANT
   Be aware that web catalog restrictions can affect the visibility of the consent in the storefront. Make sure that the visibility restriction are configured properly. Read more on restrictions in the [Set Up Content Variant Visibility topic](../../../back-office/marketing/web-catalogs/edit-content-tree/visibility.md#user-guide-marketing-web-catalog-content-visibility).
5. Click **Save** on the top right to save the content node.

Once the landing page with the consent description is added to a web catalog node, you can [create a new consent](../../../back-office/system/consent-management/index.md#user-guide-consents-create) under **System > Consent Management**, and link it to the required web catalog node.

#### IMPORTANT
Keep in mind that for the consents to be displayed in the storefront, you need to [add them to the list of enabled consents](../../../back-office/system/configuration/commerce/customer/global-consents.md#admin-guide-commerce-configuration-customers-consents-enable-globally) in the system configuration.

#### IMPORTANT
You can view all consents accepted by your customer users in the **Consents** section of their pages under **Customers > Customer Users**.

![View the Consents section of a customer user](user/img/system/consents/consents_section_customer_user_page.png)

#### IMPORTANT
Keep in mind that once a consent is accepted by at least one person in the OroCommerce storefront, it becomes uneditable and unremovable as well as the associated landing page.

**Related Topics**

* [Data Protection in the OroCommerce Storefront](../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Configure Consents](../../../back-office/system/configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents)
* [Declined Consents as Contact Requests](../../../back-office/activities/contact-requests/index.md#user-guide-activities-requests)
* [Create Consents](../../../back-office/system/consent-management/index.md#user-guide-consents-create)
* [View and Accept Consents in the Storefront](../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../../back-office/activities/contact-requests/index.md#user-guide-activities-requests)
* [Build Reports with Accepted Consents](../../../back-office/reports-segments/reports/index.md#user-guide-reports)
* [Add a Cookie Banner to the Website](../../../../bundles/commerce/CookieConsentBundle/index.md#bundle-docs-commerce-cookie-consent-bundle)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
