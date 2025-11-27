<a id="frontstore-guide-cim"></a>

# Manage Payment Profiles (Authorize.Net Customer Profiles) in the Storefront

When checking out using a credit card or <a href="https://www.authorize.Net/payments/echeck/" target="_blank">eCheck</a>, a customer is presented with the option to store the payment method for future use. This information is stored in your OroCommerce account as an Authorize.Net customer profile. A customer who has a previously saved profile is presented with the option for seamless subsequent checkouts without having to re-enter their payment data. Once you log into your account in the OroCommerce storefront, you can view and manage payment and address information stored within Customer Profiles, as well as add new credit cards and bank accounts.

To locate the information in your customer profile, navigate to **Account > Manage Payment Profiles**.

![Manage Customer Payment Information section in the storefront account](user/img/storefront/cim/manage_payment_profiles.png)

The Manage Payment Profiles page displays all available payment profiles, both for credit cards and bank accounts.

#### NOTE
Up to 10 payment profiles can be saved in your OroCommerce account.

## Add a New Credit Card

**Via your customer profile:**

To create a new credit card payment profile:

1. On the Manage Payment Profiles page, click **+Add New Credit Card** on the right.
2. In the **New Payment Profile** form, provide the following details:
   ![Add a new credit card payment profile](user/img/storefront/cim/add_new_credit_card.png)
   * **Name** — Provide the name for the account.
   * **Credit Card Number** — Provide the card number (without spaces).
   * **Expiration Date** — Provide the expiration date for the card you are attaching to the account.
   * **CVV** — Provide the verification number displayed at the back of the card.
   * **Address** — Provide billing address details (organization, phone and fax fields are optional).
   * **Set as Default** — Select the checkbox to mark the current credit card as default. The default credit card is displayed on the top of the payment method dropdown list during checkout.
3. Click **Save**.

When proceeding through the checkout, you are now able to select the newly created credit card at the Payment step.

![New credit card selected as a payment method at checkout](user/img/storefront/cim/new_credit_card_at_checkout.png)

**At checkout**:

To add a new card during the checkout:

1. Scroll down to the bottom of the Profile list and click **New Card**.
   ![New credit card added as a payment method at checkout](user/img/storefront/cim/add_new_card_at_checkout.png)
2. Provide the details of the new card in the form:
   ![New credit card form at checkout](user/img/storefront/cim/new_card_at_checkout_form.png)
3. To save the details of the card for the future use, select the **Save Payment Details** checkbox.
   ![Credit card form filled in during checkout](user/img/storefront/cim/card_form_fillied_in_checkout.png)

   When you place the order, this card is saved in your account in the **Manage Payment Profiles** section as a non-default card.
   ![New credit card created at checkout is saved in the customer profile](user/img/storefront/cim/new_card_from_checkou_saved_to_account.png)

### Manage a Credit Card Profile

* To edit a credit card, click <i class="fas fa-pencil-alt" aria-hidden="true"></i> **Edit** at the end of the row of the selected profile.
  ![Edit payment profile info](user/img/storefront/cim/update_payment_profile.png)

  To update card information, select the **Update Credit Card Information** checkbox and provide new information in the credit card form.
  ![Update credit card payment details](user/img/storefront/cim/update_credit_card_info.png)
* To delete credit card, click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** at the end of the row of the selected profile. Click **Yes** in the confirmation dialog.
  ![Delete a credit card profile](user/img/storefront/cim/delete_credit_card.png)

## Add a New Bank Account

**Via your customer profile:**

To create a new back account profile:

1. On the Manage Payment Profiles page, click **+Add New Bank Account**
2. In the **New Payment Profile** form, provide the following details:
   > ![Add a new bank account payment profile](user/img/storefront/cim/bank_account_new.png)
   * **Name** — Provide the name for the bank account.
   * **Bank Account** — Provide bank account details, such as the routing number, the account number, the bank name.
   * **Address** — Provide address details (organization, phone and fax fields are optional).
   * **Set as Default** — Select the checkbox to mark the current bank account as default. The default bank account is displayed on the top of the payment method dropdown list during checkout.
3. Click **Save**.

When proceeding through the checkout, you are now able to select the newly created bank account at the Payment step.

![New bank account selected as a payment method at checkout](user/img/storefront/cim/new_bank_account_at_checkout.png)

**At checkout**:

To add a new bank account during checkout:

1. Scroll down to the bottom of the Profile list and click **New Bank Account**.
   ![New bank account added as a payment method at checkout](user/img/storefront/cim/add_new_bank_acc_at_checkout.png)
2. Provide the details of the new bank account in the form.
3. To save the details of the bank account for the future use, select the **Save Payment Details** checkbox.
   > ![New bank account form at checkout](user/img/storefront/cim/new_acc_at_checkout_form.png)

   When you place the order, this bank account is saved in your account in the **Manage Payment Profiles** section as a non-default bank account.

   #### WARNING
   Keep in mind that payment details of a new bank account must not duplicate the information of the saved accounts as in this case a new profile will not be created.

### Manage a Bank Account

* To edit a bank account, click <i class="fas fa-pencil-alt" aria-hidden="true"></i> **Edit** at the end of the row of the selected profile.
  ![Edit bank account payment profile info](user/img/storefront/cim/update_bank_acc_profile.png)

  To update card information, select the **Update Bank Account Information** checkbox and provide new information in the bank account form.
  ![Update bank account payment details](user/img/storefront/cim/update_bank_acc_info.png)
* To delete a bank account, click <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** at the end of the row of the selected profile. Click **Yes** in the confirmation dialog.
  ![Delete a bank account profile](user/img/storefront/cim/delete_bank_acc.png)

## Payment Profiles on the Authorize.Net Side

All credit card and bank account payment profiles are synchronized with Authorize.Net as soon as they are added or modified on the OroCommerce side. You can access all payment details in your Customer Profile on the Authorize.Net side where you can charge or refund a transaction for your profile ID.

![Credit card details on the authorize.Net side](user/img/storefront/cim/credit_card_details_authorize_side.png)

#### NOTE
If you edit or delete a payment profile on the Authorize.Net side, these changes will be reflected in your OroCommerce account. Keep in mind, however, that payment profiles created in Authorize.Net are not synced back to OroCommerce.

**Related Topics**

* [Set Up Authorize.Net Integration in the Back-Office](../../../back-office/system/integrations/payment-integration/authorizenet/authorizenet-integration.md#user-guide-payment-configuration-payment-method-integration-authorizenet-details)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
