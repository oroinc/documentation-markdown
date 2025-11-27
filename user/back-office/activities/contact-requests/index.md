<a id="user-guide-activities-requests"></a>

# Manage Contact Requests in the Back-Office

Contact requests are used to track contact with individuals who are requesting information such as product information, support, partnership information, or any other types of assistance. Oro has a standard embedded contact form out-of-the-box for you to add to your websites. Contact requests are automatically generated and added to the page of all contacts in your Oro application when your customers use this form.

Additionally, contact requests are used for consent management purposes when a customer [declines a consent](../../system/consent-management/index.md#user-guide-consents-create) in the OroCommerce storefront. When the **Declined Consent Notification** option is enabled for a specific consent, a notification is created in the back-office as a contact request to inform that the consent has been declined. Read more information on consents in the relevant [Data Protection and Consent Management](../../../concept-guides/administration/consents/index.md#user-guide-consents) topic.

See a short demo in our media library on <a href="https://academy.oroinc.com/media-library/manage-contact-requests" target="_blank">how to create and manage contact requests</a> or keep reading the guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/psQnfsFxQeg" frameborder="0" allowfullscreen></iframe>

<a id="user-guide-activities-requests-create-manually"></a>

## Create a Contact Request

If you need to register a particular request received from a customer by phone or email, you can manually create a contact request within your Oro application.

1. Navigate to **Activities > Contact Requests** in the main menu.
2. Click **Create Contact Request** on the top right.
3. Provide the following details on the page that appears:

   | **Name**                     | **Description**                                                                                                                                                                                                                                                                                                          |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **First Name**               | The first name of the person who requested support.                                                                                                                                                                                                                                                                      |
   | **Last Name**                | The last name of the person who requested support.                                                                                                                                                                                                                                                                       |
   | **Organization Name**        | The name of an organization, on behalf of which the request has been filed, if any. This field is for information and search purposes only.                                                                                                                                                                              |
   | **Preferred Contact Method** | Choose the contact method to be used on the list. The possible values are:<br/>- Both phone and email<br/>- Phone<br/>- Email<br/><br/>By default, the field is set to *Email*.                                                                                                                                          |
   | **Phone** and **Email**      | Contact details related to the request. The values are determined by the *Preferred Contact Method* and must be defined.                                                                                                                                                                                                 |
   | **Contact Reason**           | Choose a contact reason from the list to simplify request analysis. By default, the field is set to *Other*. To create a new contact reason that can be assigned to a certain contact request, refer to the [Contact Reasons](../../system/contact-reasons/index.md#admin-guide-contact-reasons) topic for more details. |
   | **Comment**                  | The text of the request.                                                                                                                                                                                                                                                                                                 |
4. Click **Save** on the top right.

#### NOTE
If you use the OroCommerce application, you can also relate a contact request to a customer user or a website, if necessary.

![Display the additional section with the options to select a customer user or a website](user/img/activities/CreateContactRequestCommerce.png)

## Create a Contact Request from a Third-Party Application

Add the code for the form to your website, as described in the [Embedded Forms guide](../../system/integrations/embedded-forms/index.md#admin-embedded-forms) topic. Every time a customer completes the form, the information is automatically synced to your Oro application.

#### NOTE
Use the *Contact Request form* type for your website. Other contact request types can be developed in the course of integration according to your specific business needs.

## View and Manage Contact Requests

The ability to view and edit contact requests depends on the specific [roles and permissions](../../system/user-management/index.md#user-guide-user-management-permissions-roles-acl) defined in the system.

All contact requests can be viewed from the page of all contact requests under **Activities > Contact Requests** in the main menu. From this page, you can view, edit, and delete contact requests.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
