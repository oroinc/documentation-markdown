<a id="system-workflows-single-page-checkout"></a>

# Configure Single Page Checkout Workflow in the Back-Office

#### HINT
This section is part of the [Checkout Configuration Concept Guide](../../../../concept-guides/checkout/index.md#checkout-management-concept-guide) topic that provides the general understanding of single-page and multi-page checkout concepts.

## Overview

In your Oro application, you can control the way the checkout is displayed to customers in the storefront. By default, each checkout step is displayed on a new page. However, by activating the Single Page Checkout workflow in the back-office, you can make all steps fit one page. This will make the checkout process easier and quicker for customers, since they will be able to see how far along in the checkout they are, and how many fields are left to complete it.

![Illustration of single page checkout in the storefront](user/img/system/workflows/single_page_checkout/SampleFlow2.png)

To reach the Single Page Checkout workflow:

1. Navigate to **System > Workflows** in the main menu.

   Within the list of workflows, you can perform the following actions for the Single Page Checkout workflow:
   * View the workflow: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
   * Activate the workflow: <i class="fa fa-check fa-lg" aria-hidden="true"></i>
2. Click **Single Page Checkout** to open the flow.
   ![Illustration of single page checkout in the back-office](user/img/system/workflows/single_page_checkout/SPCList.png)

   #### NOTE
   If the workflow is active, you can deactivate it from the list page by clicking <i class="fa fa-times fa-lg" aria-hidden="true"></i>.

   On the Single Page Checkout workflow page, you can perform the following actions:
   * Activate — Click <i class="fa fa-check fa-lg" aria-hidden="true"></i> **Activate** on the top right of the page to activate the workflow.
   * Deactivate (if the workflow is active) – click <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** on the top right of the page to deactivate the workflow.

For more information managing workflows, see the [Workflow Management topic](../index.md#user-guide-system-workflow-management).

## Steps and Transitions: Illustration

As an illustration let us go through the sample flow to see the Single Page Checkout workflow in action:

1. Add an item to the shopping list in the storefront, and click **Create Order** to proceed to the checkout.
   ![Create an order leading to single page checkout](user/img/system/workflows/single_page_checkout/SampleFlow1.png)
2. The following sections (steps) are displayed on one page:
   * Billing Information
   * Shipping Information
   * Order Summary (including *Agreements*)

   ![Illustration of single page checkout in the storefront](user/img/system/workflows/single_page_checkout/SampleFlow2.png)
3. In the **Billing Information** section, provide your address and select a payment method.
4. In the **Shopping Information** section:
   * Provide shipping and billing addresses.
   * Select a shipping method.
   * Set the Do Not Ship Later Than date.
5. In the **Order Summary** section:
   * Review the order by checking items, SKUs, item quantity, price and the subtotal amount.
   * Check order options.
   * Select whether the shopping list should be deleted after submitting the order, or saved.
   * Accept all mandatory consents to process your personal data, if such consents have not been accepted previously. Keep in mind that if you leave the checkout after accepting a mandatory consent, this consent is considered accepted and can be revoked only through the [profile management](../../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents-revoke).
6. Submit the order by clicking **Submit Order** on the top left of the page.
7. Receive an email confirmation with order details.

**Related Topics**

* [Checkout Workflow](checkout.md#system-workflows-checkout-workflow)
* [Alternative Checkout Workflow](alternative-checkout.md#system-workflows-alternative-checkout-workflow)
* [Workflow Management topic](../index.md#user-guide-system-workflow-management)
* [Checkout Process in the Storefront](../../../../storefront/checkout/index.md#frontstore-guide-orders-checkout)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
