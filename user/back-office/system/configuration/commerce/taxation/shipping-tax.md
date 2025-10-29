<!-- System > Configuration > Commerce > Taxation > Shipping Tax -->

# Configure Global Shipping Tax Settings

#### HINT
This section is part of the [Tax Management](../../../../../concept-guides/administration/taxes/index.md#concept-guide-taxes) concept guide that provides a general understanding of the tax configuration and management in OroCommerce.

You can select a shipping tax code that should be used for shipping total cost calculation and specify if the shipping cost already contains a tax.

To change the shipping tax configuration:

1. Navigate to the system configuration (click **System > Configuration** in the main menu).
2. Select **Commerce > Taxation > Shipping** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global shipping tax configuration](user/img/system/config_commerce/taxation/shipping_tax_config.png)
3. Clear the **Use Default** checkbox to change the system-wide setting.
4. In the **Shipping Tax** section, configure the options:
   * **Tax Code** - Select the tax code (tax identifier) that in combination with [tax rules](../../../../taxes/tax-rules/index.md#tax-rules) defines the tax rate that is applied for the shipping tax calculation.
   * **Shipping Rates Include Tax** - Enable the checkbox to avoid charging taxes on shipping twice if the shipping rates provided by the shipping carrier(s) or entered manually in the back-office already include tax.
5. Click **Save**.
