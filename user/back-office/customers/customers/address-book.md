<a id="user-guide-getting-started-address-book"></a>

# Create an Address

<!-- begin -->

For customers, customer users, and contacts in the Oro application, the address book allows to enter and view account/customer address details.

To add an address to the address book:

1. Click **Add Address** in the right corner.
   ![Click Add Address in the right corner of the selected page](user/img/customers/customers/acc_add_address.png)

   A popup form appears with the following fields to fill in:

   | Field            | Description                                                                                                                                                                                                                            |
   |------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Types**        | Defines the type of the address to be entered:<br/>- Billing<br/>- Shipping<br/>- Default Billing<br/>- Default Shipping<br/><br/>Note: More than one type can be selected for one address.                                            |
   | **Primary**      | Checking the **Primary** box marks the address primary. Note that only one primary address is possible. Marking a different address primary will by default delete this mark from the address that has previously been marked Primary. |
   | **Label**        | Identify the address by adding a label. This can help distinguish addresses if there is more than one address in the address book for one account.                                                                                     |
   | **Name prefix**  | If applicable, add a prefix to the name, e.g., Dr., Mrs., etc.                                                                                                                                                                         |
   | **First name**   | Enter the first name of the account representative.                                                                                                                                                                                    |
   | **Middle name**  | Enter the middle name of the account representative.                                                                                                                                                                                   |
   | **Last name**    | Enter the last name of the account representative.                                                                                                                                                                                     |
   | **Name suffix**  | If applicable, add a suffix name, e.g., IV, Jr., etc.                                                                                                                                                                                  |
   | **Organization** | Specify the organization represented by the account.                                                                                                                                                                                   |
   | **Country\***    | This field is mandatory. Select the country from the list. Selecting a country prompts additional fields to appear (Street, City, State, Zip/postal code, Phone).<br/>Street, City, and Zip are mandatory fields.                      |

#### NOTE
Either the Organization or the First and Last Name fields are mandatory.

1. Click **Save** once you have filled all the fields.

   The address and the map showing the address location is displayed on the right of the address.
   ![The address and the map are shown on the right of the address](user/img/customers/customers/acc_address_saved.png)

## View an Address on the Map

It is possible to add more addresses to the same account. If you have more than one address on the Address Book page, clicking on one or the other will prompt a map to appear that corresponds to the selected address.

![Click an address to trigger the map that corresponds to the selected address](user/img/customers/customers/acc_address_correspondin_map.png)

Please be aware that a valid Google API key is required to display maps in the storefront. Please see [the back-office settings](../../system/configuration/system/integrations/google-settings/google-integration.md#system-configuration-integrations-google) for more information.

## Manage an Address

* **Mark address as primary** - To mark the address as primary, click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> on the right top of the address background, check the **Primary** box and click **Save**. The primary label will move to the updated address.

#### NOTE
Delete is disabled for the primary address. To delete the address marked as primary, you must first move the primary label to a different address.

* **Edit an address** - To edit an address, click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> on the top right of the address background, update the address details, and click **Save**.
* **Delete an address** - Delete an address by clicking ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) next to it.

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
