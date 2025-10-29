<a id="doc-entity-actions-edit"></a>

<a id="admin-guide-create-entities"></a>

<a id="doc-entity-actions-create"></a>

# Manage Entities

In your Oro application, you can update existing entities, delete custom entities with no records, and manage unique keys to avoid duplication of existing information.

## Edit an Entity

#### IMPORTANT
The configuration of each specific entity defines which of its properties are available for editing.

To edit an entity:

1. Navigate to **System > Entities > Entity Management** in the main menu.
2. On the **All Entities** page, select the entity you want to edit and click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon.

![The All Entities page](user/img/system/entity_management/all-entities-list.png)
1. In the **General Information** section, update the following information:

* **Icon** — Select the icon from the list that will denote all entity records.
* **Label** — Type the label used to refer to the entity on the interface. The label must be at least 2 symbols long. Make sure that labels are unique and avoid duplicating them as this makes distinguishing between labels on the interface impossible.
* **Plural Label** — Type the plural form of the label. It is used in titles of the menu items and grids related to the entity. The plural label must be at least 2 symbols long.
* **Description** — Type a short but meaningful description that can help you and other users understand the purpose and the specifics of the created entity in future.

![Basic settings available under the General Information section on the edit entity page](user/img/system/entity_management/entity-general-info.png)
1. In the **Communication & Collaboration** section, update the following information:

![Basic settings available under the communication and collaboration section](user/img/system/entity_management/entity-communication-collab.png)
* **Activities** — Defines which activities users can add from the page of an entity record. When you add an activity from the entity record page, the entity record appears as a context for this activity. For more information about the activities, see the [Activities](../../activities/index.md#user-guide-activities) topic.
  > * **Calls** — Select this checkbox to enable [logging calls](../../activities/calls/index.md#doc-activities-calls) from the page of an entity record. Calls are logged via the **More actions** dropdown and are displayed in the **Activity** section on the page of an entity record.
  > * **Tasks** — Select this checkbox to enable [adding tasks](../../activities/tasks/create-tasks.md#doc-activities-tasks-actions-add-detailed) from the page of an entity record. Tasks are added via the **More actions** dropdown and are displayed in the **Activity** section on the page of an entity record.
  > * **Conversations** — Select this checkbox to enable starting conversation from the page of an entity record. To use the [conversation feature](../configuration/commerce/customer/global-interactions.md#configuration-guide-commerce-configuration-interactions), enable it in the system configuration first. Conversations can then be started via the **More actions** dropdown and are displayed in the **Activity** section on the page of an entity record.
  > * **Emails** — Select this checkbox to enable [sending emails](../../getting-started/user-menu/my-emails.md#user-guide-using-emails) from the page of an entity record.
  > * **Notes** — Select this checkbox to enable [adding notes](../../getting-started/information-management/notes.md#user-guide-add-note) to an entity record. Notes are added via the **More actions** dropdown and are displayed in the **Activity** section on the page of an entity record.
  > * **Calendar Events** — Select this checkbox to enable [adding calendar events](../../activities/calendar-events/index.md#doc-activities-events) from the page of an entity record.

  > ![The activities become available in the More actions dropdown of an entity record if they are enabled in the Communication & Collaboration section](user/img/system/entity_management/more-actions-activities.png)
* **Enable Comments** — Defines whether it is possible to leave comments on entity records. Select **Yes** from the list to enable adding comments to entity records. Select **No** from the list to restrict adding comments to entity records. The default value is **No**. Comments are displayed in the corresponding section on the page of an entity record. For more information on comments, see the topic on [Adding Comments](../../getting-started/information-management/comments.md#user-guide-activities-comments).
  > ![Available actions displayed in the comments section when the enabled comments field is set to `yes`](user/img/system/entity_management/entity_addcomment.png)

1. In the **Attachments** section, specify the following:

* **Enable Attachments** — Defines whether it is possible to attach files to the entity records. Select **Yes** from the list if you want to enable adding attachments to entity records. Select **No** from the list if you want to disable adding attachments to entity records. The default value is **No**. Attachments are added via the action button and are displayed on the page of an entity record in the corresponding section. For more information on comments, see the topic on [attachments](../../getting-started/information-management/attachments.md#user-guide-activities-attachments).
* **Max Allowed File Size, Mb** — Type the upper limit of attachment size. Attachments whose size exceed the specified value will not be allowed.
* **Allowed Mime Types** — Enter the list of supported MIME types. If this field is left empty, the list of MIME types defined in the [system configuration](../configuration/system/general-setup/upload.md#configuration-guide-system-configuration-general-setup-sysconfig-upload-settings) will be applied. The format of MIME types must follow these examples: application/pdf, image/\*
* **Link Attachments To Context Entity** — If an entity record is mentioned as a context in an email, this email appears in the **Activity** section of the entity record view page. When the email contains a file as an attachment, it is possible to reattach the file to the entity record itself. You can define whether the user will reattach the file manually when required or the system will reattach it automatically.
  > * **Manual** — Select this value from the list if users are to reattach files from emails to the entity record manually.
  > * **Auto** — Select this value from the list if the system is to reattach all the attachments from emails to the entity record automatically.

  > > This field is available only when **Enable Attachments** is set to **Yes**. The default value is **Manual**.
  > ![Basic properties available under the attachments section and how the attachments are displayed on the entity record page if the checkbox is enabled](user/img/system/entity_management/entity_addattachment.png)

1. In the **Other** section, update the following:

* **Ownership Type** — Defines who the owner of the entity can be (none, user, business unit, or organization). The ownership type is fixed and cannot be changed once created. For more information, see the [Ownership Type](../user-management/roles/index.md#user-guide-user-management-permissions-ownership-type) topic.
* **Field Level ACL** — Select this checkbox to define that permissions can be set on individual fields of this entity. For more information about field level ACLs, see the [Entity Fields](entity-fields/index.md#doc-entity-fields) topic.
* **Show Restricted** — Select this checkbox if you enabled **Field Level ACL** and are going to disable editing of some fields of the entity records but still want users to review the disabled fields on the interface. Fields disabled for modifying will appear dimmed on the interface. For more information about field level ACLs, see the [Entity Fields](entity-fields/index.md#doc-entity-fields) topic.
* **Auditable** — This subsection defines whether the system will log what actions are performed with the entity records and who performed them, and users with the corresponding permissions will be able to check it in the **Change History** and **Data Audit** sections of the system. Select **Yes** to enable audit of records of the entity. Select **No** to disable audit of records of the entity. The default value is **No**. For more information about the data audit, see the [Data Audit](../data-audit/index.md#user-guide-data-audit) topic.

![The logging audit report displayed in the change history section when the auditable option is set to `yes`](user/img/system/entity_management/entity_change_history.png)![A list of logging audit records displayed in the data audit section when the auditable option is set to `yes`](user/img/system/entity_management/data_audit.png)
* **Enable Tags** — Defines whether it is possible to assign tags to entity records. Select **Yes** to enable adding tags to entity records. Select **No** to disable adding tags to entity records. The default value is  **No**. For more information on tag management, see the [Tags topic](../tags-management/index.md#admin-guide-tag-management).

![A sample of an entity record with assigned tags](user/img/system/entity_management/entity_addtags.png)
* **Workflow Step in Grid** — Defines whether to show the column with information about the current workflow step in the grid that contains all entity records. For more information on workflows, see the [Workflow Management topic](../workflows/index.md#doc-system-workflow-management).
  > * **Show** — Select this value from the list to show the column with the workflow step in the grid on the **All <Entity Name>** page. This is the default value.
  > * **Hide** — Select this value from the list if you do not want to show the column with the workflow step in the grid.

![A sample of an entity record with enabled workflow step](user/img/system/entity_management/entity_showworkflowstep.png)
1. Click **Save and Close** on the top right.
2. Once you saved the entity, you must [update the schema](manage-entity-fields.md#admin-guide-update-schema) to apply the changes.

#### WARNING
Schema changes are permanent and cannot be easily rolled back. We recommend that developers back up data before any database schema change if changes have to be rolled back.

![The Update schema button on the entity record page](user/img/system/entity_management/update-schema.png)
1. You can also [add](entity-fields/index.md#admin-guide-create-entity-fields) and [import fields](manage-entity-fields.md#admin-guide-import-entity-fields) to the entity.
2. After you have added fields to the entity, [update the schema](manage-entity-fields.md#admin-guide-update-schema) again to apply the changes.

#### WARNING
Schema changes are permanent and cannot be easily rolled back. We recommend that developers back up data before any database schema change if changes have to be rolled back.

You can view all entities under **System > Entities > Entity Management**.

<a id="admin-guide-work-with-entities-unique-keys"></a>

## Manage Unique Keys

Unique keys are a set of fields by which the system matches new information with an existing entity record to determine whether this record is distinct or not. Use unique keys to avoid duplication of existing information.

For example, by default you can create two contacts with the same information:

*Jane Roe, born 1985-01-15, sales@example.com*

The system assigns them different IDs and treats them as different records, but they look the same on the interface and actually represent the same person.

Now imagine that before adding contacts you have defined two sets of unique keys:

* *First Name+Last Name+Birthday*
* *First Name+Last Name+Email*

You create a contact:

*Jane Roe, born 1985-01-15, sales@example.com*

And your colleague Roger tries to add Jane as a contact too:

*Jane Roe, sales@example.com*

The system checks:

- The first names and the last names are the same, but the birthday is different (not specified in the second case), maybe these are different contacts.
- The first names and the last names are the same, but the email is the same too, so it must be the same contact.

As a result, the system informs Roger that this contact already exists in the system.

To manage unique keys:

1. Navigate to **System > Entities > Entity Management** in the main menu.
2. In the grid on the **All Entities** page, click the required entity.
3. Click **Manage Unique Keys** in the upper-right corner of the page.
4. On the **Unique Keys** page, click **+Add**.
5. Specify the required information:
   * **Name** — The set name on the interface. It is used just for reference.
   * **Key** — The fields that will be included in this set. Hold the CTRL key to select several fields.
6. If you need to add another set, repeat steps 4–5.
   ![Specifying a name and a key in the unique keys section](user/img/system/entity_management/entity_manageuniquekeys.png)
7. If you need to delete a set, click the **x** icon next to the set name.
8. Click **Save**.

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
