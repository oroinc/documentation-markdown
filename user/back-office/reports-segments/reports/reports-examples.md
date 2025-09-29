<a id="user-guide-business-intelligence-reports-reports-examples"></a>

# Reports in Use

This section contains several examples of the report configuration.

## Aggregate Data in the Report

Below is an example of a simple report that displays a particular budget per opportunity.

![An example of a simple report that displays a particular budget per opportunity](user/img/reports/reports_examples_1.png)
1. Once you set up the *Budget amount* column, click **Add** to add it into the **Columns** list.
2. Click **Save**.
3. You are now redirected to the report view that shows the opportunities with the known **Budget Amount**:
   ![Report view with the opportunities](user/img/reports/reports_examples_2.png)
4. Click **Edit** to continue the report configuration.

Let us see what happens after we use the **Count** function for the **Opportunity Budget** column:

1. Click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to update the column and change the function for the **Budget amount** to *Count*.
   ![Selecting the Count function for the budget amount from the dropdown list](user/img/reports/reports_examples_3.png)
2. Click **Save**. The report data changes:

   **Report Preview (Function = Count)**
   ![Report example illustrating the count function](user/img/reports/reports_examples_4.png)

Similarly, you can use sum, max, average, and min functions.

**Report Preview (Function = Sum)**

![Report example illustrating the sum function](user/img/reports/reports_examples_5.png)

The sum of **Budget Amount** values of all opportunities makes $202,565.00.

**Report Preview (Function = Max)**

![Report example illustrating the max function](user/img/reports/reports_examples_6.png)

The biggest budget amount value of the opportunity is $9,902.00.

## Use Simple Grouping by Value

You can group the information in the report by unique values in the column(s).

![Report example illustrating the grouping by unique values function](user/img/reports/reports_examples_7.png)

The report preview:

![Preview of the report outcome grouped by opportunity status](user/img/reports/reports_examples_8.png)

## Use Grouping by Value at Multiple Levels

You can group records based on several columns (e.g., per opportunity status and the business customer name).

![Report example illustrating the multiple columns grouping function](user/img/reports/reports_examples_9.png)

Now, you can see the calculated budget metrics (total, average, min, and max) for all the opportunities with the same status that belong to a specific customer.

The report preview:

![Preview of the report outcome grouped by opportunity status and customer name](user/img/reports/reports_examples_10.png)

#### HINT
Once a report is generated, you can click the name of a column to sort all the data in the report by the specified field value (ascending or descending).

Here is an example of the report ordered by the **Name** column:

![Preview of the report outcome ordered by Name in the descending order](user/img/reports/reports_examples_11.png)

As you can see in the outlined area, there are opportunities which are won, lost and requires analysis for Albers Super Markets. You can view the budget details for the all those groups.

#### NOTE
If the customer’s name is the most important part of the grouping, it might be reasonable to edit the report and move the column to make it first.

<a id="user-guide-business-intelligence-reports-chart-examples"></a>

## Use Charts

Let us make a chart for the budget per opportunity status report (not grouped by customers).

Configuration:

![Configuring the line chart with the status in the X axis and budget amount in the Y axis](user/img/reports/reports_examples_12.png)

Output:

![The report preview illustrating the previously set configuration](user/img/reports/reports_examples_13.png)

**Related Topics**

[Use System Reports](system-reports.md#user-guide-business-intelligence-reports-use-system-reports)
[Use Custom Reports](custom-reports.md#user-guide-business-intelligence-reports-use-custom-reports)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
