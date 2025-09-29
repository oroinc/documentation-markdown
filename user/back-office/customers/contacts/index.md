<a id="user-guide-contacts"></a>

# Manage Contacts in the Back-Office

#### HINT
This section is part of the [Customer Management](../../../concept-guides/customers/index.md#concept-guide-customers) topic that provides a general understanding of accounts, contacts, customers, and customer hierarchy available in the Oro applications.

In your Oro application, you can use [contacts](../../../glossary.md#term-Contact) to save details of actual people with whom you are getting in touch during the business activities.

#### NOTE
For a quick guidance, please see a short demo on <a href="https://academy.oroinc.com/media-library/22091" target="_blank">accounts, contacts and customers</a>.

<iframe width="560" height="315" src="https://www.youtube.com/embed/3typtIVAU6Y" frameborder="0" allowfullscreen></iframe>

## Create a Contact

#### NOTE
Checkout a short video on <a href="https://academy.oroinc.com/media-library/create-edit-contact-records-orocrm#play=SmkJGGwG-r0" target="_blank">how to create and edit contact records</a>, or keep reading the step-by-step guidance.

In order to create a contact:

1. Navigate to **Customers > Contacts** in the main menu.
2. Click **Create Contact**.
3. In the **General** section, define the basic settings of the contact created.

   The following fields are mandatory and **must** be defined in the section.

   | **Name**                         | **Description**                                                                                                                                               |
   |----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Owner**                        | Define users that can manage the contact, subject to the [role settings](../../system/user-management/roles/index.md#user-guide-user-management-permissions). |
   | **First Name** and **Last Name** | Name used to refer to the contact in the UI.                                                                                                                  |

   The rest of the fields are optional. They can be used to define additional details of the contact, such as the name prefix and suffix, the middle name, free-text description, emails and phone numbers, birthday, etc.
   - With the optional field **Assigned To** you can specify a [User](../../../glossary.md#term-User) record, to which the contact will be assigned.
   - With the optional field **Reports To** you can specify another Contact record, that corresponds to a person in charge
     of the contact added (e.g. manager of the department, CEO of the company etc.).
   - You can also add a picture (upload a picture to be used for the contact in the UI) and/or
     [tags](../../../glossary.md#term-Tag) related to the contact.
   - With the **Addresses** form you can define Billing and Shipping addresses of the contact. Any amount of the addresses
     may be added.
4. The **Groups** section contains all the [contact groups](../../system/contact-groups/index.md#contact-groups) available in the system. Check the boxes to assign the contact to a group. One contact may be assigned to several groups.
5. The **Accounts** section contains all the [accounts](../accounts/index.md#user-guide-accounts) available in the system. Check the boxes to assign the contact to an account. One contact may be assigned to several accounts.

## View and Manage a Contact

All contacts available in the system are displayed on the page of all contacts (**Customers > Contacts**). Here, you can view, edit, delete, and bulk delete contacts.

![click the delete icon to delete contact](user/img/customers/contacts/action_icons.png)

[Inline editing](../../getting-started/information-management/manage-records/index.md#doc-grids-actions-records-edit-inline) can help you amend details of contacts without opening the edit contact form. For contacts, it is available from records’ grids and view pages.

If the <i class="fas fa-pencil-alt" aria-hidden="true"></i> **Edit Inline** icon appears next to a value, inline editing is available for it.

To edit contacts from the grid using inline editing, perform the same actions as for inline editing from the contact page.

![Illustrate inline editing](user/img/customers/contacts/inline_editing_contacts.gif)
<!-- .. important:: Learn how to :ref:`export <export-bulk-items>` and :ref:`import <import-contacts>` contacts in the .csv format in corresponding topics in Oro documentation library. -->

## Create an Address

For customers, customer users, and contacts in Oro application, the address book allows to enter and view account address details.

To add an address to the address book:

1. Click **Add Address** in the right corner.
   ![Click Add Address in the right corner of the selected page](user/img/customers/customers/acc_add_address.png)

   A popup form appears with the following fields to fill in:
   > | Field            | Description                                                                                                                                                                                                                            |
   > |------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   > | **Types**        | Defines the type of the address to be entered:<br/>- Billing<br/>- Shipping<br/>- Default Billing<br/>- Default Shipping<br/><br/>Note: More than one type can be selected for one address.                                            |
   > | **Primary**      | Checking the **Primary** box marks the address primary. Note that only one primary address is possible. Marking a different address primary will by default delete this mark from the address that has previously been marked Primary. |
   > | **Label**        | Identify the address by adding a label. This can help distinguish addresses if there is more than one address in the address book for one account.                                                                                     |
   > | **Name prefix**  | If applicable, add a prefix to the name, e.g., Dr., Mrs., etc.                                                                                                                                                                         |
   > | **First name**   | Enter the first name of the account representative.                                                                                                                                                                                    |
   > | **Middle name**  | Enter the middle name of the account representative.                                                                                                                                                                                   |
   > | **Last name**    | Enter the last name of the account representative.                                                                                                                                                                                     |
   > | **Name suffix**  | If applicable, add a suffix name, e.g., IV, Jr., etc.                                                                                                                                                                                  |
   > | **Organization** | Specify the organization represented by the account.                                                                                                                                                                                   |
   > | **Country\***    | This field is mandatory. Select the country from the list. Selecting a country prompts additional fields to appear (Street, City, State, Zip/postal code, Phone).<br/>Street, City, and Zip are mandatory fields.                      |

#### NOTE
Either the Organization or both the First and Last Name fields are mandatory.

1. Click **Save** once you have filled in all the fields.

   The address and the map showing the address location is displayed on the right of the address.
   ![The address and the map are shown on the right of the address](user/img/customers/customers/acc_address_saved.png)

## View an Address on the Map

It is possible to add more addresses to the same account. If you have more than one address on the Address Book page, clicking on one or the other will prompt a map to appear that corresponds to the selected address.

![Click an address to trigger the map that corresponds to the selected address](user/img/customers/customers/acc_address_correspondin_map.png)

Please be aware that a valid Google API key is required to display maps in the storefront. Please see [the back-office settings](../../system/configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google) for more information.

## Manage an Address

* **Mark address as primary** - To mark the address as primary, click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> on the right top of the address background, check the **Primary** box and click **Save**. The primary label will move to the updated address.

#### NOTE
Delete is disabled for the primary address. To delete the address marked as primary, you need to move the primary label to a different address first.

* **Edit an address** - To edit an address, click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> on the right top of the address background, update the address details and click **Save**.
* **Delete an address** - Delete an address by clicking <i class="fas fa-trash-alt" aria-hidden="true"></i> next to it.

* [Export Contacts](export-contacts.md)
* [Import Contacts](import-contacts.md)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
