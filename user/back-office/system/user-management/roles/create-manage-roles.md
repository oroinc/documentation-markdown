<a id="user-guide-user-management-permissions-roles-interface"></a>

<a id="user-guide-user-management-permissions-roles-actions"></a>

# Configure User Roles in the Back-Office

You can create new roles and apply permissions to fit specifically your business processes, clone and modify the existing roles.

## Create a Role

To create a new role in:

1. Navigate to **System > User Management > Roles** in the main menu.
2. Click **Create Role** on the top right.
3. In the **General** section, provide the role name.
   ![image](user/img/system/user_management/create_new_role_from_scratch.png)
4. In the **Additional** section, specify the following:
   * **Description** — Use the built-in text editor to format the provided description.
   * **Organization** — Select the organization that the user role belongs to.

     #### NOTE
     If you want this role to be applicable for all organizations defined in the system, do not specify any organization. In this case, the field value becomes **System-wide**. If there is only one organization defined in the system or you do not have global access rights, there is no option for selecting an organization.
5. In the **Entities** section, you can set three types of permissions - entity-level, field-level and system capabilities:
   * To specify access levels for entity-level permissions, click on the arrow icon next to the required permission (e.g. create or assign), and select the access level from the list. By default, access levels for each permission are set to **None**.
     ![image](user/img/system/user_management/single_entity_level_permissions.png)

     To set the same access level for all actions on entity, select the required access level from the ellipsis menu at the end of the entity row.
     ![image](user/img/system/user_management/entity_level_permissions.png)
   * To specify access levels for [field-level permissions](field-level-acl.md#user-guide-user-management-permissions-roles-field-level-acl), click **+** to the left of the entity name. Click on the arrow icon next to the required permission, and select the access level from the list. Read more on how to enable field-level permissions in the [Apply Permissions to Entity Fields](field-level-acl.md#user-guide-user-management-permissions-roles-apply-field-level-acl) topic.
   * To set system capabilities, enable or disable the checkbox next to the required options.
     ![image](user/img/system/user_management/cloned_role_system_capabilities.png)
6. In the **Workflows** section, specify access levels for workflows and workflow transitions. There are two permissions for workflows, **view** and **perform transitions**. By default, all workflow access levels are set to **None**. Choose the workflow or the transition to which you want to assign different permissions, click on the action name and select the required access level from the list.

   #### TIP
   If you do not see individual transitions of the workflow, click the **+** **Expand** icon in front of the workflow name to expand the list of transitions.

   ![image](user/img/system/user_management/create_role_workflow_permissions.png)
7. In the **Users** section, select checkboxes in front of the users to whom you want to assign this role.
8. Click **Save**.

<a id="user-guide-user-management-permissions-roles-clone"></a>

## Clone a Role

You can create a role by cloning the existing one:

1. Navigate to **System > User Management > Roles** in the main menu.
2. On the page of **All Roles**, click the ellipsis menu at end of the corresponding row of the selected role, and then click the <i class="far fa-copy" aria-hidden="true"></i> **Clone** icon.
   ![image](user/img/system/user_management/clone_role_from_grid.png)

   Alternatively, you can clone the role from the page of the selected role by clicking <i class="far fa-copy" aria-hidden="true"></i> **Clone** on the top right.
   ![image](user/img/system/user_management/clone_role_from_role_page.png)
3. The page that opens has all of the settings as the original role. Modify the settings as required.
4. In the **General** section, update the role name.
5. In the **Additional** section, provide the following information:
   * **Description** — Use the built-in text editor to format the provided description.
   * **Organization** — Select the organization that the user role belongs to.

     #### NOTE
     If you want this role to be applicable for all organizations defined in the system, do not specify any organization. In this case the field value becomes **System-wide**. If there is only one organization defined in the system or you do not have global access rights, there is no option for selecting an organization.
6. In the **Entities** section, you can set 3 types of permissions, entity-level, field-level and system capabilities:
   * To specify access levels for entity-level permissions, click on the arrow icon next to the required permission, and select the access level from the list.
     ![image](user/img/system/user_management/single_entity_level_permissions.png)

     To set the same access level for all actions on entity, select the required access level from the ellipsis menu at the end of the entity row.
     ![image](user/img/system/user_management/entity_level_permissions.png)
   * To specify access levels for [field-level permissions](field-level-acl.md#user-guide-user-management-permissions-roles-field-level-acl), click **+** to the left of the entity name. Click on the arrow icon next to the required permission, and select the access level from the list. Read more on how to enable field-level permissions in the [Apply Permissions to Entity Fields](field-level-acl.md#user-guide-user-management-permissions-roles-apply-field-level-acl) topic.
   * To set system capabilities, enable or disable the checkbox next to the required options.
     ![image](user/img/system/user_management/cloned_role_system_capabilities.png)
7. In the **Workflows** section, specify access levels for workflows and workflow transitions. There are two permissions for workflows, **view** and **perform transitions**. Choose the workflow or the transition to which you want to assign different permissions, click on the action name, and select the required access level from the list.

   #### TIP
   If you do not see individual transitions of the workflow, click the **+** **Expand** icon in front of the workflow name to expand the list of transitions.

   ![image](user/img/system/user_management/create_role_workflow_permissions.png)
8. In the **Users** section, select checkboxes in front of the users to whom you want to assign this role.
9. Click **Save**.

<a id="user-guide-user-management-permissions-roles-edit"></a>

## Edit a Role

To edit an existing role:

1. Navigate to **System > User Management > Roles** in the main menu.
2. On the page of **All Roles**, click the ellipsis menu at end of the corresponding row of the selected role, and then click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon.
   ![image](user/img/system/user_management/edit_role.png)

   Alternatively, you can edit the role from the page of the selected role by clicking <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** on the top right.
   ![image](user/img/system/user_management/edit_role_from_role_page.png)
3. On the page that opens, update the information as necessary.

<a id="user-guide-user-management-permissions-roles-delete"></a>

## Delete a Role

You can delete roles if they are not assigned to any user, and if you are granted permissions to delete roles.

To delete an existing role:

1. Navigate to **System > User Management > Roles** in the main menu.
2. On the page of **All Roles**, click the ellipsis menu at end of the corresponding row of the selected role, and then click the <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** icon.
   ![image](user/img/system/user_management/delete_role.png)

   Alternatively, you can edit the role from the page of the selected role by clicking <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** on the top right.
   ![image](user/img/system/user_management/delete_role_from_page.png)

**Related Articles**

* [Introduction to Role Management](index.md#user-guide-user-management-permissions-roles)
* [Field Level Permissions](field-level-acl.md#user-guide-user-management-permissions-roles-field-level-acl)
* [End-to-end Access Configuration in Context](access-in-context.md#user-guide-user-management-permissions-roles-examples)
* [Entity and System Capabilities](admin-capabilities.md#admin-capabilities)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
