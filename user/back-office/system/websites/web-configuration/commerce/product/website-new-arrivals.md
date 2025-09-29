<a id="sys-websites-commerce-products-new-arrivals"></a>

<a id="sys-commerce-product-new-arrivals-block-website"></a>

# Configure Settings for Product Promotions per Website

In the Promotions section of Commerce configuration settings, you can enable **New** product icons and configure the new arrivals block for the storefront per website. You can also enable them [globally](../../../../configuration/commerce/product/global-promotions.md#configuration-guide-commerce-configuration-promotions) and [per organization](../../../../user-management/organizations/org-configuration/commerce/product/organization-new-arrivals.md#sys-users-organization-commerce-products-new-arrivals).

## Prerequisites

Before enabling the new product icons and new arrivals segment, make sure you have performed the following actions:

1. Mark the selected products as new arrivals in the **General** section of the **Products > Products** main menu by setting **Is New Arrival** to *Yes*.
2. Create a new arrivals segment under **Reports & Segments > Manage Segments** as described in the [Create Segment](../../../../../reports-segments/segments.md#user-guide-business-intelligence-create-segments) topic.

## Configure New Arrivals per Website

1. Navigate to **System > Website** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.
3. Select **Commerce > Product > Promotions** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![image](user/img/system/websites/web_configuration/NewArrivalsBlockWeb.png)
4. In the **New Product Icons**, clear the **Use Organization** check box and select *Yes* in the **Show on Product View** list to enable new product icons. To disable the icons, select *No*.
5. In the **New Arrivals** section provide the following information:
   * **Product Segment** – Select the segment that will include the items to be featured in the **New Arrivals** block.

   > #### NOTE
   > If *Choose Segment* is selected, the **New Arrivals** block disappears from the homepage.
   * **Maximum Items** – Set the maximum number of items that the block should contain. By default, the number is set to 4 items.
   * **Minimum Items** – Set the minimum number of items that the block should contain. By default, the number is set to 3 items.

   #### NOTE
   The block will be hidden if the number of items in the segment used for the block is less than the set value. For instance, if the set minimum number is 3 and the number of items in the segment is 2, you will not be able to see the block unless you add more items to the segment, or change the minimum value.

   * **Use Slider On Mobile** – When the slider is enabled, the block occupies less screen space, while showing larger product images.

#### NOTE
When enabled, **Use Organization** allows for system settings to be used. Clear this check box to enable manual change of settings.

1. Click **Save**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
