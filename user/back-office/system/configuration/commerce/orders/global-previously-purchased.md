<a id="sys-commerce-orders-previously-purchased-main"></a>

# Configure Global Settings for Previously Purchased Products

The previously purchased products page displays the products that were recently purchased by customer users. In the storefront, this page is nested under the **Previous Purchased** menu in **Account**.

![Previously Purchased customer account menu in the storefront](user/img/system/config_commerce/order/PreviouslyPurchasedFrontStore.png)

#### HINT
The previously purchased products page is disabled by default, but you can enable it on three levels, globally, [per organization](../../../user-management/organizations/org-configuration/commerce/orders/organization-previously-purchased.md#sys-commerce-orders-previously-purchased-org) and [per website](../../../websites/web-configuration/commerce/orders/website-previously-purchased.md#sys-commerce-orders-previously-purchased-website). Once enabled, you can also set the number of days that the purchase history should cover.

#### NOTE
Please keep in mind that [visibility restrictions](../../../../products/products/managing-product-visibility.md#products-product-visibility) may affect the visibility of products for the previously purchased products page. Consequently, if the product is hidden for a specific website, category, customer group, etc., it will not be available on the previously purchased list.

<a id="sys-commerce-orders-previously-purchased-global"></a>

## Enable and Set Up Previously Purchased Products

To enable previously purchased products page globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Orders > Purchase History** in the panel to the left.
   ![Global purchase history configuration settings](user/img/system/config_commerce/order/PreviouslyPurchasedGlobal.png)
3. In the **Purchase History** section:
   * *Enable Purchase History* — Clear the **Use Default** chec kbox and select the **Enable Purchase History** check box to enable the Previously Purchased Products page.
   * *Display Products Purchased Within (Days)* — The period of 90 days is set by default. To change it, clear the **Use Default** check box and enter the number of days that the purchase history should cover.
4. Click **Save Settings** on the top right of the page.
