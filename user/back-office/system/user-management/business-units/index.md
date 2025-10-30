<a id="user-management-bu"></a>

# Configure Business Units in the Back-Office

A [business unit](../../../../glossary.md#term-Business-Unit) represents a group of users with similar business or administrative tasks/roles.

For instance, one toy company with three toy shops can be set up as the main organization with three child business units created under it, one for each toy store. Permissions could be used to restrict access for these business units.

#### NOTE
If strict data isolation is needed between business units, it makes sense to use the [multi-organization](../organizations/index.md#user-ee-multi-org-system) approach (available for the Enterprise edition only).

To create a new business unit:

1. Navigate to **System > User Management > Business Units** in the main menu.
2. Click **Create Business Unit** on the top right.
3. In the **General** section, provide the following information:
   * **Name** — The name used to refer to the business unit on the interface. This is the only mandatory field.
   * **Parent Business Unit** — The business unit to which this business unit belongs (a level higher in the administrative hierarchy).
   * **Phone** — The phone number specified for the business unit record.
   * **Website** — The website specified for the business unit record.
   * **Email** — The email address specified for the business unit record.
   * **Fax** — The fax number specified for the business unit record.

   ![image](user/img/system/user_management/users_bu_create.png)
4. In the **Additional** section, provide a short description of the business unit record.
5. In the **Users** section, select the **Has Group** checkbox next to the required users to add them to the business unit you are creating.

   #### NOTE
   One user can belong to more than one business unit.
6. Click **Save and Close**.

Once saved, the business unit is available on the list of all business units under **System > User Management > Business Units**, where you can filter business units by name, view, edit and delete them.

![image](user/img/system/user_management/user_business_unit_grid.png)

**Related Articles**

* [Create and Manage User Groups](../groups/index.md#user-management-groups)
* [Create and Manage Organizations](../organizations/index.md#user-management-organizations)
* [Work with Multiple Organizations](../organizations/index.md#user-ee-multi-org)
* [Introduction to Role Management](../roles/index.md#user-guide-user-management-permissions-roles)
