<a id="configuration-guide-commerce-configuration-promotions"></a>

<a id="user-guide-new-products"></a>

<a id="sys-commerce-product-new-arrivals"></a>

<a id="sys-commerce-product-new-arrivals-block-global"></a>

# Configure Global Settings for Product Promotions

## Enable New Product Icons

On the Product Promotions configuration page, you can enable **New** product icon to be displayed on the product details page.

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Promotions** in the menu to the left.
3. To customize the option configuration, clear the **Use Default** checkbox to override the default configuration.
4. In the **New Product Icons** section, select *Yes* or *No* in the **Show on Product View** list to enable or disable new product icon on the product details page.

![A new icon is displayed on the product details page](user/img/system/config_commerce/product/new-product-icon.png)

## Configure New Arrivals Globally (Version 5.1 and Below)

#### IMPORTANT
The configuration applies to OroCommerce version 5.1 and below and is retained in the current version only for legacy backward compatibility. For v6.0 and above, please configure this option via the product segment content widget under Marketing > Content Widgets following the [new configuration logic](../../../../../concept-guides/catalog-promotions/product-management/index.md#concept-guides-product-management-new-arrivals-products).

### Prerequisites

Before enabling the new arrivals segment, make sure you have performed the following actions:

1. Mark the selected products as new arrivals in the **General** section of the **Products > Products** main menu by setting **Is New Arrival** to *Yes*.
2. Create a new arrivals segment under **Reports & Segments > Manage Segments** as described in the [Create Segment](../../../../reports-segments/segments.md#user-guide-business-intelligence-create-segments) topic.

### Configuration

To set up a **New Arrivals** block globally, [per organization](../../../user-management/organizations/org-configuration/commerce/product/organization-new-arrivals.md#sys-users-organization-commerce-products-new-arrivals) and [per website](../../../websites/web-configuration/commerce/product/website-new-arrivals.md#sys-websites-commerce-products-new-arrivals).

1. In the main menu, navigate to **System > Configuration**.
2. Select **Commerce > Product > Promotions** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global new arrivals configuration](user/img/system/config_commerce/product/NewArrivalsBlockSystemConfig.png)
3. To customize the option configuration, clear the **Use Default** checkbox next to the option and select the required value.
4. In the **New Arrivals** section, provide the following information:
   * **Product Segment** – Select the segment that will include the items to be featured in the **New Arrivals** block.

   > #### NOTE
   > If *Choose Segment* is selected, the **New Arrivals** block disappears from the homepage.
   * **Maximum Items** – Set the maximum number of items that the block should contain. By default, the number is set to 4 items.
   * **Minimum Items** – Set the minimum number of items that the block should contain. By default, the number is set to 3 items.

   #### NOTE
   The block will be hidden if the number of items in the segment used for the block is less than the set value. For instance, if the set minimum number is 3 and the number of items in the segment is 2, you will not be able to see the block unless you add more items to the segment, or change the minimum value.

   * **Use Slider On Mobile** checkbox – When the slider is enabled, the block occupies less screen space, while showing larger product images.
5. Click **Save**.
