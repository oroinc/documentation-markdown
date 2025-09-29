<a id="doc-integrations-multi-shipping"></a>

# Configure Multiple Shipping Integration in the Back-Office

#### HINT
The Multiple Shipping feature is available starting from OroCommerce v5.0.8. To check which application version you are running, see the [system information](../../system-information/index.md#system-information).

#### HINT
This section is part of the [Shipping Configuration](../../../../concept-guides/shipping-configuration/index.md#admin-guide-shipping) topic that provides a general understanding of the shipping concept in OroCommerce.

To set up the multi shipping integration in OroCommerce:

1. Make sure to enable the [Multi Shipping](../../configuration/commerce/sales/global-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping) configuration option in the system configuration under **Commerce > Sales > Multi Shipping Options**.

Then:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** and select Multi Shipping Cost as an integration type.
   ![Multi shipping integration form](user/img/system/integrations/multi-shipping-integration.png)
3. Provide the shipping method name that is shown as an option for shipping configuration in the OroCommerce back-office.
4. Set the status to **Active**.
5. Select the **Default Owner**. The field is already populated with the name of the user creating the integration. You can change this value to a different user if necessary
6. Click **Save and Close**.

#### IMPORTANT
Once the integration is created, the next step is to [set up a shipping rule](../../shipping-rules/index.md#sys-shipping-rules) under **System > Shipping Rules** and add your integration to it to enable customers to select the desired shipping method at checkout.

**Related Topics**

* [Shipping Configuration Concept Guide](../../../../concept-guides/shipping-configuration/index.md#admin-guide-shipping)
* [System Shipping Configuration](../../configuration/commerce/shipping/index.md#configuration-guide-commerce-configuration-shipping)
* [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules)
