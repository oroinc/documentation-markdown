<a id="admin-guide-contact-reasons"></a>

# Configure Contact Reasons in the Back-Office

Contact Reasons are used to help categorize the [contact requests](../../activities/contact-requests/index.md#user-guide-activities-requests) submitted by customers through any channel (either via the [embedded](../integrations/embedded-forms/index.md#admin-embedded-forms) *Contact Us* form in the storefront, or by phone and email). You can create a list of contact reasons based on the most frequently asked questions or common issues. These reasons are displayed both in the storefront and in the back-office, enabling customers and sales representatives to select the appropriate topic for contact requests.

To create a contact reason:

1. Navigate to **System > Contact Reasons** in the main menu.
2. The list of available reasons is displayed.
   ![The list of available reasons](user/img/system/contact_reasons/all_contact_reasons.png)
3. Click **Create Contact Reason** on the top right.
4. Give the reason a meaningful name.
   ![A contact reason creation page](user/img/system/contact_reasons/create_contact_reason.png)
5. Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. If [localization](../user-management/organizations/org-configuration/general-setup-org/organization-localization.md#config-guide-localization-organization-localization) is enabled in the system configuration, the corresponding translation of the contact reason is displayed in the storefront. Click the same icon again to return to the single-language view.
6. Click **Save and Close**.
7. Now you can edit the existing contact reasons or delete the unnecessary ones if necessary by clicking the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> or <i class="fas fa-trash-alt" aria-hidden="true"></i> icons respectively at the end of the selected reason’s row.

Once saved, the reason appears in the dropdown list of the corresponding section of the *Contact Us* form in the storefront.

![Select a contact reason from the dropdown list in the storefront](user/img/system/contact_reasons/select_reasons_storefront.png)

When a customer submits the form selecting a certain reason, the relevant request is created in the **Contact Request** module under the **Activities** main menu. The request contains the **Contact Reason** field that helps you identify a possible issue the customer is concerned about.

![Select a contact reason from the dropdown list in the storefront](user/img/system/contact_reasons/contact_request_page.png)

You can also assign a contact reason to a contact request manually by selecting the appropriate category when creating or editing a contact request.

![Assign a contact reason manually when editing a contact request](user/img/system/contact_reasons/assign_contact_reason.png)

For more details, see the [How to Create a Contact Request Manually](../../activities/contact-requests/index.md#user-guide-activities-requests-create-manually) topic.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
