<a id="user-guide-system-configuration-commerce-sales-multi-shipping-website"></a>

# Configure Multiple Shipping Settings per Website

For standard [multi-step checkout](../../../../../../concept-guides/administration/checkout/index.md#checkout-guide-multi-page), you configure different line item grouping for the storefront checkout, as well as enable storefront customers to select different shipping methods for different line items. In addition, you can enable sub-orders to be created for each group of line items.

![Displaying order line items grouped by category at checkout](user/img/system/config_commerce/sales/multi-shipping-storefront.png)

You can also configure this functionality [globally](../../../../configuration/commerce/sales/global-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping) and [per organization](../../../../user-management/organizations/org-configuration/commerce/sales/organization-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping-org).

To configure multi shipping per website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Sales > Multi Shipping Options** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
4. Clear the **Use Organization** checkbox to change the organization-wide settings.
5. In the **General Options**, select **Enable Shipping Method Selection Per Line Item** to activate the multi-shipping functionality and display other related options.
6. In the **Line Items Grouping Options**, configure the following options:
   * **Enable Grouping Of Line Items During Checkout** — When enabled, line items during checkout are displayed in groups divided by specific criteria (e.g., ID, category, brand, etc). This option may affect shipping rules and discount calculations (see other configuration options).
     * *Group Line Items By* — Select if you want to group line items per ID, category, brand, or parent product.
     * *Create Sub-Orders For Each Group* — When enabled, in addition to the main order, the system will create respective sub-orders for each group of line items in the back-office. Storefront customers, however, will see only primary orders in their order history.
7. In the **Order History Options** section, configure the following options:
   > * *Show Sub-Orders In Order History* — When enabled, customers can see only sub-orders in their order history. Primary orders will be hidden.
   > * *Show Main Orders In Order History* — When enabled, customers can see both the primary order and its sub-orders in their order history.
8. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
