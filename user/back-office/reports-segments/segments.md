<a id="user-guide-business-intelligence-filters-segments"></a>

# Manage Segments in the Back-Office

Segments are dynamically filtered subsets of the data (e.g., product collection, marketing list). To use a set of records in reports, filters, web catalog nodes, or marketing lists, you can create a segment and reuse it instead of copying the same query as a condition.

![Creating a filter condition using the Apply Segment option](user/img/reports/use_segments_in_filter.png)

Segment combines a set of records filtered using the query that may use the following information as the foundation:

* Activity
* Data audit
* Field Condition
* Segment
* Condition Group

Dynamic segments refresh automatically. Segments of manual type require explicit refresh by clicking **Refresh** <i class="fas fa-sync-alt" aria-hidden="true"></i>.

<a id="user-guide-business-intelligence-create-segments"></a>

## Create a Segment

To create a new segment:

1. Navigate to **Reports & Segments > Manage Segments** in the main menu.
2. Click **Create Segment**.
3. In the *General Details*:
   ![Creating the dynamic Featured Products segment for the product entity](user/img/reports/segment_general.png)
   1. Fill in the segment name.
   2. *Optionally*, add a **Description** to help you and other users understand the segment’s purpose or peculiarities in the future.
   3. Select the primary entity that segment should look up.
   4. Select the segment type from the list. **Dynamic** segments are updated as soon as any changes have occurred in the system. **Manual** segments are updated only following the manual refresh action when viewing the segment details.
   5. Optionally, specify the records limit. The segment shows the first X results in case the limit is provided.
   6. Select the segment owner - a business unit, members of which can manage the segment, subject to the roles defined in the system.
4. In the *Designer > Columns* section, define the set of the fields of the entity records to be shown in the segment.

   To add a column to the grid:
   > 1. Choose a field from the drop-down in the **Column** section.
   > 2. Type in a label to refer to the field in the segment report on the interface. The field label is used by default. Customize it if necessary.
   > 3. Define the sorting order for at least one column in the segment to sort the resulting data set by the field value.
   > 4. Click **Add** button.
   > 5. Reorder the columns by clicking on the line and dragging it to the necessary location.

   > ![Adding the product status, featured products, product id, and SKU columns in the designer section](user/img/reports/segments_column.png)

   To manage the columns, use action icons in the last column:
   > - Delete a column from the segment with ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg).
   > - Edit the column settings with <i class="fa fa-edit fa-lg" aria-hidden="true"></i>.
   > - Change the column position, dragging the column by the <i class="fas fa-arrows-alt-v" aria-hidden="true"></i> icon.
5. In the *Designer > Filters* section, define the filter to select the records for the segment.
6. Click **Save**.

## Refresh a Manual Segment

To refresh the data in the segment of the manual type:

1. Navigate to **Reports & Segments > Manage Segments** in the main menu.
2. Click on the necessary segment line.
3. Click **Refresh** <i class="fas fa-sync-alt" aria-hidden="true"></i>.

## View a Segment Filtered Record

To view the records selected using the segment filter:

1. Navigate to **Reports & Segments > Manage Segments** in the main menu.
2. Click on the necessary segment line.

![View the Featured Products segment outcome](user/img/reports/segment_view.png)
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
