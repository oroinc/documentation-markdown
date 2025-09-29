<a id="user-guide-territories"></a>

# Manage Sales Territories in the Back-Office

#### NOTE
Sales Territories are only available in the Enterprise edition.

A [sales territory](../../glossary.md#term-Sales-Territories) is the customer group or geographical area for which an individual sales person or a sales team holds responsibility. Territories can be based on various factors such as geography, industry, product line, the expected revenue, etc. Territory Management is a system by which customer accounts are grouped based on a defined set of criteria. This makes for easy sharing of customer accounts among sales teams in your company. In the simplest scenario, you can assign tasks based on geographical territory relation, where a sales rep A can be responsible for country A, a sales rep B can be responsible for country B.

Currently, the sales territory management is available for leads, opportunities and all types of customers.

With sales territories you can:

- Define territories for leads, opportunities, and any customer type
- Organize and balance the workload of sales people
- Automatically assign records to different territories
- Prioritize specific territories making sure they do not overlap
- Filter data by territory via the dashboard widget

## Enable Territories

Sales Territories are disabled by default. Prior to starting work with territory management, ensure that it is enabled in your Oro application instance. For configuration instructions, see the [relevant guide](../system/configuration/crm/sales-pipeline/sales-territories.md#sys-configuration-crm-sales-pipeline-sales-territories).

## Create a Territory

Territories menu becomes available under **Sales** in the main menu when the sales territories feature is enabled in system configuration.

To create a new territory:

1. Navigate to **Sales > Territories** and click **Create Territory**.
   ![The create territory page](user/img/sales/sales_territories/create_territory.png)
2. Provide the following information in the **General** section:

   | Field           | Description                                                                                                                                                                                                                             |
   |-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Name**        | The name specified for your territory.                                                                                                                                                                                                  |
   | **Owner**       | Limits the list of users who can manage the territory.                                                                                                                                                                                  |
   | **Priority**    | Territory with the highest priority (e.g. 1) will be assigned to the record in case of overlapping definitions. The lower is the number, the higher is the priority. For more details on priorities, see the next section of the guide. |
   | **Description** | If necessary, enter a short but meaningful description related to the territory you are creating.                                                                                                                                       |

### Set a Priority

Setting a priority determines what records the territory should display, or which territory should display what data.

#### NOTE
Please avoid using negative priority numbers as this may cause the confusion.

As an illustration, two overlapping territories have been created - **Leads France** and **Leads Paris**. These two territories will overlap if some of leads’ addresses have France specified for the country and Paris for the city within the same address record.

![The list of all territories highlighting the two that overlap Paris](user/img/sales/sales_territories/leads_france_paris.png)

The priority of 30 has been set for Leads France, and the priority of zero was left for Leads Paris. When the territories are activated, Leads Paris will display leads (assigned records) that fall into Leads France as well as Leads Paris category.

![The Leads Paris territory view page](user/img/sales/sales_territories/leads_paris_higher.png)

So, in this scenario, Leads France will have **no** assigned leads as Leads Paris will take them over.

![The Leads France territory view page](user/img/sales/sales_territories/france_lower.png)

### Use Filters

A number of [filters](../reports-segments/filters.md#user-guide-filters-management) will be displayed on the Create Territory page. Each filter will correspond to the entity for which the territory has been enabled. Setting conditions to the filter of a specific entity will add a territory to its records. For instance, if you enable territories for leads, a Lead filter will become available in the Create Territory form. When you set conditions to the Lead filter, a territory will be added to the records of leads.

![Display the filter possibilities in the storefront](user/img/sales/sales_territories/filters.png)

#### NOTE
When conditions are not set for a specific entity, a territory is not added to its records.

As an example, we have set a condition to the Opportunity filter, looking only for those that have the budget amount higher than $1000.

![Display the filter condition configured for the opportunity entity that would search only the records that have the budget amount higher than $1000.](user/img/sales/sales_territories/set_filter.png)

Once the territory is saved, it will need to be activated to be able to function (see the section below).

## Activate a Territory

Once the details have been saved, a new territory with its matching records should become available in the **Matching Records** section. Matching records are records filtered according to the conditions determined for a specific territory. By default, the territory is inactive. To activate the territory and assign it to the opportunity records, click Activate.

#### NOTE
Note that if the territory has not been activated, the Territory column of the Matching records grid will not contain any values yet.

Note that you can edit the territory only when it is inactive. If you wish to edit the territory that is active, click Deactivate and then Edit.

Once the territory has been activated, **Assigned Records** section will become available on the territory view page. Assigned records are records that have been assigned a specific territory as the result of the filter conditions determined when creating a territory.

![A sample of the Opportunity territory with the records that have the budget amount higher than $1000](user/img/sales/sales_territories/opp_activate.png)

When entities have been assigned a territory, each of them will be displayed on the view page of the territory, to which they have been assigned.

#### NOTE
When a territory is activated, it is automatically assigned to all existing records that fall under its definition, and to all new records when they are created.

## Manage Territories from the Territories Grid

As soon as the territory has been created and records assigned, you can view and manage it within the Territories grid.

You can perform the following actions for an **inactive** territory from the grid:

- Activate: <i class="fa fa-check fa-lg" aria-hidden="true"></i>
- View: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
- Edit: <i class="fa fa-edit fa-lg" aria-hidden="true"></i>
- Delete: <i class="fas fa-trash-alt" aria-hidden="true"></i>

![The actions you can perform to disabled territories from the grid](user/img/sales/sales_territories/inactive_territory_manage.png)

You can perform the following actions for an **active** territory from the grid:

- Deactivate: <i class="fa fa-ban fa-lg" aria-hidden="true"></i>
- View: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>

![The actions you can perform to active territories from the grid](user/img/sales/sales_territories/active_territory_manage.png)

It is possible to filter records by territories. To enable the territory filter, click Grid Settings and, in the **Filter** tab, select **Territory** from the list.

![The steps you need to take to add a territory filter to the filter tab](user/img/sales/sales_territories/grid_filters.png)![Filter the opportunity records by the Opportunity territory](user/img/sales/sales_territories/grid_filters_vip.png)

## View Territories

### From the Grid of an Assigned Record

To be able to view territory assignment from the grid of the related entity, make sure that **Territory** is enabled in the **Grid Settings**.

![Highlight the territory filter in the grid settings](user/img/sales/sales_territories/grid_settings_territory.png)![A list of all open opportunities with the related territories column](user/img/sales/sales_territories/grid_territories.png)

When enabled, the Territory column will appear in the grid showing the territory to which a particular record is assigned.

### From the View Page of an Assigned Record

When a record is assigned a territory, it is displayed in the Territory field on the view page of that record.

![View the related territory from the selected account page](user/img/sales/sales_territories/territory_view_page.png)

## Territories in Widgets

Sales Territories can also be used in the following widgets:

- Forecast
- Leads Statistics
- Opportunities Statistics
- Opportunities by Status

Within these widgets, you can view records filtered within one or several specific territories.

![Enabling territories for the Forecast widget](user/img/sales/sales_territories/forecasts.png)![Enabling territories for the Opportunity Statistics widget](user/img/sales/sales_territories/opp_statistics.png)![Enabling territories for the Lead Statistics widget](user/img/sales/sales_territories/leads_statistics.png)![Enabling territories for the Opportunities by Status widget](user/img/sales/sales_territories/opp_by_status_ter.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
