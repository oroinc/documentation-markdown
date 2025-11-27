<a id="doc-grids"></a>

<a id="doc-grids-open-grid"></a>

<a id="doc-grids-grid-page"></a>

<a id="user-guide-ui-components-create-pages"></a>

# Record Tables (Grids)

In Oro, the list of all available records of one type is aggregated on one page within a table (also called *a grid*). The data in the record tables can be filtered and saved as a new page, and the columns in the table can be customized to display only the required information. The page with all single-type records has a number of actions available as buttons on its top right. In addition, each item on the list has a number of actions available in the ellipsis (or the more options) menu at the end of its row. Actions at the top of the page and those within the ellipsis menu are all subject to the type of the records they are meant to apply to.

![A sample of a record table](user/img/getting_started/navigation/grids_grid.png)

You can reach record tables in the following ways:

1. Via the main menu (e.g., Marketing > Marketing Lists).
2. Via the [shortcuts menu](shortcuts.md#user-guide-getting-started-shortcuts).
3. By clicking the grid link on the page of a record (see the screenshot below).
   ![Click the grid link on the page of a record](user/img/getting_started/navigation/grid_from_view.png)

<a id="doc-grids-actions-pager"></a>

<a id="doc-grids-actions-set-items-per-page"></a>

## Navigate Between Table Pages

If you have a lot of records, they may not all fit on one data page. In this case, use the pager block that you can see in the center above the table. In the pager block, you can see the page that you are currently on, the total number of pages, and the total number of records in the table.

![Pager block](user/img/getting_started/navigation/grids_pager.png)

You can navigate between pages using the **<** (previous page) and **>** (next page) buttons. To open a particular page, type its number in the field that displays the current page and press **Enter**.

To change the number of records displayed per page, click the **View Per Page** drop-down list on the top right of the table, and select the required number of items per page.

<a id="doc-grids-actions-refresh"></a>

<a id="doc-grids-actions-export"></a>

<a id="doc-grids-actions-adjust"></a>

<a id="doc-grids-actions-change-table"></a>

<a id="doc-grids-actions-change-column-order"></a>

<a id="doc-grids-actions-sort-data"></a>

<a id="doc-grids-actions-reset"></a>

<a id="doc-grids-actions-grid-views-share"></a>

## Manage Data in Tables

The tables not only display record data but also contain links to the pages of these records. In addition, the tables are configurable, so you can adjust the appearance and contents of these tables to your taste and needs using the action buttons:

1. **Export Data** — Use to export the data in the table to a file either in .csv or .xlxs format (available formats may vary). Import results are sent to your email.
2. **Sort Data** — By default, data in tables is sorted in ascending order by the first column. To sort a field, click the column header. When sorting is ascending, an upward arrow appears next to the column name. When sorting is descending, a downward arrow appears.
3. <i class="fas fa-redo-alt" aria-hidden="true"></i> **Refresh** — Use to refresh the data displayed in the table and retrieve the latest details
4. <i class="fas fa-sync-alt" aria-hidden="true"></i> **Reset** — Use to clear the table customization and return to default settings. Reset applies to all filters, records per page, and sorting changes you have made.
5. <i class="fa fa-cog fa-lg" aria-hidden="true"></i> **Grid Settings** — Use to define which columns to show in the table.
   * You can manually select the columns by clicking on the checkbox next to the required field.
   * To show all columns in the table, click **Select All**.
   * To change the order of the columns, click on the arrow icon next to the name of the column you wish to move, hold the mouse button, and drag the column to the required position.
   * Use the quick search field to find the required item quickly.

   #### IMPORTANT
   Some fields that an entity has may be unavailable as columns in the table. The system administrator defines the list of available fields. If you are the system administrator, see the description for the **Show on Grid** field in the [Advanced Entity Field Properties](../../system/entities/entity-fields/entity-fields-advanced-properties.md#admin-guide-create-entity-fields-advanced) topic.
6. <i class="fa fa-filter fa-lg" aria-hidden="true"></i> **Filters** — Use to show/hide filters to select specific items to be displayed in the table. More information on filters is provided in the Filters section below.

#### NOTE
The default settings define whether to paginate data in tables, how many items to show per page, and what maximum number of pages can be shown. They also define whether the top of the table is locked so you can see the page name, data headers, etc., when you scroll. Usually, these settings are defined by the system administrator for the whole Oro application.

<a id="doc-grids-actions-filters"></a>

<a id="doc-grids-actions-filters-showhide"></a>

<a id="doc-grids-actions-filters-select-to-display"></a>

<a id="doc-grids-actions-filters-apply"></a>

## Filter Data in Tables

Filters are used when you need to quickly pick out the records you need from the entire data pool.

The following actions are available for filters:

1. To show/hide filters, click <i class="fa fa-filter fa-lg" aria-hidden="true"></i>
   ![Click the filter button to display available filters](user/img/getting_started/navigation/grids_filters.png)

   By default, filters are hidden. When filters are hidden, and some are currently applied to the data in the table, you will see a summary of the applied filters at the top of the table. Click the summary to show filters.
   ![A short summary of the applied filters](user/img/getting_started/navigation/grids_filters_applied-hidden.png)
2. To apply a filter, click on its button in the bar and specify your query in the control that appears. Note that filter controls might look different depending on the type of data you are going to filter — whether it is textual, numeric, date, or option set. After the filter is applied, its query will appear in the controls, so you can easily recall how you have filtered the data.
3. Click on a cross **x** after the query to remove a filter.
4. To select which filters from the available set to display, click **Manage Filters**. Select the checkboxes in front of the filters you want to display. You can use a search field at the top of the list to quickly find the required filter.

### Types of Filters

The controls available for fields depend on the field type.

1. **Text fields that can take any value**

   For text fields that can take any value, you can enter search words (or part of the word) and select from the list in front of it whether the values that you select must contain these search phrase at any position or does not contain it at all, must start with it, end with it, etc.
   ![Available values in the contains dropdown](user/img/getting_started/navigation/grid_filters_define.png)

   For conditions like ‘Is Any Of’ and ‘Is Not Any Of,’ enter search words separated by the comma.
2. **Fields that can take limited values**

   Start typing the required value into the text field. When this value appears in the drop-down list, click it to select. You can click the empty text field to see the list of all available values.
3. **Dates and time**

   Click the date fields to select the date via the calendar menu. Click the time fields to select a time from the list.

   In addition to selecting a strict calendar date, you can use variables that enable you to specify relative values, such as ‘today,’ ‘start of the month,’ etc.
   ![Variables that enable to specify relative values such as ‘today,’ ‘start of the month,’ etc](user/img/getting_started/navigation/grids_filters_apply2-2.png)

   Also, specify the condition of how to form your desired time range, whether it starts from the day and time that you specified, lies between set dates, etc.
   ![Specify the condition of desired time range](user/img/getting_started/navigation/grids_filters_apply2-3.png)

#### IMPORTANT
If more than one filter is active, only the records that meet the requirements of *all* selected filters are displayed.

<a id="doc-grids-grid-views"></a>

<a id="doc-grids-actions-grid-views-create"></a>

<a id="doc-grids-actions-grid-views-set-default"></a>

<a id="doc-grids-actions-grid-views-rename"></a>

## Mass Actions in Tables

With the help of checkboxes preceding individual records, you can perform mass actions on all or selected records.

For example:

* Mass delete and edit some records

![Delete the selected contact records](user/img/getting_started/records/grids/grids_delete_bulk.png)
* Mass merge contacts, accounts and campaigns

![Merge the selected contact records](user/img/getting_started/records/grids/grids_merge.png)
* Select which products to add to a product collection content variant in a web catalog

![image](user/img/getting_started/records/grids/web-catalog.png)
* Select what products qualify for a promotion

![image](user/img/getting_started/records/grids/grid-promotions.png)
* Choose what products to include in a master catalog category.

![image](user/img/getting_started/records/grids/master-catalog-grid.png)

#### NOTE
These checkboxes are for mass actions only, and **do not affect records during export**.

To perform mass actions on records:

1. Select the checkboxes next to the records you want to apply a mass action to.
2. Click the ellipsis menu at the right end of the grid table and select the required action.

![Mass actions in grids](user/img/getting_started/records/grids/mass-actions.png)

## Create Saved Table Views (Grid Views)

A saved view is a table with applied filters or custom orders. The default table view is what you see when opening a page with all single-type records. It shows unfiltered data.

#### NOTE
For some entities, additional default table views exist (e.g., **Open Leads** for leads, **Duplicated Accounts** for accounts).

If you need to use a frequent set of filters, save them as a custom table view.

To save a table as a new one:

1. Click **Options** next to the table name.
2. Click **Save as**.
3. In the dialog, define the name of the new table view and set it as default if necessary.
4. Click **Save**.
5. To open a particular table view, click the arrow next to the current view name, and then click the name of the view you want to open.

To manage saved views, click **Options** next to the view name. The following is the list of options available:

1. Rename
2. Share with Others/Unshare (available for the Enterprise edition only)
3. Delete (custom views)
4. Set as Default

![The list of available options under Options](user/img/getting_started/navigation/Table_Options.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
