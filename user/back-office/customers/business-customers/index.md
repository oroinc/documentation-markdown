<a id="user-guide-system-channel-entities-business-customer"></a>

# Manage Business Customers in the Back-Office

Business customers represent a point of contact in your sales and business activities. With the help of Business Customers, you can track activities and records associated with them across different channels.

You can create a **Business Customer** record for each customer involved in the business-to-business activity.

<a id="user-guide-customers-create"></a>

## Enable Business Customers

Enable business customers in your Oro application via a sales channel:

1. Navigate to **System > Channels** in the main menu.
2. Click **Create Channel**.
3. Once the form opens:
   * Select a meaningful name for the channel.
   * Set the channel type to **Sales**
   * In the **Entities** section, select **Business Customer** from the list and click **Add**.
4. Click **Save and Close**.

## Create a Business Customer

To create a new business customer:

1. Navigate to **Customers > Business Customers** in the main menu.
2. Click **Create Business Customer**.
3. Provide the following information:
   * **Owner** — Limits the list of users that can manage the customer to users whose [roles](../../system/user-management/roles/index.md#user-guide-user-management-permissions) allow managing business customers assigned to the owner (e.g., the owner, members of the same business unit, system administrator, etc.). By default, the user creating the record is chosen.
   * **Name** — The name used to refer to the business customer in the system.
   * **Channel** — Choose one of the active sales channels, from which your Oro application will get information on this customer.
   * **Account** — An [account](../accounts/create.md#user-guide-accounts-create) to which the customer will be assigned. Details of this business customer will then be part of this account’s details.

   The rest of the fields are **optional**. The fields are added to the system based on general B2B practices, aims, and processes and keep additional details of the customer. The optional fields may be left empty.
   <!-- If you need to collect and process any other details of business customers, :ref:`custom fields can be created <doc-entity-fields-create>`. Their values will be displayed in the **Additional** section. -->
4. Click **Save and Close**.

<a id="user-guide-customers-actions"></a>

## Manage Business Customers

The following actions can be performed with business customer records:

**From the business customers grid**:

1. Delete ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg)
2. Edit <i class="fa fa-edit fa-lg" aria-hidden="true"></i>
3. View <i class="fa fa-eye fa-lg" aria-hidden="true"></i>

![The actions available for the business customer from the grid, such as view, edit, and delete.](user/img/customers/business_customers/customers_grid.png)

**From the view page of a specific business customer**:

1. Get to the Edit page.
2. Delete the customer from the application.
3. Perform actions from the **More Actions** menu (e.g., send an email, log a call).

<!-- The other available actions depend on the system settings defined in the  **Communication &  Collaboration** section of the **Business Customer** entity configuration. See step 4 of the :ref:`Create an Entity <doc-entity-actions-create>` action description. -->![The page of a specific business customer](user/img/customers/business_customers/business_customers_viewpage.png)
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

* [Export Business Customers](export.md)
* [Import Business Customers](import.md)
