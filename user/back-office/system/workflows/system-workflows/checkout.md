<a id="system-workflows-checkout-workflow"></a>

# Configure Checkout Workflow in the Back-Office

#### HINT
This section is part of the [Checkout Configuration Concept Guide](../../../../concept-guides/administration/checkout/index.md#checkout-management-concept-guide) topic that provides a general understanding of single-page and multi-page checkout concepts.

## Overview

The Checkout workflow represents a standard checkout procedure in the eCommerce environment. It is a [system workflow](../index.md#user-guide-system-workflow-management-system-custom) that defines the sequence of [steps and transitions](../steps-transitions.md#user-guide-system-workflow-management-steps-transitions) that a user can go through when creating an order in the storefront.

To reach the workflow:

1. Navigate to **System > Workflows** in the main menu.

   On the page of all workflows, you can perform the following actions for the Checkout workflow:
   * View the workflow: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>
   * Deactivate / Activate the workflow: <i class="fa fa-times fa-lg" aria-hidden="true"></i> / <i class="fa fa-check fa-lg" aria-hidden="true"></i>

   ![image](user/img/system/workflows/checkout/CheckoutGridBackoffice.png)
2. Click **Checkout** to open the flow.

   On the Checkout workflow page, you can perform the following actions:
   * Deactivate the workflow - click <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** to deactivate the workflow.
   * Activate the workflow - click <i class="fa fa-check fa-lg" aria-hidden="true"></i> **Activate** to activate the workflow.

   ![image](user/img/system/workflows/checkout/CheckoutViewPageBackoffice.png)

## Steps and Transitions: Illustration

As an illustration, we are going to proceed through the steps of the Checkout workflow in the default OroCommerce storefront.

<!-- start_checkout_sample_0 -->

Several items have been added to a shopping list in the OroCommerce storefront. To proceed to the checkout, click **Create Order**.

![Shopping list with option to create order and proceed to checkout](user/img/system/workflows/checkout/CreateOrderButton.png)

#### NOTE
The **Create Order** button is available if the following conditions are met:

* At least one [shipping method](../../../../concept-guides/administration/shipping-configuration/index.md#user-guide-shipping) is available
* At least one [payment method](../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment) is available
* There is at least one product with a price in the shopping list
* Items to be purchased are available in the [inventory](../../../inventory/index.md#user-guide-inventory) in the back-office

A warning message is shown if for some reason you are unable to start the checkout process.

<!-- finish_checkout_sample_0 -->

### Step 1: Agreements

At the Agreements step, you are required to accept all mandatory [consents](../../consent-management/index.md#system-consent-management) to process your personal data, if such consents have not been accepted previously. Keep in mind that if you leave the checkout after accepting a mandatory consent, this consent is considered accepted and can be revoked only through the [profile management](../../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents-revoke).

#### IMPORTANT
Keep in mind that for the Agreements section to be displayed in the checkout, you need to [add the necessary consents to the list of enabled consents](../../configuration/commerce/customer/global-consents.md#admin-guide-commerce-configuration-customers-consents-enable-globally) in the system configuration.

![The first step of the checkout is agreements where you are required to accept any available mandatory consents](user/img/system/workflows/checkout_with_consents/storefront_step_agreements.png)![Accept a mandatory consent on the agreements step at checkout](user/img/system/workflows/checkout_with_consents/storefront_step_accept_agreement.png)

Once the consent is accepted, click **Continue** to proceed with the checkout.

### Step 2: Billing Information

<!-- start_checkout_sample_1 -->

The checkout is now open. The next step is to enter billing information for the order by selecting an existing address from the address book, or creating a new one.

Checking **Ship to this address** allows you to use the provided billing address as shipping.

Clicking **Continue** redirects you to the next step.

#### NOTE
You can edit *the already provided* information (until the order is submitted) by clicking <i class="fas fa-pencil-alt" aria-hidden="true"></i> on the left side of the page.

<!-- finish_checkout_sample_1 -->![The billing information step at the checkout (with consents)](user/img/system/workflows/checkout_with_consents/Checkout_BilInfo.png)

### Step 3: Shipping Information

<!-- start_checkout_sample_2 -->

If the **Ship to this address** box has been checked at the Billing Information step, the provided address is automatically selected at the Shipping Information step.

To edit shipping information, clear the **Use billing address** box and provide a different shipping address for the order.

<!-- finish_checkout_sample_2 -->![image](user/img/system/workflows/checkout_with_consents/UseBillingAddressBox.png)

### Step 4: Shipping Method

<!-- start_checkout_sample_3 -->

Provide a [shipping method](../../../../concept-guides/administration/shipping-configuration/index.md#user-guide-shipping) by selecting one from the list of the available methods.

<!-- finish_checkout_sample_3 -->![The shipping method step at the checkout](user/img/system/workflows/checkout_with_consents/Shipping_Info.png)

### Step 5: Payment

<!-- start_checkout_sample_4 -->

Choose a suitable [payment method](../../../../concept-guides/administration/payment-configuration/index.md#user-guide-payment) by selecting it from the list of all available methods.

<!-- finish_checkout_sample_4 -->![The payment method step at the checkout](user/img/system/workflows/checkout_with_consents/Payment.png)

### Step 6: Order Review

<!-- start_checkout_sample_5 -->
<!-- start_checkout_sample_alt5 -->

Once all the necessary information has been provided, you can review the order at the **Order Review** step:

* View Options for the order:
  * Do not ship later than
  * PO Number
  * Notes
  * Delete the shopping list
* Check quantity, price, subtotal, shipping and total cost
* Edit the Order
* Edit the already provided information by clicking <i class="fas fa-pencil-alt" aria-hidden="true"></i> on the left side of the page

To submit the order, click **Submit Order**.

<!-- finish_checkout_sample_alt5 -->

Once submitted, the order will be received and dealt with by the sales team.

<!-- finish_checkout_sample_5 -->

#### BUSINESS TIP
### Business Tip

Explore our guide to discover how <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a> improves operations, customer experiences, and increases sales.

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
