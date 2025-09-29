<a id="user-guide-system-configuration-commerce-sales-multi-shipping"></a>

# Configure Global Multiple Shipping Settings

#### HINT
The Multiple Shipping feature is available starting from OroCommerce v5.0.8. To check which application version you are running, see the [system information](../../../system-information/index.md#system-information).

For standard [multi-step checkout](../../../../../concept-guides/checkout/index.md#checkout-guide-multi-page), you can configure different line item grouping for the storefront checkout, as well as enable storefront customers to select different shipping methods for different line items. In addition, you can enable sub-orders to be created for each group of line items.

![Displaying order line items grouped by category at checkout](user/img/system/config_commerce/sales/multi-shipping-storefront.png)

You can also configure this functionality [per organization](../../../user-management/organizations/org-configuration/commerce/sales/organization-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping-org) and [per website](../../../websites/web-configuration/commerce/sales/website-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping-website).

To configure multi shipping globally:

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Sales > Multi Shipping Options** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).
3. To update any of the options, clear the **Use Default** checkbox first.
4. In the **General Options**, select **Enable Shipping Method Selection Per Line Item** to activate the multi-shipping functionality and display other related options.
5. Once you enable multi shipping, you are prompted to create the related [multi shipping integration](../../../integrations/shipping-integration/multi-shipping.md#doc-integrations-multi-shipping) to allow customers select a preferred shipping method at checkout. To simplify the manual integration creation, click the **Create Multi Shipping Integration** button to create it automatically. After the integration is created, the note disappears.

![Global multi shipping configuration settings and a button for the automatic integration creation](user/img/system/config_commerce/sales/multi-shipping-button.png)
1. In the **Line Items Grouping Options**, configure the following options:
   ![Global multi shipping configuration settings](user/img/system/config_commerce/sales/multi-shipping-global.png)
   * **Enable Grouping Of Line Items During Checkout** — When enabled, line items during checkout are displayed in groups divided by specific criteria (e.g., ID, category, brand, etc). This option may affect shipping rules and discount calculations (see other configuration options).
     * *Group Line Items By* — Select if you want to group line items per ID, owner, category, brand, or parent product.
     * *Create Sub-Orders For Each Group* — When enabled, in addition to the main order, the system will create respective sub-orders for each group of line items in the back-office. Storefront customers, however, will see only primary orders in their order history.
2. In the **Order History Options** section, configure the following options:
   > * *Show Sub-Orders In Order History* — When enabled, customers can see only sub-orders in their order history. Primary orders will be hidden.
   > * *Show Main Orders In Order History* — When enabled, customers can see both the primary order and its sub-orders in their order history.
3. Click **Save Settings**.

#### IMPORTANT
Once the integration is created, the next step is to [set up a shipping rule](../../../shipping-rules/index.md#sys-shipping-rules) under **System > Shipping Rules** and add your integration to it to enable customers to select the desired shipping method at checkout.
