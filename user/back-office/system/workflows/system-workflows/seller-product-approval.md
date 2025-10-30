<a id="system-workflows-seller-product-approval-workflow"></a>

# Configure Seller Product Approval Workflow in the Back-Office

#### HINT
The workflow is only available in the Enterprise edition of the Oro application starting from v5.1.2. It requires an extension, so visit Oro Extensions Store to download the <a href="https://extensions.oroinc.com/orocommerce/extension/seller-product-approval-workflow/" target="_blank">Seller Product Approval workflow extension</a> and then use the composer to [install the extension to your application](../../../../../backend/extension/install-extension.md#cookbook-extensions-composer).

The Seller Product Approval workflow is a powerful tool that enables global administrators to manage the review and publication of products from non-global organizations. Once the workflow extension is installed, it is initially disabled.

To enable the workflow, the global administrator needs to:

1. Navigate to **System > Workflows** in the main menu.
2. Activate the Seller Product Approval workflow by clicking <i class="fa fa-check fa-lg" aria-hidden="true"></i> at the end of the row. Or click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> to view the workflow’s details.

![Seller Product approval flow under the Workflow menu](user/img/system/workflows/seller-product-approval/enable-seller-product-flow.png)

Seller Product Approval workflow is a system workflow, which means it cannot be edited, only deactivated.

## Workflow Steps and Transitions

**Draft**

Products created outside the global organization are *Disabled* by default and have the workflow in **Draft** status. In this status, users can edit products and submit them for approval by the global administrator.

![Newly created product is in Draft workflow status](user/img/system/workflows/seller-product-approval/seller-product-flow-draft.png)

**Waiting for Approval**

When a product is submitted for approval, it still has a *Disabled* status and a workflow status of **Waiting for Approval**. In this status, the global administrator, a user working within the global organization, can either approve or reject the product. Users can also add notes for the reviewer while sending the approval request. Once the request is sent, an email with a link to the product will be sent to the administrator for review. If users leave review comments, those comments will also be sent to the same email.

If a user in a regular organization needs to make any changes, they can cancel the approval request and continue editing the product.

![Display how the seller product approval workflow status changes after the user sends the request to approve the product creation](user/img/system/workflows/seller-product-approval/seller-product-flow-send-for-approval.png)

**Approved**

If the reviewer finds the product satisfactory and approves it, the product’s status changes to *Enabled*, and its workflow status becomes **Approved**. Depending on the [configuration parameter](../../configuration/commerce/product/seller-product-approval-flow.md#system-configuration-commerce-product-seller-product-approval-workflow), an email notification will be sent either to the business unit that owns the product or to the user who requested the approval.

![Display how the seller product approval workflow status changes after the admin approves the product creation](user/img/system/workflows/seller-product-approval/seller-product-flow-approved.png)

**Rejected**

If the reviewer decides to reject the product, it will be marked as *Disabled*, and the workflow status will be updated to **Rejected**. The reviewer can provide notes explaining the reason for the rejection. An email, containing the rejection comments left by the reviewer, will be sent to either the product’s owning business unit or the user who submitted the product, depending on the [configuration parameter](../../configuration/commerce/product/seller-product-approval-flow.md#system-configuration-commerce-product-seller-product-approval-workflow).

![Display how the seller product approval workflow status changes after the admin rejects the product creation](user/img/system/workflows/seller-product-approval/seller-product-flow-rejected.png)

**Requesting Changes**

After a product has been approved, the user can request changes by sending a list of desired changes to the reviewer. An email containing the list of changes will be sent to the reviewer. Statuses remain unchanged.

![Possibility for the user to request changes for the approved product](user/img/system/workflows/seller-product-approval/seller-product-flow-request-change.png)

## Global Organization Products

Products created within the global organization are exempt from this workflow and have their status field **Enabled** for editing.

![Products created under the global organization do not have the seller product approval workflow and can be edited](user/img/system/workflows/seller-product-approval/seller-product-flow-global-product.png)

**Related Topics**

* [Configure Global Seller Product Approval Workflow Settings](../../configuration/commerce/product/seller-product-approval-flow.md#system-configuration-commerce-product-seller-product-approval-workflow)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
