<a id="system-workflows-alternative-checkout-workflow"></a>

# Configure Alternative Checkout Workflow in the Back-Office

#### NOTE
The alternative checkout workflow is available as a <a href="https://github.com/oroinc/commerce-demo-checkouts" target="_blank">demo extension</a> and should be installed separately.

The Alternative Checkout workflow represents an **example** of the [checkout workflow](checkout.md#system-workflows-checkout-workflow) customization. It is a [system workflow](../index.md#user-guide-system-workflow-management-system-custom) that defines the sequence of [steps and transitions](../steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that a user can go through when creating an order in the storefront.

In addition to the standard [checkout steps](checkout.md#system-workflows-checkout-workflow), alternative checkout workflow includes request and order approval steps before creating an order. For this workflow, orders with subtotals exceeding the specified value will have to be reviewed and approved by users with the permission to *approve orders that exceed the allowable amount*. By default, the order approval threshold is set to 5000.

#### NOTE
Please keep in mind that the default alternative checkout is merely an example of an alternative checkout workflow. Enabling it for your customer users in the OroCommerce storefront requires some customization efforts. To test the alternative checkout workflow on the demo website (or locally with installed demo data), you may be required to create an order and approve it under two different demo users: under Marlene S Bradley to create an order that requires manager approval and Nancy Sallee to approve the order as the manager. You can also test the flow under customer users who belong to a customer with ID 4 (customer_id=4).

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.

   Within the Workflows grid, you can perform the following actions for the alternative checkout workflow:
   * Configure order approval threshold: <i class="fas fa-cog" aria-hidden="true"></i>
   * View the workflow: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
   * Deactivate the workflow: <i class="fa fa-times fa-lg" aria-hidden="true"></i>

   ![image](user/img/system/workflows/alternative_checkout/ACF_grid.png)
2. Click **Alternative Checkout** to open the flow.

   On the Alternative Checkout workflow page, you can perform the following actions:
   * Configure order approval threshold: <i class="fas fa-cog" aria-hidden="true"></i> **Configuration**.
     ![image](user/img/system/workflows/alternative_checkout/ACF_configuration.png)
   * Deactivate the workflow - click <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** to deactivate the workflow.
     ![image](user/img/system/workflows/alternative_checkout/ACF_page.png)

## Steps and Transitions: Illustration

As an illustration, we are going to proceed through the steps of the Alternative Checkout workflow in the default OroCommerce storefront.

Several items have been added to a shopping list in the OroCommerce storefront. To proceed to the checkout, click **Create Order** on the bottom right of the shopping list page.

![Shopping list with option to create order and proceed to checkout](user/img/system/workflows/alternative_checkout/ACF_CreateOrderButton.png)

#### NOTE
The **Create Order** button is available if the following conditions are met:

* At least one [shipping method](../../../../concept-guides/shipping-configuration/index.md#user-guide-shipping) is available
* At least one [payment method](../../../../concept-guides/payment-configuration/index.md#user-guide-payment) is available
* There is at least one product with a price in the shopping list
* Items to be purchased are available in the [inventory](../../../inventory/index.md#user-guide-inventory) in the back-office

A warning message is shown if for some reason you are unable to start the checkout process.

<!-- check the conditions -->

### Step 1: Agreements

At the Agreements step, you are required to accept all mandatory consents to process your personal data, if such consents have not been accepted previously. Keep in mind that if you leave the checkout after accepting a mandatory consent, this consent is considered accepted and can be revoked only through the [profile management](../../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents-revoke).

> ![The first step of the checkout is agreements where you are required to accept any available mandatory consents](user/img/system/workflows/alternative_checkout/storefront_step_agreements_bluethooth.png)

Once the consent is accepted, click **Continue** to proceed through the checkout.

### Step 2: Billing Information

The checkout is now open. The next step is to enter billing information for the order by selecting an existing address from the address book, or creating a new one.

Checking **Ship to this address** allows you to use the provided billing address as shipping.

Clicking **Continue** redirects you to the next step.

#### NOTE
You can edit *the already provided* information (until the order is submitted) by clicking <i class="fas fa-pencil-alt" aria-hidden="true"></i> on the left side of the page.

![The billing information step at the checkout (alternative checkout)](user/img/system/workflows/alternative_checkout/ACF_CreateBilling.png)

### Step 3: Shipping Information

If the **Ship to this address** box has been checked at the Billing Information step, the provided address is automatically selected at the Shipping Information step.

To edit shipping information, clear the **Use billing address** box and provide a different shipping address for the order.

![image](user/img/system/workflows/alternative_checkout/ACF_CreateShipping.png)

### Step 4: Shipping Method

Provide a [shipping method](../../../../concept-guides/shipping-configuration/index.md#user-guide-shipping) by selecting one from the list of the available methods.

![The shipping method step at the checkout (alternative checkout)](user/img/system/workflows/alternative_checkout/ACF_ShippingMethod.png)

### Step 5: Payment

Choose a suitable [payment method](../../../../concept-guides/payment-configuration/index.md#user-guide-payment) by selecting it from the list of all available methods.

![The payment method step at the checkout (alternative checkout)](user/img/system/workflows/alternative_checkout/ACF_Payment.png)

### Step 6: Order Review

Once all the necessary information has been provided, you can review the order at the **Order Review** step:

* View Options for the order:
  * Do not ship later than
  * PO Number
  * Notes
  * Delete the shopping list
* Check quantity, price, subtotal, shipping and total cost
* Edit the Order
* Edit the already provided information by clicking <i class="fas fa-pencil-alt" aria-hidden="true"></i> on the left side of the page

To submit the order, click **Submit Order** at the bottom of the page.

![The page of the order in the back-office, once the order is submitted](user/img/system/workflows/alternative_checkout/ACF_OrderReview.png)

### Step 7: Request Approval

Since the order amount exceeds the threshold of $5000, manager approval is required to submit the order.

![image](user/img/system/workflows/alternative_checkout/ACF_RequestApproval.png)

Order Approval will remain pending until the manager approves it.

![image](user/img/system/workflows/alternative_checkout/ACF_ApprovalPending.png)
<!-- comment: currently alternative checkout wf works with customer users under customer with ID 4 -->

### Step 8: Approve Order

The manager can approve the order by navigating to Orders, selecting the required order and clicking **Approve Order**.
At this point, the manager can submit the order themselves, or let the employee handle the order:

![image](user/img/system/workflows/alternative_checkout/ACF_ApproveOrder.png)

Once submitted, the order will be received and dealt with by the sales team.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
