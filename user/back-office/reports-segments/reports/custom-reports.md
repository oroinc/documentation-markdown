<a id="user-guide-business-intelligence-reports-use-custom-reports"></a>

# Use Custom Reports

## Create a Custom Report

To create a custom report:

1. Navigate to **Reports and Segments > Manage Custom Reports** in the main menu.
2. Click **Create Report** at the top right of the page.
3. On the **Create Report** page, define properties of the report, as described in the sections below.

### General

![View the Create Report page](user/img/reports/custom_reports_1.png)

The following fields are mandatory and **must** be defined for a report:

| Field           | Description                                                                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Name**        | A name that is used to refer to the report on the interface.<br/><br/>It is recommended to create a name that indicates the information the report presents.                                                                                                          |
| **Entity**      | A target [entity](../../../glossary.md#term-Entity) of the report. Its data will be used to generate the report.<br/><br/>Select one of the entities from the list. (You can also start typing the entity name in the text field to narrow down your entity choices.) |
| **Report Type** | Select *Table* from the list. The report will present the data in the form of the table. Currently, this is the only available type.                                                                                                                                  |
| **Owner**       | Select the user who can manage this report and be responsible for it.                                                                                                                                                                                                 |

The only optional system field is **Description**. It can be used to save additional information about the report.

### Designer

In the **Designer** section, you can define the structure of your report.

![View the settings under the Designer section](user/img/reports/custom_reports_2.png)

There are four main subsections that help you build your report:

- **Columns**—In this subsection, you define which columns your report will contain.
- **Grouping**—In this subsection, you can define how the information in your report will be aggregated.
- **Grouping by Date**—In this subsection, you can enable period filters.
- **Filters**—In this subsection, you apply filters to the data of your report to select only the information you need.

#### Columns

<a id="user-guide-business-intelligence-reports-add-a-column"></a>

##### Add a Column

To add a column:

1. Specify the required data:

| Field        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Column**   | Select the field that contains the required values. The column must be related to the information specified in the **Entity** field of the **General** section.<br/><br/>You can see the available fields in the list, where fields are grouped by entities.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Label**    | If required, you can rename the label of the selected field. This custom name will be applicable only to the current report.<br/><br/>By default, the field label is used.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Function** | Select a function that you want to apply to the field values. The function processes a set of values and displays the requested information.<br/><br/>For example, you want a report that shows the number of opportunities with each of the statuses **Open**, **Closed Won** and **Closed Lost**. Then, you can create a report with target entity **Opportunity**. For the opportunity’s columns, add **Status** and **Id**. For the **Id** field, specify the **Count** function.<br/><br/>![Create a report for the opportunity entity with the status and ID columns](user/img/reports/custom_reports_3.png)<br/><br/>As the result, the system takes the first of the statuses and counts how many Ids are listed under it, and the same for other statuses.<br/><br/>![The opportunity report output provided that the Count function was selected for the ID column](user/img/reports/custom_reports_4.png)<br/><br/>There are some field-specific functions (e.g. **Won Count** that shows the number of won opportunities) for the opportunity’s **Status** field. The most common functions are the following:<br/><br/>- **None**—The data is not aggregated, you will see field values as they are.<br/>- **Count**—The column displays the number of values in the set.<br/>- **Sum**—The column displays the sum of all values in the set.<br/>- **Average**—The column displays arithmetical mean of the values in the set.<br/>- **Min**—The column displays the smallest value in the set.<br/>- **Max**—The column displays the largest value in the set.<br/><br/>#### NOTE<br/>You can see only the functions available for the selected field. For example, **Sum** is applicable only to numeric fields.<br/><br/>#### IMPORTANT<br/>When you specify a function for any column, all other columns must be added to the **Grouping** section of your report. |
| **Sorting**  | Select the sorting order for the field.<br/><br/>- **None**—The data in the field are not sorted.<br/>- **Asc**—The data are sorted in the ascending order (e.g. from the smallest to the largest number, or from A to Z).<br/>- **Desc**—The data are sorted in the descending order (e.g. from the largest to the smallest number, or from Z to A).<br/><br/>#### IMPORTANT<br/>If sorting is defined for several columns, the report is sorted according to the order specified for the first column, and then, if multiple values of other columns correspond to any value of a first column, they will be sorted according to the order defined for the next columns.<br/><br/>Let us display the following table.<br/><br/>Unsorted:<br/><br/>| A   |   1 |<br/>|-----|-----|<br/>| C   |   1 |<br/>| B   |   3 |<br/>| A   |   3 |<br/>| B   |   2 |<br/>| B   |   1 |<br/>| C   |   3 |<br/><br/>For example, the **Asc** sorting is defined for the first column and **Desc**—for the second:<br/><br/>Sorted:<br/><br/>| A   |   3 |<br/>|-----|-----|<br/>| A   |   1 |<br/>| B   |   3 |<br/>| B   |   2 |<br/>| B   |   1 |<br/>| C   |   3 |<br/>| C   |   1 |<br/><br/>After the report has been generated, it can be sorted by any of its columns.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
1. Click **Add**.

The field you have defined will appear in the **COLUMN** table.

##### Edit a Column

To edit a column:

1. Click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon to the right of the corresponding row.
2. Perform the required changes as described in the [Add a Column]() section description.
3. Click **Save**.

##### Delete a Column

To delete a column:

1. Click the <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** icon to the right of the corresponding row.
2. In the **Delete Confirmation** dialog box, click **Yes, Delete**.

##### Rearrange Report Columns

To move a column, click the <i class="fas fa-arrows-alt-v" aria-hidden="true"></i> **Move** icon to the right of the corresponding row, hold the mouse button, and drag the column up (to make it appear earlier in the report) or down (to make it appear later).

#### Grouping

When you specify a function for some of the fields, you need to add all other fields (that do not have any function specified for them) to the **Grouping** section.

##### Add a Field to Grouping

To add a field to the **Grouping** section, select it from the **Grouping Columns** field, and click **Add**. For example, you can see a total, average, maximum, and minimum budget amount for each opportunity with the same status.

#### WARNING
Do not add fields that are not present in the **Columns** section.

##### Remove a Field from Grouping

To remove a field from the **Grouping** section:

1. Click the <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** icon to the right of the corresponding row.
2. In the **Delete Confirmation** dialog box, click **Yes, Delete**.

#### Grouping by Date

In this section, you can define whether to show additional period filters for this report on the report view page.

![The report output with the enabled grouping by day filter](user/img/reports/custom_reports_6.png)

With these filters, you can define the date range to filter the report data and group the data in this range by periods (days, month, quarters, years).
You can also decide whether to show or not the periods that do not contain any data.

![The report settings that define whether to show or hide the periods that do not contain any data](user/img/reports/custom_reports_7.png)

| Field                            | Description                                                                                                               |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Enable Grouping by Date          | Select this check box to enable additional date filters.                                                                  |
| Date Field                       | Select the date field which will be used for grouping. Only the date fields related to the selected entity are available. |
| Allow to Skip Empty Time Periods | Select/deselect this check box to show/hide the periods that do not contain any data.                                     |

#### Filters

You can define the conditions used to select specific records. Only the data of the records that meet all the conditions defined in the **Filters** section will be used for the report.

For more details, see the [Filters](../filters.md#user-guide-business-intelligence-filters-management) guide.

### Chart Designer

![The settings of the Chart Designer section](user/img/reports/custom_reports_8.png)

#### Chart

OroCommerce supports line charts. To create a line chart for the report, define the following fields (all the fields are mandatory) in the **Chart** section.

| Field                 | Description                                                                      |
|-----------------------|----------------------------------------------------------------------------------|
| **Chart Type**        | Currently only the **Line Chart** option is available                            |
| **Category (X Axis)** | Select the fields with the values which will form the X Axis of the report chart |
| **Value (Y Axis)**    | Choose the fields with the values which will form the Y Axis of the report chart |

For more details, see the [chart example](reports-examples.md#user-guide-business-intelligence-reports-chart-examples).

## View a Custom Report

### From the Custom Reports List

In the main menu, navigate to **Reports & Segments > Manage Reports**, and in the custom reports list, click the required report.

Alternatively, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu and click the <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** icon.

![The actions you can perform with reports](user/img/reports/custom_reports_9.png)

### From the Custom Report View Page

In the main menu, navigate to **Reports & Segments**. Custom reports are gathered in sections by the name of the field they are related to. Select the required section, navigated further to the desired report, and click it.

![Navigating to the custom report from the main menu](user/img/reports/custom_reports_10.png)

## Export a Report

#### NOTE
Please be aware the Export Grid button may not be available for some reports if the grid you want to export contains grouping by a related entity.

1. Open the report that you want to export:
   * To export a custom report, navigate to **Reports & Segments > Manage Reports** in the main menu and click the required report.
   * To export a system report, navigate to **Reports & Segments > Reports** in the main menu and further to the required report (e.g. **Reports & Segments > Reports > Accounts > Life Time**).
2. On the report page, click the **Export Grid** button in the upper-left corner, and then click **CSV** or **XLSX** to export the report to the file of the corresponding format.
   ![Highlight the Export Grid button on the custom report's details page](user/img/reports/custom_reports_11.png)

## Edit a Custom Report

### From the Custom Reports Grid

1. In the main menu, navigate to **Reports & Segments > Manage Reports**.
2. On the **All Reports** page, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu, and then click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon.
   ![Click the edit icon from the More Options menu of a selected report](user/img/reports/custom_reports_12.png)
3. Update the report details as required. For the description of the fields, see [Create a Custom Report]().
4. Click **Save**.

### From the Custom Report View Page

1. In the main menu, navigate to **Reports & Segments > Manage Reports**.
2. On the **All Reports** page, click the required report.

   Alternatively, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu, and then click the <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** icon.
3. On the report page, click **Edit** in the upper-right corner.
4. Update the report details as required. For the description of the fields, see [Create a Custom Report]().
5. Click **Save**.

## Delete a Custom Report

### From the Custom Reports Grid

1. In the main menu, navigate to **Reports & Segments > Manage Reports**.
2. On the custom reports page, select the report to delete, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu, and then click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete**.
3. In the **Deletion Confirmation** dialog box, click **Yes, Delete**.

### From the Custom Report View Page

Alternatively, you can delete a custom report from the reports view page by clicking **Delete** in the upper-right corner.

![Highlight the Delete button on the custom report view page](user/img/reports/custom_reports_15.png)

## Delete Multiple Custom Reports

You can delete multiple custom reports at a time.

1. In the main menu, navigate to **Reports & Segments > Manage Reports**.
2. Select multiple custom reports by clicking <i class="fa fa-caret-down fa-lg" aria-hidden="true"></i> in the left corner of the list header.
3. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the list header and click <i class="fas fa-trash-alt" aria-hidden="true"></i> to delete multiple reports at a time.
   ![Using the bulk delete function to delete multiple custom reports](user/img/reports/custom_reports_16.png)
4. In the **Delete Confirmation** dialog box, click **Yes, Delete**.

**Related Topics**

* [Use System Reports](system-reports.md#user-guide-business-intelligence-reports-use-system-reports)
* [Reports Examples](reports-examples.md#user-guide-business-intelligence-reports-reports-examples)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
