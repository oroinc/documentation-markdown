<a id="user-guide-sales-seller-registration-requests"></a>

# Manage Seller Registration Requests in the Back-Office

#### HINT
This section is part of the [OroMarketplace Concept Guide](../../../concept-guides/business-models/marketplace/index.md#concept-guide-oro-marketplace) that provides a general understanding of the marketplace features and concepts.

Merchants looking to sell their products online via OroMarketplace can submit an online registration form on the OroMarketplace website. Once the form is submitted, the details of the application are synchronized with the OroMarketplace back-office. A person responsible for processing seller registration requests in the marketplace owner organization can then start processing the request, accept it straight away, or decline it. They can also create a new request via the back-office of the (global) marketplace owner organization, as long as they have obtained the necessary details from the seller.

#### HINT
Before you work with seller regsitration requests, make sure they are [enabled in the application](../../system/configuration/commerce/marketplace/marketplace-general.md#configuration-commerce-marketplace-seller-global).

## Create a Seller Registration Request

To create a new seller registration request:

1. Navigate to **Sales > Seller Registration Requests** in the back-office.
2. Click **Create Seller Registration Request** on the top right.

![Create a new seller registration request button](user/img/sales/seller-registration-requests/create-seller-registration-request.png)
1. In the **General** section, provide the following mandatory information:
   * **Owner** — The owner of the seller registration request record.
   * **First Name** — The first name of the seller.
   * **Last Name** — The last name of the seller
   * **Organization Name** — The organization name of the seller.
   * **Business Name** — The business email address of the seller.
   * **Business Phone Number** — The business phone number of the seller.

![Create form for a new seller registration request](user/img/sales/seller-registration-requests/create-seller-registration-request-form.png)
1. Click **Save and Close**.

Once the request is saved, the person responsible for handling them can progress it through the steps of the [Seller Registration Workflow](../../system/workflows/system-workflows/seller-registration-flow.md#system-workflows-seller-registration-flow).

## Manage a Seller Registration Request

You can perform the following actions for requests from the grid:

* Delete <i class="fas fa-trash-alt" aria-hidden="true"></i>
* Edit <i class="fa fa-edit fa-lg" aria-hidden="true"></i>
* View <i class="fa fa-eye fa-lg" aria-hidden="true"></i>

![Grid actions for seller registration requests](user/img/sales/seller-registration-requests/grid-actions-seller-request.png)

Two grid views are available for seller registration requests: **Open Seller Registration Requests** and **All Seller Registration Requests**. You can filter the grid with all requests and then save the filtered page as another grid view.

![Illustration of how to add a new grid page.](user/img/sales/seller-registration-requests/new-grid-for-seller-request.png)

On the view page of a request, you can transition it through the steps of the [Seller Registration Workflow](../../system/workflows/system-workflows/seller-registration-flow.md#system-workflows-seller-registration-flow), and perform the following actions:

* Edit
* Delete
* Log Call
* Add Task
* Send Mail
* Add Note
* Add Event

For more information, see [Information Management](../../getting-started/information-management/index.md#user-guide-data-management-basics-entities).

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->![Action available for a seller registration request from its view page](user/img/sales/seller-registration-requests/request-view-page.png)
