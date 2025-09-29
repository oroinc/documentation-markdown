<a id="user-guide-business-intelligence-filters-management"></a>

<a id="user-guide-getting-started-filters"></a>

<a id="user-guide-filters-management"></a>

# Use Filters in the Back-Office

Filters are used to define a set of records to be displayed. Its configuration automatically enables users to select only the records that meet the filter requirements.
Filters are always created for the records of a specific type ([entity](../../glossary.md#term-Entity)) specified in the general details of the relevant field.

This section will help you learn the basics of filtering expressions and their elements.

## Filter Options

To define a filter, use any of the following filter options or combine them:

- **Field Condition**: select only the records with specific values of the selected [fields](../../glossary.md#term-Field).
- **Activity**: select only the records to which a specific kind of [activity](../activities/index.md#user-guide-activities) has been/has not been assigned.
- **Data Audit**: select only the records that have been modified in a specific way (available only when the corresponding functionality is enabled for an entity).
- **Conditions Groups**: sets of field conditions that combine requirements of several other filters in one group.
- **Segments**: sets of records dynamically or manually updated in compliance with predefined filters. More details are described in the [Segments guide](segments.md#user-guide-business-intelligence-filters-segments).

Sample filter that finds all the records with any related activity logged:

![All options available under the Filters section](user/img/reports/filters_1.1.png)

## AND/OR Operators

To combine the conditions of two or more filters, you can use the operators **AND** and **OR**:

- If **AND** is used, only the records that meet the conditions of all the connected filters will be selected.
- If **OR** is used, all the records that meet the conditions of any of the connected filters will be selected.

The following sections provide a detailed explanation of the filters with examples for different operators.

![Illustrating the usage of AND/OR operators with the options under the Filters section](user/img/reports/filters_1.png)

<a id="user-guide-business-intelligence-filters-field-conditions"></a>

## Field Conditions

Field Condition filters specify a rule for values of the record attributes. Only the records that meet the condition will be selected.

To define a field condition:

1. Drag **Field condition** to the box on the right.

> ![Dragging the Field condition option to the constructor field](user/img/reports/filters_2.png)
1. Click **Choose a field**.
2. A list of fields appears. At the top of the list, you can see the field’s name, for which the records are filtered. (In the example below, it is an Opportunity). Below the Opportunity name is a list of all available fields related to it.

> ![View the list of fields related to the opportunity record](user/img/reports/filters_4.png)
1. Select a field that you want to apply for the rule:

> - This can be a field of the entity selected in the **General** section. For example, we can filter Opportunity records by status.

> ![Filtering the opportunity record by status](user/img/reports/filters_5.png)
> - You can also select a field of another related entity. For example, if you want the list to contain only Opportunities assigned to a customer, scroll down the list and select this field under the *Related Entities* header.

>   The name of the selected field (e.g., *Customer*) will appear at the top of the list.
>   ![Filtering the opportunity record by customer name](user/img/reports/filters_7.png)
> - You can also add another field related to *Customer* under the *Related entities* section. For example, you can select only the customers with addresses in California.
>   ![Filtering the opportunity record by customer name and address](user/img/reports/filters_8.png)

#### HINT
Once you have specified all the required conditions, another default field condition appears. Some components of this field contain links with a list of possible values suitable for the specified field.

![Filtering the opportunity record by customer name and city that contains California](user/img/reports/filters_9.png)

<a id="user-guide-business-intelligence-filters-activity"></a>

## Activities

The **Activity** filter specifies a rule for [activities](../activities/index.md#user-guide-activities) assigned to the record. Only the records that meet the condition will be selected.

To define the activity settings:

1. Drag **Activity** to the box on the right.
2. There are three selector links:

> - *Has activity /has not activity* - only the records to which the defined activity has/has not been assigned will be selected.
>   ![Creating a filter condition using the Activity option](user/img/reports/filters_10.png)
> - The List of available activities to filter by.
>   ![Creating a filter condition using the Activity option setting Has Activity to All](user/img/reports/filters_11.png)
> - *Choose a field*: select the field to filter by. For example, we will select only the records for which a call was logged after June 1, 2019.
>   ![Creating a filter condition for the calls logged after June 1, 2019.](user/img/reports/filters_12.png)

<a id="user-guide-business-intelligence-filters-data-audit"></a>

## Data Audit

The **Data Audit** filter specifies a rule for the record changes recorded in the system. Only the records that meet the condition will be selected.

To define the data audit settings:

1. Select a field for which a condition is defined in the same way as described above in [Field Conditions]().
2. Determine if the condition should be valid for the records where the field has or has not been changed.
   ![Creating a filter condition using the Data Audit option](user/img/reports/filters_13.png)
3. Select the date when the changes have/have not been applied.

For example, we will select only the records for which the Job Title value has been changed since June 1, 2019.

![Creating a filter condition for job titles that have been changed since June 1, 2019](user/img/reports/filters_14.png)

#### NOTE
You can combine any number of Activity, Data Audit, and Field Condition filters, joining them with the **AND** and **OR** operators.

<a id="user-guide-business-intelligence-filters-condition-groups"></a>

## Conditions Groups

A conditions group is a set of activity and/or data audit and/or field condition filters already joined with the **AND** and **OR** operators. A field condition works as the brackets in mathematics, so all the filters added to a condition group are applied first.

To define the **Condition Group** filter:

1. Drag **Conditions Group** to the box on the right.
2. Add the Activity, Data audit, and Field Condition filters to the section that appears.
3. Define the conditions and conjunctions between them.

#### IMPORTANT
Keep in mind that if a user generates a report with several conditions (for example, A and B) in one conditions group, they receive the report that includes the values that satisfy the A condition, the B condition, and both. If you want to get the report only with both conditions applied, enable the **Group Same-Entity Conditions Within Condition Groups** option in the [system configuration](../system/configuration/system/general-setup/display.md#doc-configuration-display-settings-report). This way, the report will only contain values that match all the defined conditions.

For complex conditions, it is a good idea to outline the conditions first.

A condition group may also be included in another condition group as a separate filter.

<a id="user-guide-filters-segments"></a>

## Segments

A segment is a set of the Activity, Data Audit, Field Condition, and Condition Group filters created separately for the records of a specific field. It can be updated dynamically or upon a user’s request.

In other words, if you often need to use a specific set of conditions to filter the entity records, you can create a segment and use it instead of redefining the same conditions again.

The ways to create and manage segments are described in more detail in the [Segments guide](segments.md#user-guide-business-intelligence-filters-segments).

To add a segment to the filters:

1. Drag **Apply segment** to the box on the right.
   ![Dragging Apply segment to the box](user/img/reports/filters_15.png)
2. Click **Choose segment** and select one of the segments predefined in the system.

Subject to the conjunction with the rest of the conditions, the list will now include:

> - Only the records from the segment that correspond to the rest of the conditions (**AND** is used).
> - The records that correspond to the rest of the conditions and the segment (**OR** is used).
