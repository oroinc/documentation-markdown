<a id="user-guide-consents"></a>

# Consent Management Concept Guide

Customers want to feel that their data is safe when they shop online, so the governments have been stepping in to provide more regulation to ensure customer data privacy. As a result, regulations like the General Data Protection Regulation (GDPR) in the European Union and California Consumer Privacy Act (CCPA) in California, US have been put in place.

## Regulations in the US

The United States has no all-encompassing data protection law, instead it has a number of sector-specific data protection regulations. For example, <a href="https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business" target="_blank">CAN-SPAM</a> regulates commercial email, <a href="https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule" target="_blank">COPPA</a> covers websites and apps aimed at children, and the <a href="https://www.ftc.gov/" target="_blank">Federal Trade Commission</a> provides best practice guidance.

In the state of California since 2004, website admins and businesses have been creating Privacy Policies to comply with the California Online Privacy Protection Act (<a href="https://consumercal.org/about-cfc/cfc-education-foundation/california-online-privacy-protection-act-caloppa-3/" target="_blank">CalOPPA</a>). California’s privacy law - the California Consumer Privacy Act (<a href="https://ccpa-info.com/" target="_blank">CCPA</a>) - was passed in June 2018 and took effect on Jan 1, 2020.

**CalOPPA** applies to commercial websites that collect personal information about California residents and requires websites to display a Privacy Policy section with basic information about the website’s privacy practices, such as:

* What type of personal information is collected (e.g., name, email address, shipping address, payment details, etc.)
* What third-parties might receive the information (e.g., a payment processor, a mail carrier, etc.)
* A disclosure of whether your website honors “Do Not Track” (DNT) signals

Unlike CalOPPA, **CCPA** does not only apply to California businesses but to any business that impacts people in California. It requires businesses to help customers access the following rights:

* The right to know about the personal information a business collects about them and how it is used and shared
* The right to delete personal information collected from them (with some exceptions)
* The right to opt-out of the sale of their personal information
* The right to non-discrimination for exercising their CCPA rights

#### IMPORTANT
To learn more on data protection in the USA, please see a <a href="https://fas.org/sgp/crs/misc/R45631.pdf" target="_blank">guide to privacy laws</a>.

## Regulations in the EU

The General Data Protection Regulation (GDPR) is a law on protection of personal data that affects companies based in the European Union and organizations that have operations and customers on its territory, regardless of the company’s location. In addition to putting new obligations on the companies collecting personal data, the GDPR gives individuals more power to access the information that is held about them. This includes giving consumers the right to get their personal data erased in circumstances where it is no longer necessary for the purpose it was collected, if the consent to process data is withdrawn, or if it has been processed unlawfully.

Not complying with the GDPR can result in disciplinary actions from relevant supervisory authorities.

#### IMPORTANT
Learn more on data protection regulations in the official <a href="https://www.eugdpr.org/" target="_blank">GDPR</a> portal and the <a href="https://ec.europa.eu/info/law/law-topic/data-protection_en" target="_blank">EU Commission web page</a>, or see the <a href="https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr" target="_blank">ICO's Guide to the GDPR</a> before you proceed.

## Compliance with Other Regulations

Consent management does not only apply to data protection regulations, and you can unable consents or agreements to ensure compliance with any laws, regulation, or rules that may be emposed by your state or country.

Here are a couple of examples of when you might need to collect a consent or agreement from your customer at the checkout, or inform them about important details of the sale they are about to complete.

Under the federal law, any plumbing materials connected to the public water system that provides water for human consumption must be lead-free. Therefore, if your business sells plumbing supplies that contain lead, you must warn your buyer that such pipes, fittings, and fixtures must be used exclusively for services where water is not anticipated to be used for human consumption. You can set up a consent form to appear at the checkout to collect an informed consent and make sure that your buyers understand all the ramifications.

Another example where consents at checkout need to be put in place concerns export restrictions. Export of specific products or shipping from the US to some countries may be restricted. Under U.S. law, commerce enterprises have an obligation to “know their customer”, including the ultimate buyer if their customers re-export the products. So, for instance, if you selling a product to a buyer who you know intends to re-export the product to a country to which direct exports from the US are prohibited, you will be violating the law. An example of such product may be a processor with advanced encryption algorithm, or a different piece of technology embedded in the product controls that you cannot sell outside of the US.

Whatever state or country you run your business, OroCommerce’s consent management system, discussed below, can help you build a robust compliance system tailored to your business and legal needs.

## Data Protection Compliance in OroCommerce

To help online businesses comply with data protection regulations, OroCommerce provides a flexible mechanism for collecting and managing customer consents.

In this respect, OroCommerce webstore customers have the right to:

* Know what personal data is processed and stored in the application and how, and request this information at any moment.
* Request to modify their personal data if it is incorrect, outdated, or otherwise inaccurate.
* Reuse their personal data and export it to other systems or organizations.
* Revoke the consent to process their personal data and opt out of any email, telephone or other types of communication.

## Getting Started with Consent Management

In the OroCommerce back-office, consents are managed by security policy officers (or other company-specific roles with the corresponding consent management permissions) who enable, configure and manage them in the application. Consents can also be localized and display the information in the required language.

You can create two types of consents in OroCommerce, mandatory and optional.

**Mandatory consents** restrict buyers in the storefront from proceeding to the checkout or creating RFQs, unless they accept these consents. An example of a mandatory consent is a buyer’s agreement to comply with the company’s terms and conditions, or their explicit permission to let the application process personal data for business intelligence purposes.

**Optional consents** do not restrict buyers from working with the application and are usually used to retrieve permissions to send them email newsletters, inform about upcoming sales or seasonal discounts, etc.

Once the consent is accepted by at least one buyer in the OroCommerce storefront, it becomes uneditable and unremovable from the system, and can be used as evidence should any legal requirements arise to provide it. Moreover, in this case, administrators cannot modify the content of the consent description in any way, and can only view the available consents.

You can view all consents accepted by your customer users in the **Consents** section of their pages under **Customers > Customer Users**.

By default, consents are disabled in OroCommerce.

To enable and configure consents in OroCommerce, take the following steps:

* Enable consents in the [system configuration](../../back-office/system/configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents).
* Create a [landing page](add-consent.md#user-guide-consents-add) with the text of the consent, and add it as a content variant of a content tree node.
* Create a [new consent](../../back-office/system/consent-management/index.md#user-guide-consents-create) under **System > Consent Management**, define its properties, and link it to the content tree node.
* Add the consent to the list of enabled user consents in the [system configuration](../../back-office/system/configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents) to display consents in the storefront.

Consents can be configured on [two levels](../../back-office/system/index.md#configuration-guide-config-levels), [global](../../back-office/system/index.md#doc-system-configuration) and [website](../../back-office/system/websites/web-configuration/index.md#doc-website-configuration). However, you can add consents to the storefront on the website level only when consents are enabled globally.

Learn more on the configuration and localization of consents in OroCommerce in the following topics:

* [Configure Consents](../../back-office/system/configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents)
* [Create Consents](../../back-office/system/consent-management/index.md#user-guide-consents-create)
* [Add a Consent Landing Page to a Web Catalog](add-consent.md#user-guide-consents-add)
* [Localize Consents](localize-consents.md#user-guide-consents-localizing-consents)
* [View and Accept Consents in the Storefront](../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../back-office/activities/contact-requests/index.md#user-guide-activities-requests)
* [Cookie Consent Banner](../../storefront/cookie-consent-banner/index.md#frontstore-guide-cookie-banner)
* [Add a Cookie Banner to the Website](../../../bundles/commerce/CookieConsentBundle/index.md#bundle-docs-commerce-cookie-consent-bundle)

**Related Topics**

* [Data Protection in the OroCommerce Storefront](../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Declined Consents as Contact Requests](../../back-office/activities/contact-requests/index.md#user-guide-activities-requests)
* [Build Reports with Accepted Consents](accepted-consents-report.md#user-guide-reports-accepted-consents)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
