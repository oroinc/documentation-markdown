<a id="customers-customer-groups-edit-price-lists"></a>

# Configure Price List per Customer Group

<!-- begin -->

To change the price list settings for the customer group:

1. Navigate to **Customers > Customer Group** in the main menu.
2. Click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer group and then click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon to start editing the group details.
3. In the **Price Lists** section, do the following to configure price lists that are used for price calculation when the customer users who belong to this customer group access the particular website (for example, *Default*):

   #### TIP
   Switch between the websites using tabs.

   ![The price list section of the All Customers customer group](user/img/customers/customer_groups/customer_group_price_lists.png)
   1. Select one of the following values for the **Fallback** option:
      * *Website* — OroCommerce uses [Website Price Lists from the selected website configuration](../../system/websites/configure-price-lists.md#sys-website-edit-price-lists) to calculate the prices shown in the storefront.
      * *Current customer group only* — For price calculation, OroCommerce uses the configurations (per website) in the current customer group.
   2. To add a price list, click **+ Add Price List** and select the price list in the newly added line. After you start typing the price list name, the list of suggestions appears. Press **Enter** or click the suggested value to add the price list.

   ![Adding a new price list to the pricelist section](user/img/customers/customer_groups/pricing_pricelist_add.png)

   #### NOTE
   The price list is appended to the bottom of the list and, initially, has a lower priority than the existing price lists. Adjust the price list priority if necessary and specify whether the merge is allowed (the later is shown only for the **Merge by priority** price selection strategy).

   1. To control the way prices are merged into the combined price list, select or clear the **Merge Allowed** option for the price lists.

   When merge is allowed, the prices for the tiers and units that are missing in the higher priority price list may be covered by the prices from the lower priority price lists that support the price merge.
   1. To delete a price list from the default price lists, click the <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** icon at the end of the corresponding row.
   2. To change the price list priority, click and hold the <i class="fas fa-arrows-alt-v" aria-hidden="true"></i> **Sort** icon, and drag the price list up or down the list.
4. Click **Save**.

<!-- finish -->

**Related Articles**

* [Pricing Configuration](../../system/configuration/commerce/catalog/global-pricing.md#pricing-configuration)
* [Price List Configuration per Website](../../system/websites/configure-price-lists.md#sys-website-edit-price-lists)
* [Price List Configuration per Customer](../customers/customer-price-lists.md#customers-customers-edit-price-lists)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
