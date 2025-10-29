<a id="configuration-commerce-marketplace-seller-global"></a>

# Configure Global Marketplace Settings

#### HINT
This section is part of the [OroMarketplace Concept Guide](../../../../../concept-guides/business-models/marketplace/index.md#concept-guide-oro-marketplace) that provides a general understanding of the marketplace features and concepts.

In OroMarketplace, you can configure to display the name of the seller (organization) in the storefront product listings, product details, shopping lists, and on order pages. Please be aware that to enable sellers to register with your marketplace and select the consents to be displayed in the Seller Registration form in the storefront, you must enable this feature in the [organization settings of the global organization](../../../user-management/organizations/org-configuration/commerce/marketplace/organization-marketplace-general.md#configuration-commerce-marketplace-seller-organization).

#### NOTE
You can also configure marketplace settings [per organization](../../../user-management/organizations/org-configuration/commerce/marketplace/organization-marketplace-general.md#configuration-commerce-marketplace-seller-organization).

To configure marketplace settings globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Marketplace > General** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

1. Clear the **Use Default** checkbox to change the system-wide setting.
2. In the **Product Family** section:
   * Enable the **Use Global Organization Product Family** to use product families from the Global organization. The creation of product families per seller will be restricted.
3. In the **Seller Name** section:
   * Enable the **Display Seller Name** checkbox to show the seller’s name in the storefront website.
4. In the **Promotions** section:
   * Select the **Enable Seller Promotions** option to enable sellers to have the capability to create their own [promotions and coupons](../../../../../concept-guides/business-models/marketplace/index.md#concept-guide-oro-marketplace-promotions) within their respective stores. This option is enabled by default. To further activate the promotion functionality, make sure that the following [options](../sales/global-multi-shipping.md#user-guide-system-configuration-commerce-sales-multi-shipping) are enabled:
     * **System Configuration > Commerce > Sales > Multi Shipping Options > Enable Shipping Method Selection Per Line Item**
     * **System Configuration > Commerce > Sales > Multi Shipping Options > Enable Grouping Of Line Items During Checkout**
     * **System Configuration > Commerce > Sales > Multi Shipping Options > Create Sub-Orders For Each Group**

   > In addition, please ensure that the **Group Line Items By** option under **System Configuration > Commerce > Sales > Multi Shipping Options** is set to *Organization*.
5. Click **Save Settings**.
