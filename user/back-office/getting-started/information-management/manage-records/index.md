<a id="doc-grids-records"></a>

# Manage Records

There are a number of standard actions for managing records in Oro applications, but some are type-specific. This means that, although editing or deleting records is generally available for most records, additional actions can be applied, too. The types of these additional records depend on the type of the record itself. For example, converting a lead to an opportunity is not the action you can apply to a shopping cart, as this particular action is lead-specific. In addition, the actions you can perform to selected records also depend on your [role](../../../system/user-management/roles/index.md#user-guide-user-management-permissions-roles) in the company, and the [permissions](../../../system/user-management/roles/index.md#user-guide-user-management-permissions) defined for it.

This topic describes the typical actions you can perform on most records, such as editing, saving, deleting, and more.

<a id="user-guide-ui-components-view-pages"></a>

<a id="doc-grids-actions-records-view"></a>

## View Records

To view more details of a specific record and to work directly with the record (i.e., create a task related to a
customer, appoint a calendar event for a user, turn a cart into an order, share a contact, and so on), you need to get
to its details page (as in the example).

![View the details of a contact record](user/img/getting_started/records/view_01.png)

Here, you can see all the details of the record and its location on the map. You can use the links and
action buttons as described in this article. Information on a view page of the selected record is allocated in sections that you can easily switch between. All the sections are placed one after another, so you can also scroll down to find the required information.

You can do the following actions on the details page:

* [Edit the record](#doc-grids-actions-records-edit)
* [Delete the record](#doc-grids-actions-records-delete)
* [Share the record](#doc-grids-records-share)
* Add [attachments](../attachments.md#user-guide-activities-attachments), [notes](../notes.md#user-guide-add-note), and [comments](../comments.md#user-guide-activities-comments) to the record
* [Export](../export.md#export-records) and [import](../import.md#import-records) the record details

<a id="doc-grids-actions-records-edit"></a>

<a id="doc-grids-actions-records-edit-inline"></a>

<a id="doc-grids-actions-records-edit-editpage"></a>

## Edit Records

You can edit records in your application in three ways:

1. By using ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) [inline editing](#doc-grids-actions-records-edit-inline) in [record tables](../../navigation/record-tables.md#doc-grids).
   ![Illustration of the inline editing in record tables](user/img/getting_started/records/inline_editing_example.png)
2. By clicking  <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** in the ellipsis (or more options) menu located at the end of the row of the selected record in the [table](../../navigation/record-tables.md#doc-grids).
3. By opening the page of the selected record and clicking **Edit**.

### Edit Records Using Inline Editing

Inline editing enables you to edit record field values directly from [record tables](#user-guide-ui-components-view-pages). Inline editing is available only for a limited set of fields, and this set differs for different records and is not configurable.

To edit a record using inline-editing:

1. Point to the value you want to edit in the record table. If the <i class="fas fa-pencil-alt" aria-hidden="true"></i> **Edit Inline** icon appears next to it, you can edit this value in the table column.
2. Click the <i class="fas fa-pencil-alt" aria-hidden="true"></i> **Edit Inline** icon.

   Alternatively, double-click on the value itself.
3. Modify the value as required.

   Inline editors can be of different types. The simplest inline editor is a plain text field where you can type the required value.
   ![An example of the plain text field type of inline editors](user/img/getting_started/records/grids/inline_editing_example.png)

   If a field can take only specific values, the inline editor will show you a list of values to select from.
   ![An example of a list values editor type](user/img/getting_started/records/grids/grids_inlineeditor2.png)
4. Click the <i class="fa fa-check fa-lg" aria-hidden="true"></i> **Save Changes** icon to save a new value, or the <i class="fa fa-ban fa-lg" aria-hidden="true"></i> **Discard Changes** icon to return to the old value.

### Manage Records Using Ellipsis Menu

The Ellipsis menu (or the more options menu) is located on the page of all records and is available for each item in the table. To see the actions available for the selected record, click the ellipsis menu at the end of its row. You may be able to view, edit, delete records, or perform other record-specific actions, such as activating or deactivating a process.

![Illustration of the ellipsis menu](user/img/getting_started/records/grids/grids_editrecord.png)

<a id="doc-grids-actions-records-delete"></a>

<a id="doc-grids-actions-records-delete-single"></a>

<a id="user-guide-getting-started-mass-actions-management-console"></a>

<a id="doc-grids-actions-records-delete-multiple"></a>

## Delete Records

Some records in your Oro application can be removed from the system using bulk delete (e.g., marketing lists, contacts, email campaigns, etc).

To delete several records:

1. In the table, select the checkboxes next to the records you want to delete.
2. Click the ellipsis menu at the right end of the table header row, and the click the ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** icon.
3. In the confirmation dialog, click **Yes, Delete**.
4. Once deletion is confirmed, the records are removed.

![Delete the selected contact records](user/img/getting_started/records/grids/grids_delete_bulk.png)

<a id="doc-grids-actions-records-merge"></a>

## Merge Records

#### IMPORTANT
Currently, merging is available for accounts, contacts, and campaigns.

To merge records:

1. In the table, select the checkboxes in front of the records you want to merge.
2. Click the ellipsis menu at the right end of the table header row, and then click the <i class="fa fa-random fa-lg" aria-hidden="true"></i> **Merge** icon.

![Merge the selected contact records](user/img/getting_started/records/grids/grids_merge.png)

The process of merging is described in detail in the [Merging Accounts](../../../customers/accounts/merge.md#user-guide-accounts-merge) topic.

## Save Updated Records

To save the record, you have created or updated, click one of the options in the Save menu on the top right:

1. **Save** — Save the changes but remain on the same page. Use this option to make more changes to the record configuration.
2. **Save and Close** — Save the changes and close the page. Once saved and closed, you are redirected to the record page.
3. **Save and New** — Save the changes for the record you are creating/updating, and create/update another one straight away.

#### NOTE
To discard the changes, click **Cancel** on the top right.

## Review Record History

You can review the history of a specific record if you have the corresponding permissions. Click on the **Change History** link on the top right of the record page to open the dialog window. If the record has been modified, you will see who, how, and when updated it.

![Open the dialog window by clicking on the change history link](user/img/getting_started/records/grids/view_history.png)

<a id="doc-grids-records-share"></a>

## Share Records

#### NOTE
Sharing records is available in the Enterprise edition applications and can be enabled for users in the [back-office configuration settings](../../../system/configuration/system/general-setup/user.md#admin-configuration-user-settings-share).

Sharing records is convenient when you need assistance from other system users who might have no access to the related record. For example, suppose there is a task related to an opportunity that a person from a marketing team should perform. Still, the marketing associates have no access to the opportunity records. In that case, the sales manager can share the record with a specific user (or group of users).

To share a record, click **Share** on the top right of the record page and enter the user’s name to share the record with in the corresponding **Share with** field. You can also click the list icon to select such user(s).

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
