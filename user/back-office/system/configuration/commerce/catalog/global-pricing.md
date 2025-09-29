<a id="sys-config-commerce-catalog-pricing"></a>

<a id="pricing-configuration"></a>

# Configure Global Pricing Settings

#### HINT
This section is part of the [Price Management](../../../../../concept-guides/pricing/index.md#user-guide-pricing) topic that provides the general understanding of pricing concept in Oro applications.

Global pricing configuration helps you:

* Enable/disable the default OroCommerce pricing management system.
* Set the price precision and price rounding strategy.
* Configure default price lists, their priority and merge strategy to get the necessary resulting combination of prices that are shown on the websites, and for the customers whenever their price list settings fall back to the system default.
* Specify an offset in hours that helps launch combined price list recalculation before price change is activated.
* Enable all or some currencies from the allowed currencies list to be used in the OroCommerce storefront and back-office.
* Select the currency that is shown by default in the OroCommerce storefront and back-office.

#### NOTE
The [website level](../../../websites/configure-price-lists.md#sys-website-edit-price-lists) configuration has higher priority and overrides these configuration settings. [Customer group](../../../../customers/customer-groups/customer-group-price-lists.md#customers-customer-groups-edit-price-lists) configuration overrides configuration on the website level. Custom configuration on the [customer level](../../../../customers/customer-groups/customer-group-price-lists.md#customers-customer-groups-edit-price-lists) has the highest priority.

#### IMPORTANT
Please, be aware that the configuration settings described below are for the default pricing feature (combined price list pricing) that comes out-of-the-box with your OroCommerce application. If you have [flat pricing configured for the whole application](../../../../../../backend/setup/post-install/flat-pricing.md#dev-guide-setup-flat-pricing) (a simple pricing engine without strategies and merges), then the configuration page will have only Display Currency, Price Rounding, and General/Price List Settings. Flat pricing is also available on [organization](../../../user-management/organizations/org-configuration/commerce/catalog/pricing.md#configuration-guide-commerce-configuration-catalog-pricing-organization) and [website](../../../websites/web-configuration/commerce/catalog/website-pricing.md#pricing-currency-website) levels. [Flat pricing is enabled](../../../../../../backend/setup/post-install/flat-pricing.md#dev-guide-setup-flat-pricing) by your system administrator via the console, not the UI.

![Pricing configuration page when flat pricing is enabled](user/img/system/config_commerce/catalog/flat-pricing-enabed-config.png)

To change the default global pricing settings:

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Catalog > Pricing** in the menu to the left.

> The following options are available on the **Pricing** page:

> > ![Pricing system configuration page](user/img/system/config_commerce/catalog/pricing_sys_config.png)
> > * **Enable Oro Pricing** — By default, this option is enabled. When disabled, all pricing stored in and managed by the default OroCommerce pricing management system becomes hidden from the application. Disable Oro Pricing when you need to introduce a custom pricing management system for storing and fetching prices.
> > * **Subtotals Calculation Precision in Sales Documents** — The number of digits allowed in the fractional part of the subtotals, totals, and taxes calculated in shopping lists, checkout, orders, and RFQs. For example, with precision for sales documents set to 2, even when the original precision of prices is 4, such as $10.0001, the subtotals and taxes will be rounded to 2 digits. Note that the feature is available starting from OroCommerce v.4.2.7.
> > * **Price Calculation Precision in Price Lists** — The number of digits allowed in the fractional part of the price calculation rule results. The results will be rounded using the “round half away from zero” rule (2.5 will be rounded to 3). If this value is empty, the system will not apply any rounding until the maximum supported price precision (4 digits) is reached. Note that the feature is available starting from OroCommerce v.4.2.7.
> > * **Pricing Rounding Type** — The rounding type used when calculated product price has more digits in the fractional part than allowed by the respective price precision settings. These are the rounding settings used for price and tax calculations that happen in shopping lists, checkout, orders, and RFQs. Please use one of the following options:
> >   - *Ceil* — Rounds to the nearest integer that is not less than the price with the fractional part (e.g., 23.5 is rounded to 24; 23.3 is rounded to 24; 23.7 is rounded to 24)
> >   - *Floor* — Rounds to the nearest integer that does not exceed the price with the fractional part (e.g., 23.5 is rounded to 23; 23.3 is rounded to 23; 23.7 is rounded to 23)
> >   - *Half Down* — Uses ceil rounding for the prices with the fractional part that is bigger than 0.5 and uses floor rounding for the prices with a fractional part that is that lower than or equal to 0.5 (e.g., 23.5 is rounded to 23; 23.3 is rounded to 23; 23.7 is rounded to 24)
> >   - *Half Up* —  Uses ceil rounding for the prices with the fractional part that is bigger than or equal to 0.5 and uses floor rounding for the prices with a fractional part that is that lower than 0.5 (e.g., 23.5 is rounded to 24; 23.3 is rounded to 23; 23.7 is rounded to 24)
> >   - *Half Even* — Uses ceil rounding for the prices with the fractional part that is bigger than 0.5, uses floor rounding for the prices with a fractional part that is that lower than 0.5, and rounds the price to the nearest even integer when the price fraction is exactly 0.5 (e.g., 23.5 is rounded to 24; 23.3 is rounded to 23; 23.7 is rounded to 24)
> > * **Price Lists** — A set of default price lists that can be used for price calculation. A website, a customer group, and a customer can have their own set of price lists that overrides the default configuration.

<a id="offset-of-processing-cpl-prices"></a>
> * **Offset Of Processing CPL Prices** — An offset (in hours) from the scheduled price change that determines how early the price list recalculation and reindex should happen to prepare the actual prices in the OroCommerce storefront for the scheduled launch. Delayed recalculation helps spread resource-consuming tasks in time and launch them only when the price is going to be used soon. This eliminates unnecessary intermediate recalculation every time the price is updated between the time price list schedule is added and the time when recalculation is expected to start (considering the offset from the scheduled launch). If you update the price once a week, set the offset to 40 (hours). If you update prices more frequently, set the value that approximately matches the delay between the updates of the price information. It can be aligned with the data synchronization process between your OroCommerce and the external ERP system. For continuos price updates use the minimal recommended offset value of 0.083 (5 minutes).
> * **Pricing Strategy** — The strategy used for matching prices. OroCommerce searches for the closest match of the product price in the selected units and currency for the requested product quantity in one of the following ways:
>   - Using *Minimal Price* strategy — From the default or customized set of price lists, OroCommerce collects all products prices that match product units, currency, and the requested product quantity, and selects the minimal price per tier and per unit as the one to show to the customer user:
>     ![Default price lists configuration when minimal strategy is selected](user/img/system/config_commerce/catalog/pricing_pricelist_new_ui.png)
>   - Using *Merge by priority* strategy — OroCommerce walks through the default or customized set of price lists starting with the price list of the top priority and moving along to those with the lower priority.

>     When the product price is initially found in the price list with the **Merge Allowed** option *enabled*, the price and the price list priority is collected for further evaluation and merge. Prices for other units and for other tiers of product quantity can be collected from the same price list and from other price lists with the **Merge Allowed** option *enabled*. The tier/unit prices with the highest priority are shown to the customer user.

>     When the product price is initially found in the price list with the **Merge Allowed** option *disabled*, OroCommerce collects the product prices for all units and for all tiers of product quantity from this price list only. Other price lists are not taken into account, as price merge is not allowed. The units and tiers of quantity where the price is missing are hidden from the customer user.
>     ![Default price lists configuration when merge allowed is selected](user/img/system/config_commerce/catalog/pricing_pricelist2_new_ui.png)
> * **Enabled Currencies** — The subset of [allowed currencies](../../system/general-setup/global-currency.md#sys-config-sysconfig-general-setup-currency) that is available for the customer user by default.

>   #### NOTE
>   The **Display Currencies** field is only available in the Enterprise edition.

>   ![Display the currency selector in the storefront](user/img/system/config_commerce/catalog/currency_on_the_front_store.png)
> * **Default Currency** — The currency that is used by default to show prices in the storefront.
1. To customize the option configuration, clear the **Use Default** check box next to the option and select or type in the new option value.
2. To add a price list to the default price lists:
   1. Click **+ Add Price List** and select the price list in the newly added line. After you start typing the price list name, the list of suggestions that match your entry appears. Press **Enter** or click the suggested value to add the price list.
      ![Adding a price list to the default price lists](user/img/system/config_commerce/catalog/pricing_pricelist_add.png)

      #### NOTE
      The price list is appended to the bottom of the list and, initially, has lower priority than the existing price lists. Adjust the price list priority if necessary and specify whether the merge is allowed (the later is shown only for the *Merge by priority* price selection strategy).
3. To control the way prices are merged into the combined price list, select or clear the **Merge Allowed** option for the price lists.

   When merge is allowed, the prices for the tiers and units that are missing in the higher priority price list can be covered by the prices from the lower priority price lists that should support price merge too.
4. To delete a price list from the default price lists, click the <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Deactivate** at the end of the corresponding row.
5. To change the price list priority, click and hold  the <i class="fas fa-arrows-alt-v" aria-hidden="true"></i> **Sort** icon, and drag the price list up or down the list.
6. To roll back any changes to the currency settings, click **Revert** on the top right.

1. Click **Save Settings**.

**Related Articles**

* [Pricing Overview](../../../../../concept-guides/pricing/index.md#user-guide-pricing)
* [Pricing Configuration per Website](../../../websites/web-configuration/commerce/catalog/website-pricing.md#sys-websites-sysconfig-currency)
* [Global Currency Configuration](../../system/general-setup/global-currency.md#admin-configuration-currency)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
