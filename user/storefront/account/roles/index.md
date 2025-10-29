<a id="frontstore-guide-roles"></a>

# Manage Roles in the Storefront

Roles are predefined sets of permissions. In the Roles section, you can view, edit and create new roles to define the level of permissions and access to the actions and data in OroCommerce storefront for the users of a specific role.

You can access the list of storefront roles in the menu under your profile name in the top navigation bar.

![image](user/img/storefront/users_roles/Roles.png)

## Roles Grid

On the All Roles page, you will be able to see the list of roles available in the system. By default, the following roles are predefined and available for every customer:

* Administrator
* Buyer

The roles table shows the following data:

* Role
* Type (Predefined, Customizable)
* More Actions (View, Edit, Delete)

Within the table you have the following [actions buttons](../../getting-started/common-controls.md#frontstore-guide-navigation-action-buttons) available:

1. Refresh ![Refresh-SVG](_themes/sphinx_rtd_theme/static/svg-icons/refresh.svg) the view table.
2. Reset ![Reset-SVG](_themes/sphinx_rtd_theme/static/svg-icons/reset.svg) the view table to clear view table customization and return to default settings. Reset applies to all filters, records per page and sorting changes that you have made.
3. Manage ![Columns-SVG](_themes/sphinx_rtd_theme/static/svg-icons/columns.svg) table settings to define which columns to show in the table.
4. Manage [filters](../../getting-started/common-controls.md#frontstore-guide-navigation-filters) ![Settings-SVG](_themes/sphinx_rtd_theme/static/svg-icons/settings.svg).

## Role View Page

To open a specific role: click on the selected role in the view table.

To edit a specific role from its view page: click ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) **Edit Role** on the right of the page.

![image](user/img/storefront/users_roles/BuyerEditRole.png)

To delete a specific customizable role from its view page: click ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete**

#### NOTE
If the role is predefined, it cannot be deleted. Neither can it be deleted if it is assigned to a user/users. Reassign the assigned users to a different role to be able to delete it.

![image](user/img/storefront/users_roles/CustomizableRoleDelete.png)

## Create a New User Role

To create a new user role, click **+Create Customer User Role** on the top right of the page, next to the table name.

A form will emerge with the following data to provide:

* Customer
* Role Title
* Access- and permissions-related settings

![image](user/img/storefront/users_roles/CreateRoleNew.png)

The following permissions are available:

| Permission                                               | Level                                                                                     |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------|
| - View<br/>- Create<br/>- Edit<br/>- Delete<br/>- Assign | - None<br/>- User (Own)<br/>- Department Level (Same Level)<br/>- Corporate (All Levels). |

With the Customer User Role you can manage the following access- and permissions-related settings and capabilities:

| Field                   | Entities                                                                              | Capabilities (Checkboxes)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **All**                 | Address, Customer User, Customer User Address, Customer User Roles, Grid (Table) View | Account Management:<br/><br/>- Audit history for Customer User<br/>- [Quote] Enter the shipping address manually<br/>- [Quote] Use any shipping address from the customer address book.<br/>- [Quote] Use any shipping address from the customer user’s address book<br/>- [Quote] Use the default shipping address from the customer user’s address book<br/><br/>Checkout:<br/><br/>- Approve orders that exceed the allowable amount<br/>- Enter the billing address manually<br/>- Enter the shipping address manually<br/>- Use any billing address from the customer address book<br/>- Use any billing address from the customer user’s address book<br/>- Use any shipping address from the customer address book<br/>- Use any shipping address from the customer user’s address book<br/>- Use the default billing address from the customer user’s address book<br/>- Use the default shipping address from the customer user’s address book.<br/><br/>Application:<br/><br/>- Share Data View. |
| **Account Management**  | Address, Customer User, Customer User Address, Customer User Role, Grid View          | - Audit history for Customer User<br/>- [Quote] Enter the shipping address manually<br/>- [Quote] Use any shipping address from the customer address book.<br/>- [Quote] Use any shipping address from the customer user’s address book<br/>- [Quote] Use the default shipping address from the customer user’s address book                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Shopping**            | Shopping List                                                                         | —                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Quotes**              | Quote, Request For Quote                                                              | —                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Checkout**            | Checkout                                                                              | - Approve orders that exceed the allowable amount<br/>- Enter the billing address manually<br/>- Enter the shipping address manually<br/>- Use any billing address from the customer address book<br/>- Use any billing address from the customer user’s address book<br/>- Use any shipping address from the customer address book<br/>- Use any shipping address from the customer user’s address book<br/>- Use the default billing address from the customer user’s address book<br/>- Use the default shipping address from the customer user’s address book                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Orders**              | Invoice, Order                                                                        | —                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **System capabilities** | —                                                                                     | Share Data View                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

#### NOTE
Predefined roles cannot be edited directly. All the original data is copied so that you can save it as a new user role for your organization. All users will be moved from the original role to this new role after you click **Save**.

To apply a role to a specific user:

1. Scroll down to the bottom of the Edit Role page.
2. Enable the checkbox next to the selected user.
3. Click **Save**.

![image](user/img/storefront/users_roles/RolesAllUsers.png)
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
