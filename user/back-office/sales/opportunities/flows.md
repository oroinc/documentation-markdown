<a id="admin-guide-workflows-opportunity-management"></a>

<a id="user-guide-system-channel-entities-opportunities-manage-flow-intro"></a>

# Manage Opportunity Workflow

Use workflows to define rules and guidelines of possible actions and updates of the opportunities in the application.

You can have multiple active workflows for the same entity at the same time (e.g.: alternative sales workflow that the sales representative can choose when they decide how to deal with an opportunity; parallel sales follow-up and order fulfillment workflow for a placed order, etc.).

In the following example, we have two workflows for an opportunity which are active at the same time (Opportunity Management Flow and Opportunity Support Flow).

![Opportunity Management Flow and Opportunity Support Flow](user/img/sales/opportunities/multiple_flows.jpg)

## Opportunity Management Flow

To ensure data consistency and reasoned opportunity management by a sales manager, you can activate Opportunity Management Flow under **System > Workflows**.

This can be done from the **Workflows** page by selecting Opportunity Management Flow and clicking **Activate** on the top right.

![Opportunity management flow view page](user/img/sales/opportunities/activate_opp_flow.png)

Active Opportunity Management Flow limits what a sales manager can do with opportunities, thus eliminating situations when, for instance, an opportunity is not yet closed but its close reason is specified, or an opportunity is closed but its close reason is unspecified.

### Start Opportunity Management Flow

Activating Opportunity Management Flow does not happen automatically for all opportunities. Once the flow has been activated in **System > Workflows**, you need to start it manually for the required opportunities.

It is possible to have multiple active workflows for the same record. If you have more than one active workflow, you can separately activate each of them. In the following example, two workflows are available for one opportunity record:

![Two opportunity workflows for one record](user/img/sales/opportunities/start_opp_managemtn_flow_manually.jpg)

You can set Opportunity Status and Probability manually before starting Opportunity Management Flow.

![Set opportunity status and probability](user/img/sales/opportunities/stautus_probability_opp_flow.jpg)![Two workflows active for one opportunity record simultaneously](user/img/sales/opportunities/two_workflows_active.jpg)

### Manage Multiple Workflows

Workflows are expandable and can be collapsed, if necessary, by clicking **+** on the left of the workflow as illustrated below:

![Illustrate the expanded Opportunity Management and Opportunity Support flows](user/img/sales/opportunities/collapse_flow.jpg)

### Transitions

The type of the transitions displayed for opportunities depend on the type of the enabled workflow.

The following transitions will become available as the result of Opportunity Management flow activation:

* Develop
* Close As Won
* Close As Lost

#### Develop

Develop transition is a simplified form for editing an opportunity.

![Developing an opportunity transition](user/img/sales/opportunities/develop.jpg)

#### Close As Won/Close As Lost

**Close Revenue** and **Close Reason** fields and statuses have become unavailable in the edit opportunity form as the result of flow activation.

![Close revenue and reason are deactivated](user/img/sales/opportunities/inactive_close_reason.jpg)

To close an opportunity as Won or Lost, use **Close As Won/Close As Lost** transition buttons instead. They are located at the top of Opportunities page.

![Opportunity flow transitions buttons](user/img/sales/opportunities/transitions.jpg)

Note that it is not possible to close an opportunity from the table of all opportunities, although inline editing is available after flow activation.

To close an opportunity as won:

1. Click **Close As Won**.
2. Provide **Close Revenue**.
3. Provide **Expected Close Date**.
4. Click **Submit**.

To close an opportunity as Lost:

1. Click **Close As Lost**.
2. Select **Close Reason** from the list.
3. Select the **Expected Close Date**.
4. Click **Submit**.

#### Other

Depending on their configuration, workflow steps can vary. Here is an example of the steps and transitions configured for the Opportunity Support flow.

![Example of the open Opportunity Support Flow](user/img/sales/opportunities/wf_steps.jpg)![Example of the Opportunity Support Flow steps and transitions once the complaint is registered](user/img/sales/opportunities/wf_steps_2.jpg)![Example of the closed Opportunity Support Flow](user/img/sales/opportunities/wf_steps_3.jpg)

<a id="mc-sales-opportunities-quote"></a>

## OroCommerce Opportunity Flow (Create a Quote from an Opportunity)

OroCommerce Opportunity Flow enables sales reps to create <a href="https://www.oroinc.com/doc/orocommerce/current/user-guide/quotes" target="_blank">quotes</a> directly from the opportunity page. All quotes created within a specific opportunity are displayed in the corresponding section of its  page. The sales rep can manage quotes from this table in the same way they can manage them from the quotes table (e.g. edit or delete).

#### NOTE
Creating a quote from the opportunity page is only available if the opportunity is related to a Commerce customer. Otherwise, the workflow will behave exactly like the standard Opportunity Management flow (for standard flow, see the [Manage Opportunity Workflow]() section of the guide).

When OroCommerce Opportunity flow is activated in **System > Workflows** and an opportunity is related to a Commerce customer, the **Create Quote** button appears on the top right of the opportunity page.

#### NOTE
Creating a quote from the opportunity page is only available for **open** opportunities, i.e. not closed or lost.

![OroCommerce opportunity flow grid](user/img/sales/opportunities/commerce_flow.png)![Creating a quote from opportunity view page](user/img/sales/opportunities/create_quote.png)

Click **Create Quote** to start creating a new quote.

When a quote is created and saved, the following information appears on the opportunity page:

- A **Quote Created** note next to the OroCommerce Opportunity Flow name.
- A **Quotes** section with details of the created quote.

From the opportunity page, the following actions are possible for the quote:

- View: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
- Edit: <i class="fa fa-edit fa-lg" aria-hidden="true"></i>
- Delete: <i class="fas fa-trash-alt" aria-hidden="true"></i>
- Expire: <i class="far fa-clock" aria-hidden="true"></i>

#### NOTE
Note that availability of the **Expire** option for a quote within the opportunity page depends on the types of workflows activated in your system.

![A quote created from an opportunity](user/img/sales/opportunities/quote_created_opp.png)

On the Quote page, the relation to the opportunity (which this quote has been created from) remains, as illustrated in the following screenshot:

![Relation between the quote and opportunity on quote page](user/img/sales/opportunities/quote_opp.png)![Relation between the quote and opportunity on quote page](user/img/sales/opportunities/quote_opp_edit.png)

#### NOTE
Although opportunity relation can be displayed on the quote page, it is not possible to manage it. When there is no opportunity relation available for a quote, inactive **Opportunity** field is displayed.

You can create any number of quotes for one open opportunity.

<!-- finish_opportunity_flows -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
