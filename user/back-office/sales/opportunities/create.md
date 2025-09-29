<a id="user-guide-opportunities-create"></a>

<a id="user-guide-system-channel-entities-opportunities-create-intro"></a>

# Create an Opportunity

Opportunities can be related to any customer type and customers introduced by various third-party extensions. They can also be related directly to accounts. This is the simplest application setup if you do not need to track multi-channel sales. You can always enable the additional complexity of multiple customer channels when the need arises.

<!-- Business customers will remain available as legacy for users who upgrade from OroCRM 1.10 edition but will be deprecated in OroCRM 2.0. -->

You can create opportunities from all related entities (e.g., from [OroCommerce customer](#user-guide-opportunities-create-from-orocommerce-customer), [account](#user-guide-opportunities-create-from-account)), [by converting a lead to an opportunity](#user-guide-opportunities-create-convert-lead-to-opportunity) and [by creating an opportunity manually](#user-guide-opportunities-create-create-manually).

## Create an Opportunity from a Related Entity

<a id="user-guide-opportunities-create-from-orocommerce-customer"></a>

### OroCommerce Customer

To create an opportunity from a Commerce customer view page, make sure you have the CRM features enabled in the system configuration.

1. Navigate to **Customers** in the main menu, click **Commerce Customers**.
2. Select your customer and open their view page.
3. Click **More Actions** in the top right corner.
4. Click Create Opportunity in the drop down.
5. A **Create Opportunity form** will open with an **Account** field pre-filled in with your selected Commerce customer.
   ![Create an opportunity from a commerce customer](user/img/sales/opportunities/commerce_customer_create_opp.jpg)![Account field predefined with commerce customer info](user/img/sales/opportunities/commerce_opportunity_form.jpg)

<a id="user-guide-opportunities-create-from-account"></a>

### Account

To create an opportunity directly from an account view page:

1. Navigate to **Customers > Accounts** in the main menu.
2. Click on the required account in the grid.
3. Navigate to **More Actions** in the top right corner.
4. Select **Create Opportunity** from the list.
5. A **Create Opportunity form** will open with an **Account** field already filled in with your selected account.
   ![Create an opportunity from an account](user/img/sales/opportunities/account_opportunity.jpg)![Account field predefined with account info](user/img/sales/opportunities/account_opp_form.jpg)

<a id="user-guide-opportunities-create-convert-lead-to-opportunity"></a>

<a id="user-guide-opportunities-create-convert-form"></a>

## Convert a Lead to Opportunity

As soon as a lead is ready to be qualified, it can be converted into an opportunity:

1. Navigate to **Sales > Leads** in the main menu.
2. Open the lead from the grid.
3. Click **Convert Lead to Opportunity** on the lead page.
   ![Convert lead to opportunity button](user/img/sales/opportunities/convert_to_opportunity_button.png)
4. Provide details in the **Opportunity Information** section.
   ![Convert to opportunity form](user/img/sales/opportunities/convert_to_opportunity_2.0.jpg)
   * **Owner** — Limits the list of users who can manage the opportunity to users, whose roles allow managing opportunities assigned to the owner (e.g. the owner, members of the same business unit, system administrator, etc.). By default, the user creating the record is chosen.
   * **Opportunity Name** — The name used to refer to an opportunity in the system.
   * **Account** — Allows to select or create a customer account the opportunity will be related to.
     > * Account field will be filled in with the company name if such name was entered when creating a lead.
     > * To create a new account, click **+** at the end of the Account field.
     > * Alternatively, use write-in functionality to enter a new account name. Type the name in the field and click **Add New Account**.
   * **Contact** — The person on the customer side who is directly related to the opportunity.
   * **Status** — A stage in the process of a sale. **Open**, **Closed Won** and **Closed Lost** are system statuses that cannot be deleted.  Other statuses can be added and customized in the system configuration settings by an admin.
   * **Probability** — The perceived probability of an opportunity being successfully closed. Probability is related to **Status**. For each status, there is a certain percentage of probability which is pre-configured automatically. You can configure percentage for each status in the [system configuration](../../system/configuration/crm/sales-pipeline/opportunities.md#sys-configuration-crm-sales-pipeline-opportunities).
   * **Budget Amount** — Budget amount is potential deal value being discussed. For OroCRM Enterprise Edition, you can select the currency of the deal. The currencies available in the dropdown will depend on your system configuration. You can find more on multi-currency functionality further below this guide.
   * **Expected Close Date** — Expected close date of the deal.
   * **Close Revenue** — The amount actually received as the result of the deal.For example, if the predicted budget was $10 000 but the result of the deal was $500 lower than the budget amount, the close revenue would constitute $9 500.
   * **Close Reason** — The reason for closing the deal, e.g. won, outsold, cancelled, etc.
   * **Customer Need** — Enter customer needs if known.
   * **Proposed Solution** — Enter your offers and/or solutions for the customer if any were proposed.
   * **Additional comments** — Enter additional comments if necessary.
5. Provide the details in the **New Contact Information** section. Since the lead has fulfilled its purpose and is no longer needed, a new contact will be created based on lead data entered in this form. It is possible to enter multiple phones, emails and addresses for an opportunity. You can choose which phone, email or address is to be primary. You can also delete the entered phone, email or address by clicking X on the right of the corresponding fields.

   #### NOTE
   Within the opportunity grid, only one phone, email and address will be displayed even if multiple phones, emails and addresses are added.
6. Click **Save and Close** to save the opportunity.

See more information in the [Lead Qualification topic](../leads/index.md#user-guide-system-channel-entities-leads).

<a id="user-guide-opportunities-create-create-manually"></a>

<a id="user-guide-opportunities-create-create-form"></a>

## Create an Opportunity Manually

To create an opportunity manually:

1. Navigate to **Sales > Opportunities** in the main menu.
2. Click **Create Opportunity** in the top right corner.
3. Provide the following information:
   ![Create opportunity form](user/img/sales/opportunities/create_opp_new.jpg)

> * **Owner** — Limits the list of users who can manage the opportunity to users, whose roles allow managing opportunities assigned to the owner (e.g. the owner, members of the same business unit, system administrator, etc.). By default, the user creating the record is chosen.
> * **Opportunity Name** — The name used to refer to an opportunity in the system.
> * **Account** — Allows to select or create a customer account the opportunity will be related to.
>   > * Account field will be filled in with the company name if such name was entered when creating a lead.
>   > * To create a new account, click **+** at the end of the Account field.
>   > * Alternatively, use write-in functionality to enter a new account name. Type the name in the field and click **Add New Account**.
> * **Contact** — The person on the customer side who is directly related to the opportunity.
> * **Status** — A stage in the process of a sale. **Open**, **Closed Won** and **Closed Lost** are system statuses that cannot be deleted.  Other statuses can be added and customized in the system configuration settings by an admin.
>   ![Opportunity status dropdown](user/img/sales/opportunities/status.jpg)
> * **Probability** — The perceived probability of an opportunity being successfully closed. Probability is related to **Status**. For each status, there is a certain percentage of probability which is pre-configured automatically. You can configure percentage for each status in the [system configuration](../../system/configuration/crm/sales-pipeline/opportunities.md#sys-configuration-crm-sales-pipeline-opportunities).
> * **Budget Amount** — Budget amount is potential deal value being discussed. For OroCRM Enterprise Edition, you can select the currency of the deal. The currencies available in the dropdown will depend on your system configuration. You can find more on multi-currency functionality further below this guide.
> * **Expected Close Date** — Expected close date of the deal.
> * **Close Revenue** — The amount actually received as the result of the deal.For example, if the predicted budget was $10 000 but the result of the deal was $500 lower than the budget amount, the close revenue would constitute $9 500.
> * **CLose Reason** — The reason for closing the deal, e.g. won, outsold, cancelled, etc.
> * **Customer Need** — Enter customer needs if known.
> * **Proposed Solution** — Enter your offers and/or solutions for the customer if any were proposed.
> * **Additional comments** — Enter additional comments if necessary.
