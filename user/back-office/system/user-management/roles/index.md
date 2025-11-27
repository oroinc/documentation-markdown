<a id="user-guide-user-management-permissions-roles"></a>

<a id="user-guide-user-management-permissions-roles-actions-on-entity-permissions"></a>

<a id="user-guide-user-management-permissions"></a>

# Configure Roles and Permissions in the Back-Office

Roles are predefined sets of permissions. After users are assigned a specific role that is typically based on job functions, they can manage information relevant to their job role. One user can even have several roles to cover for a flexible set of functions.

You can create as many roles as required and configure permissions for them according to the needs of your company.

There are four types of role permissions in OroCommerce:

* System capabilities
* Entity-level permissions
* Field-level permissions
* Workflow permissions

For **system capabilities**, you enable or disable the options you need.

For **entity-level, field-level and workflow permissions**, you assign the following access levels:

* None
* User
* Business Unit
* Division
* Organization
* Global

The set of available access levels depends on the entity’s **ownership type** which limits the range of access levels you can set for actions on this entity.

The following section explains what permissions you can apply to roles, what access levels can be set to permissions, and how access levels depend on the owner of the selected entity.

<a id="user-guide-user-management-permissions-ownership-type"></a>

<a id="user-guide-user-management-permissions-ownership-type-access-levels"></a>

## Permissions, Access Levels and Ownership Type

You can have a **permission** to perform a number of actions to entities. The set of permissions may vary for some entities but in general they are the following:

| Permission   | Description                                                                |
|--------------|----------------------------------------------------------------------------|
| View         | A user can view the entity record details.                                 |
| Create       | A user can create a new entity record.                                     |
| Edit         | A user can edit entity records.                                            |
| Delete       | A user can delete an entity record.                                        |
| Assign       | A user can change the owner of an entity record.                           |
| Share        | A user can share an entity record with other users.                        |
| Configure    | A user can set up the system configuration for themselves and other users. |

For each of these permissions you can set an **access level**:

| Access Level   | What data a user can access?                                                                                                                                                                                                             |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| None           | Access is denied.                                                                                                                                                                                                                        |
| User           | Entity records owned by the user (providing the user has access to the organization(s) for which these records were created).                                                                                                            |
| Business Unit  | Entity records owned by the business unit(s) the user has access to or by any user that has access to the same business unit.                                                                                                            |
| Division       | Entity records:<br/><br/>* Owned by business unit(s) the user has access to or by any user that has access to the same business unit.<br/>* Owned by the whole chain of the business units subordinated to those the user has access to. |
| Organization   | All entity records within the organization the user has access to. This access level is hidden if there is only one organization.                                                                                                        |
| Global         | All entity records within the system.                                                                                                                                                                                                    |

#### NOTE
Only two access levels are always available: **None** (access is denied) and **Global** (access to all entity records) within the system.

The picture below illustrates how permissions for an entity can be configured:

![image](user/img/system/user_management/ex_permissions-on-entity.png)

The set of available access levels depends on the entity’s **ownership type**. The ownership type limits the range of access levels you can set for actions on this entity. For example, you cannot set the **User** access level if the entity ownership type is **Organization**.

The following table shows what access levels can be assigned depending on the entity’s ownership type:

| Ownership type   | Possible access levels for an entity with this ownership type   |
|------------------|-----------------------------------------------------------------|
| User             | None, User, Business Unit, Division, Organization, Global       |
| Business Unit    | None, Business Unit, Division, Organization, Global             |
| Organization     | None, Organization, Global                                      |
| None             | None, Global                                                    |

Although ownership types uses the same concepts as a label, their impact is different. For example:

* The **None** ownership type gives the widest access to entity records. It means ‘This record does not belong to any particular organization or business unit or user. Therefore, either all users can access it, or no one at all.’
* The **None** access level completely restricts access to entity records. It says ‘No one can perform this action on the entity’.

Keep in mind that as soon as the entity is created, its ownership type cannot be changed. Consequently, you cannot change the predefined ownership types of system entities (such as an account or a business unit).

**Related Articles**

* [Field Level Permissions](field-level-acl.md#user-guide-user-management-permissions-roles-field-level-acl)
* [Entity and System Capabilities](admin-capabilities.md#admin-capabilities)
* [Create and Manage Roles](create-manage-roles.md#user-guide-user-management-permissions-roles-actions)
* [End-to-end Access Configuration in Context](access-in-context.md#user-guide-user-management-permissions-roles-examples)

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
