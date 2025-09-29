<a id="pricing-currency-website"></a>

<a id="sys-websites-sysconfig-currency"></a>

# Configure Pricing Settings (Currencies) per Website

#### NOTE
The website level configuration has higher priority and overrides the global configuration settings.

#### IMPORTANT
Please, be aware that the configuration settings described below are for the default pricing feature (combined price list pricing) that comes out-of-the-box with your OroCommerce application. If you have [flat pricing configured for the whole application](../../../../../../../backend/setup/post-install/flat-pricing.md#dev-guide-setup-flat-pricing) (a simple pricing engine without strategies and merges), then the configuration page will have the Display Currency as well as General/Price List Settings. Flat pricing is also available on [organization](../../../../user-management/organizations/org-configuration/commerce/catalog/pricing.md#configuration-guide-commerce-configuration-catalog-pricing-organization) level. [It is enabled](../../../../../../../backend/setup/post-install/flat-pricing.md#dev-guide-setup-flat-pricing) by your system administrator via the console, not the UI.

![Website pricing configuration page when flat pricing is enabled](user/img/system/websites/web_configuration/flat-pricing-website-config.png)

To enable currencies per website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click the <i class="fas fa-cog" aria-hidden="true"></i> **Configuration** icon to start editing the configuration.
3. Select **Commerce > Catalog > Pricing** in the menu to the left.
4. In the **Display Currencies** section, the following options are available:

   #### NOTE
   The **Display Currencies** field is only available in the Enterprise edition.

   * **Enabled Currencies** — The subset of [allowed currencies](../../../../configuration/system/general-setup/global-currency.md#sys-config-sysconfig-general-setup-currency) that is available for the customer user by default.

   ![Currency in the storefront](user/img/system/websites/web_configuration/currency_on_the_front_store.png)
   * **Default Currency** — The currency that is used by default to show prices in the storefront.

   To customize the option configuration, clear the **Use Organization** check box next to the option and select or type in the new option value.
5. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
