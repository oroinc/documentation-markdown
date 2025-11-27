<a id="admin-guide-create-entities"></a>

<a id="doc-entity-actions-create"></a>

# Create Entities

This topic describes the actions that you can perform with entities in your Oro application, such as creating a new entity from scratch, editing an existing entity, deleting it, and managing unique keys.

To create a new entity:

1. Navigate to **System > Entities > Entity Management** in the main menu.
2. Click **Create Entity** on the top right of the page.
3. In the **General Information** section, provide the following information:
   - **Name** — Type the entity name. The name must be at least 5 characters long and contain only numbers and alphabetic symbols. The first symbol must be a letter. The name cannot be a <a href="http://msdn.microsoft.com/en-us/library/ms189822.aspx" target="_blank">reserved SQL word</a>.

   #### CAUTION
   The name must be unique for every custom entity created, otherwise partial update of the existing entity and failure of the schema update may occur.

   - **Icon** — Select the icon from the list that will denote all entity records.
   - **Label** — Type the label used to refer to the entity on the interface. The label must be at least 2 symbols long. Make sure that labels are unique and avoid duplicating them as this makes distinguishing between labels on the interface impossible.
   - **Plural Label** — Type the plural form of the label. It is used in titles of the menu items and grids related to the entity. The plural label must be at least 2 symbols long.
   - **Description** — Type a short but meaningful description that can help you and other users understand the purpose and the specifics of the created entity in future.
4. In the **Communication & Collaboration** section, provide the following information:
   ![Basic settings available under the communication and collaboration section](user/img/system/entity_management/create_entity_communication_collaboration.png)
   - **Share Scopes** — This subsection defines whether the records of the entity can be shared with an individual user or the whole business unit/organization (available for the Enterprise edition only).
     > #### CAUTION
     > This section is currently unavailable for custom entities.

     > - **User** — Select this checkbox if the entity records can be shared with an individual user.
     > - **Business Unit** — Select this checkbox if the entity records can be shared with the whole business unit.
     > - **Organization** — Select this checkbox if the entity records can be shared with the whole organization.
   - **Activities** — Defines which activities users can add from the page of an entity record. When you add an activity from the entity record page, the entity record appears as a context for this activity. For more information about the activities, see the [Activities](../../activities/index.md#user-guide-activities) topic.
     > - **Emails** — Select this checkbox to enable sending emails from the page of an entity record.
     > - **Calendar Events** — Select this checkbox to enable adding calendar events from the page of an entity record.
     > - **Calls** — Select this checkbox to enable logging calls from the page of an entity record.
     > - **Tasks** — Select this checkbox to enable adding tasks from the page of an entity record.
     > - **Notes** — Select this checkbox to enable adding notes to an entity record. Notes are added via the action button and are displayed in the **Activity** section on the page of an entity record.
     >   ![The add note button becomes available if the notes checkbox is enabled](user/img/system/entity_management/entity_addnotes.png)![View the list of notes in the activity section of an entity record page](user/img/system/entity_management/entity_addnotes2.png)
   - **Enable Comments** — Defines whether it is possible to leave comments on entity records. Select **Yes** from the list to enable adding comments to entity records. Select **No** from the list to restrict adding comments to entity records. The default value is **No**. Comments are displayed in the corresponding section on the page of an entity record. For more information on comments, see the topic on [Adding Comments](../../getting-started/information-management/comments.md#user-guide-activities-comments).
     ![Available actions displayed in the comments section when the enabled comments field is set to `yes`](user/img/system/entity_management/entity_addcomment.png)
5. In the **Attachments** section, specify the following:
   - **Enable Attachments** — Defines whether it is possible to attach files to the entity records. Select **Yes** from the list if you want to enable adding attachments to entity records. Select **No** from the list if you want to disable adding attachments to entity records. The default value is **No**. Attachments are added via the action button and are displayed on the page of an entity record in the corresponding section. For more information on comments, see the topic on [attachments](../../getting-started/information-management/attachments.md#user-guide-activities-attachments).
   - **Max Allowed File Size, Mb** — Type the upper limit of attachment size. Attachments whose size exceed the specified value will not be allowed.
   - **Allowed Mime Types** — Enter the list of supported MIME types. If this field is left empty, the list of MIME types defined in the [system configuration](../configuration/system/general-setup/upload.md#configuration-guide-system-configuration-general-setup-sysconfig-upload-settings) will be applied. The format of MIME types must follow these examples: application/pdf, image/\*
   - **Link Attachments To Context Entity** — If an entity record is mentioned as a context in an email, this email appears in the **Activity** section of the entity record view page. When the email contains a file as an attachment, it is possible to reattach the file to the entity record itself. You can define whether the user will reattach the file manually when required or the system will reattach it automatically.
     > - **Manual** — Select this value from the list if users are to reattach files from emails to the entity record manually.
     > - **Auto** — Select this value from the list if the system is to reattach all the attachments from emails to the entity record automatically.

     This field is available only when **Enable Attachments** is set to **Yes**. The default value is **Manual**.

   ![Basic properties available under the attachments section of an entity record page](user/img/system/entity_management/entity_create3.png)
6. In the **Other** section, specify the following:
   - **Ownership Type** — Defines who the owner of the entity can be. For more information, see the [Ownership Type](../user-management/roles/index.md#user-guide-user-management-permissions-ownership-type) topic.
     > - **None** — Select this value form the list if the entity records must have no owner (it can also be said that the owner is the system itself). This is the default value.
     > - **User** — Select this value if the entity records must have users as owners.
     > - **Business Unit** — Select this value if the entity records must have business units as owners.
     > - **Organization** — Select this value if the entity records must have organizations as owners.
   - **Auditable** — This subsection defines whether the system will log what actions are performed with the entity records and who performed them, and users with the corresponding permissions will be able to check it in the **Change History** and **Data Audit** sections of the system. Select **Yes** to enable audit of records of the entity. Select **No** to disable audit of records of the entity. The default value is **No**. For more information about the data audit, see the [Data Audit](../data-audit/index.md#user-guide-data-audit) topic.
     ![The logging audit report displayed in the change history section when the auditable option is set to `yes`](user/img/system/entity_management/entity_change_history.png)![A list of logging audit records displayed in the data audit section when the auditable option is set to `yes`](user/img/system/entity_management/data_audit.png)
   - **Enable Tags** — Defines whether it is possible to assign tags to entity records. Select **Yes** to enable adding tags to entity records. Select **No** to disable adding tags to entity records. The default value is  **No**. For more information on tag management, see the [Tags topic](../tags-management/index.md#admin-guide-tag-management).
     ![A sample of an entity record with assigned tags](user/img/system/entity_management/search_vip_1.png)
   - **Workflow Step in Grid** — Defines whether to show the column with information about the current workflow step in the grid that contains all entity records.  For more information on workflows, see the [Workflow Management topic](../workflows/index.md#doc-system-workflow-management).
     ![A sample of an entity record with enabled workflow step](user/img/system/entity_management/entity_showworkflowstep.png)
     - **Show**—Select this value from the list to show the column with the workflow step in the grid on the **All <Entity Name>** page. This is the default value.
     - **Hide**—Select this value from the list if you do not want to show the column with the workflow step in the grid.
7. Click **Save and Close** on the top right.
8. Once you have saved the new entity, you can [add](entity-fields/index.md#admin-guide-create-entity-fields) and [import fields](manage-entity-fields.md#admin-guide-import-entity-fields) to it.
9. After you have added fields to the entity, [update the schema](manage-entity-fields.md#admin-guide-update-schema).

You can view all entities under **System > Entities > Entity Management**.

#### WARNING
Schema changes are permanent and cannot be easily rolled back. We recommend that developers back up data before any database schema change if changes have to be rolled back.

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
