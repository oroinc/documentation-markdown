<a id="configuration-commerce-shipping-tax-website"></a>

# Configure Shipping Tax Settings per Website

#### HINT
This section is part of the [Tax Management](../../../../../../concept-guides/administration/taxes/index.md#concept-guide-taxes) concept guide that provides a general understanding of the tax configuration and management in OroCommerce.

You can select a shipping tax code that should be used for shipping total cost calculation and specify if the shipping cost already contains a tax.

To change the shipping tax configuration for a specific website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Taxation > Shipping** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

1. Clear the **Use Organization** checkbox to change the organization-wide setting.
2. In the **Shipping Tax** section, configure the options:
   * **Tax Code** - Select the tax code (tax identifier) that in combination with [tax rules](../../../../../taxes/tax-rules/index.md#tax-rules) defines the tax rate that is applied for the shipping tax calculation.
   * **Shipping Rates Include Tax** - Enable the checkbox to avoid charging taxes on shipping twice if the shipping rates provided by the shipping carrier(s) or entered manually in the back-office already include tax.
3. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
