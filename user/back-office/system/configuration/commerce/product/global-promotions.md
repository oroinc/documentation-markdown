<a id="configuration-guide-commerce-configuration-promotions"></a>

<a id="user-guide-new-products"></a>

<a id="sys-commerce-product-new-arrivals"></a>

<a id="sys-commerce-product-new-arrivals-block-global"></a>

# Configure Global Settings for Product Promotions

On the Product Promotions configuration page, you can enable **New** product icons and set up a **New Arrivals** block globally, [per organization](../../../user-management/organizations/org-configuration/commerce/product/organization-new-arrivals.md#sys-users-organization-commerce-products-new-arrivals) and [per website](../../../websites/web-configuration/commerce/product/website-new-arrivals.md#sys-websites-commerce-products-new-arrivals).

![A new arrivals flag vs a new arrivals segment](user/img/system/config_commerce/product/new_arrivals_diff.png)

## Prerequisites

Before enabling the new product icons and new arrivals segment, make sure you have performed the following actions:

1. Mark the selected products as new arrivals in the **General** section of the **Products > Products** main menu by setting **Is New Arrival** to *Yes*.
2. Create a new arrivals segment under **Reports & Segments > Manage Segments** as described in the [Create Segment](../../../../reports-segments/segments.md#user-guide-business-intelligence-create-segments) topic.

## Configure New Arrivals Globally

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Promotions** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global new arrivals configuration](user/img/system/config_commerce/product/NewArrivalsBlockSystemConfig.png)
3. In the **New Product Icons**, clear the **Use Default** check box and select *Yes* in the **Show on Product View** list to enable new product icons. To disable the icons, select *No*.
   > A new product icon will look differently for various layout options:
   > * **For tiles**:

   > ![New product icon look for tiles](user/img/system/config_commerce/product/NewArrivalsFrontstoreTiles.png)
   > * **For details**:

   > ![New product icon look for details](user/img/system/config_commerce/product/NewArrivalsFrontstoreDetails.png)
   > * **For compact details**:

   > ![New product icon look for compact details](user/img/system/config_commerce/product/NewArrivalsFrontstoreCompactDetails.png)

1. In the **New Arrivals** section provide the following information:
   * **Product Segment** – Select the segment that will include the items to be featured in the **New Arrivals** block.

   > #### NOTE
   > If *Choose Segment* is selected, the **New Arrivals** block disappears from the homepage.
   * **Maximum Items** – Set the maximum number of items that the block should contain. By default, the number is set to 4 items.
   * **Minimum Items** – Set the minimum number of items that the block should contain. By default, the number is set to 3 items.

   #### NOTE
   The block will be hidden if the number of items in the segment used for the block is less than the set value. For instance, if the set minimum number is 3 and the number of items in the segment is 2, you will not be able to see the block unless you add more items to the segment, or change the minimum value.

   * **Use Slider On Mobile** check box – When the slider is enabled, the block occupies less screen space, while showing larger product images.

#### NOTE
Clear the **Use Default** check box to change settings manually.
