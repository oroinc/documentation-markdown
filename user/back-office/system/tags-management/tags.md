<a id="user-guide-system-tags-management-tags"></a>

# Configure Tags in the Back-Office

The following guide describes how you can configure [tags](../../../glossary.md#term-Tag) in your Oro application. Tags are located under **System > Tags Management** in the main menu.

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/tags-taxonomies" target="_blank">how to create tags</a> or continue reading the guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/RBY6dvZc55E" frameborder="0" allowfullscreen></iframe>

## Enable Tags for Entity

Prior to starting your work with tags, ensure that tagging is enabled for the required *entity*.

To enable tags for entities:

1. Navigate to the main menu and click **System > Entities > Entity Management**.
2. Click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> at the end of the required entity’s row to open its edit form.
3. In the **Other** section, select **Yes** in the **Enable Tags** field.
   ![Selecting Yes in the Enable Tags field](user/img/system/tags_management/enable_tags_4.png)
4. Click **Save and Close**.

   #### NOTE
   Please note that if you wish to disable tags for an entity, this will irreversibly erase all its existing tags.

## Create Tags

Tags can be created in a number of ways:

### From the Tag Page

1. Navigate to the Tag page under **System > Tags Management > Tags**.
2. Click **Create Tag** to create a new tag.
3. Define the following fields:
   * **Owner** — Limits the list of users who can manage the tag.
   * **Name** — Specify the name for your tag.
   * **Taxonomy** — Select the [taxonomy](taxonomies.md#user-guide-system-tags-management-taxonomies) to which the tag will be assigned.
4. Click **Save and Close**.

### From the Grid Page

1. Navigate to a grid page for an entity that supports tag creation. For example, open **Customers > Accounts** from the main menu. Tags will be available from the grid of that entity.
2. Click ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) edit next to the selected entity record.
3. Start typing in the tag name. If it does not yet exist in the system, (New Tag) will appear next to it in the drop down.
   ![image](user/img/system/tags_management/new-tag.png)

   Alternatively, select an existing tag from the list. You can add multiple tags.
   ![Select the required tags from the list](user/img/system/tags_management/entity_grid_inline_tag_12.png)
4. Click <i class="fa fa-check fa-lg" aria-hidden="true"></i> to save the tag(s).

### From the Details Page of an Entity

1. Navigate to a grid page for an entity that supports tag creation. For example, open **Customers > Accounts** in the main menu.
2. Click the required entity to open its details page.

1. Click ![Pencil-SVG](_themes/sphinx_rtd_theme/static/svg-icons/pencil.svg) edit in Tags.
   ![Click the edit icon in the Tags field of the selected entity record](user/img/system/tags_management/entity_view_page_14.png)
2. Specify one or more tags for the entity.
   ![Specify the tags for the entity in the field that opened](user/img/system/tags_management/entity_view_page_15.png)
3. Click <i class="fa fa-check fa-lg" aria-hidden="true"></i> to save the tags.

## Manage Tags From the Grid

Navigate to **System > Tags Management > Tags**.

Within the tags list, you can:

1. Search records by a tag: ![Search-SVG](_themes/sphinx_rtd_theme/static/svg-icons/search.svg)
2. Edit the selected tag: <i class="fa fa-edit fa-lg" aria-hidden="true"></i>
3. Delete a tag from the system:![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg)
4. Filter tags: <i class="fa fa-filter fa-lg" aria-hidden="true"></i>
5. Configure grid settings for tags: <i class="fa fa-cog fa-lg" aria-hidden="true"></i>

![The actions available for the tags in the grid](user/img/system/tags_management/tags_grid_manage_18.png)

## View Tagged Content

Clicking the selected tag will redirect you to a page where you can view all the records that have been assigned to your selected tag. This way you can search for any required tag within the system.

For instance, clicking **Gold** will redirect you to the page with a list of all records that have **Gold** as a tag.

![Point at the Gold tag](user/img/system/tags_management/tag_link_20.png)

The number in brackets indicates the how many records within the group are assigned to the selected tag.

![image](user/img/system/tags_management/content_view_page_21.png)

## Tags in Reports

It is possible to filter your reports by tags. For instance, we can create a report that will show contacts tagged as **Gold**. To do that:

1. Navigate to **Reports&Segments > Manage Custom Reports**.
2. Click **Create Report** and fill all the required information in the **General**, **Designer** and **Chart Designer** sections as described in the [Create a Custom Report](../../reports-segments/reports/custom-reports.md#user-guide-business-intelligence-reports-use-custom-reports) guide.
3. Within the **Filters** section, add the **Field Condition** by dragging it to the right.
4. Select **Contact > Tags**.
5. Enter  **is any of Gold**.
6. Click **Save and Close**.

![Apply the mentioned conditions in the Filters section](user/img/system/tags_management/report_create_gold_22.png)![Illustrate the created reports with selected tags](user/img/system/tags_management/report_created_gold_23.png)

You can create any reports of your choice and filter them by tag in a similar manner.

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
