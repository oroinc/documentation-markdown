<a id="user-guide-pricing-multiple-currencies"></a>

# Manage Prices in Multiple Currencies

#### NOTE
Before you begin, ensure that the necessary currencies are enabled in the [global](../../system/configuration/system/general-setup/global-currency.md#sys-config-sysconfig-general-setup-currency) and [website](../../system/websites/web-configuration/commerce/catalog/website-pricing.md#sys-websites-sysconfig-currency) configuration. Keep in mind that the multi-currency feature is only available in the Enterprise edition.

## Enable Multiple Currencies for the Price List

To add or remove currencies that may be used in a price list:

1. Navigate to **Sales > Price Lists** in the main menu.
2. Click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the price list and then click the <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** icon to start editing the price list details.
3. In the **General** section, next to the **Currencies**, select the currencies you would like to enable for the price list (e.g., USD, EUR, PND) and unselect those you would like to disable.
   ![Currencies available in the system](user/img/sales/pricelist/PriceListsCurrencies.png)
4. Once you enable the necessary currencies for the price list, click **Save**.

## Add Price in Specific Currency to the Price List

When adding a product price manually or using a rule that automates price generation, you always specify the currency it is in.
You can add only one price per combination of product quantity tier and currency (e.g., one price for 1 item in USD or 10 items in EUR).
For detailed information on adding product prices in particular currencies, see [Manual Price Management](manual.md#user-guide-pricing-price-list-manual) and [Automated Rule-Based Price Management](auto.md#user-guide-pricing-price-list-auto).

## View Price in Specific Currency in the Storefront

By default, prices in the OroCommerce storefront are shown in the default currency.

However, you may select a different currency with a currency selector on the top right.

![Switching between currencies in the storefront](user/img/sales/pricelist/currency_on_the_front_store.png)

After the new currency is selected, product prices automatically adjust to show the unit prices in the selected currency.
: When the price list does not contain the price for the product in the selected currency, the price information is absent. You can still add the product to the shopping list and request a quote to clarify the pricing in the specific currency.

**Related Topics**:

* [Configure Currency Exchange Rate](../../system/configuration/system/general-setup/global-currency.md#sys-config-sysconfig-general-setup-currency)
* [Configure Pricing Settings](../../system/configuration/commerce/catalog/global-pricing.md#sys-config-commerce-catalog-pricing)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
