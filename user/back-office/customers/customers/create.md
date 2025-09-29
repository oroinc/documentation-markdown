<a id="user-guide-customers-customers-create"></a>

# Create a Customer

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-customer-record" target="_blank">how to create customers in OroCommerce</a>, or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/iLphaHiU8YY" frameborder="0" allowfullscreen></iframe>

To create a new customer:

1. Navigate to **Customers > Customers** in the main menu.
2. Click **Create Customer**.
   ![An empty form is displayed when creating a new customer](user/img/customers/customers/CustomersCreate.png)
3. Optionally, select an existing [account](../accounts/index.md#user-guide-accounts) to help track sales actions and metrics for the customer that is a member of the bigger customer organization. When it remains empty, the new account is created for the new customer automatically.
4. Fill in the customer **Name**.
5. Optionally, add a customer to a customer group if you already have a group with the settings and configuration that fits the new customer.
6. If you are adding a subsidiary of the existing customer, select **Parent Customer**.
7. Assign a sales representative who will be assisting customer users.
8. Select **Tax Code** to label the customer group taxation schema.
9. Add a billing and shipping address as described in [the address book](address-book.md#user-guide-getting-started-address-book) section.
10. In the **Additional** section, select a Payment term to be used as a payment option available to the customer users during the checkout.
11. In the **Price Lists** section, add price lists and prioritize them as described in the [Price List Management for a Customer Group](../customer-groups/index.md#user-guide-customers-customer-groups-pricelist) section.
12. When OroCommerce is deployed with InfinitePay payments support, the customer’s VAT Id shall be captured for their creditworthiness verification. VAT Id should be valid, and the billing address should match the one provided for the VAT registration. These are prerequisites to enable payments via [InfinitePay](../../system/integrations/payment-integration/infinitepay/infinitepay-prerequisites.md#user-guide-payment-prerequisites-infinitepay) for the customer users.
13. Click **Save** in the top right.

#### NOTE
Keep in mind that customers with at least one successful registered checkout cannot be deleted from the system.

![A note appears when deleting a customer warning that no entities can be deleted](user/img/customers/customers/unable_to_delete_customers.png)
