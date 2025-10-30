<a id="admin-configuration-currency-org"></a>

# Configure Currency Settings per Organization

#### IMPORTANT
To enable a currency on the organization level, you should add it to the list of allowed currencies at the system level first. The organization-level configuration for base currency and display format has higher priority and overrides the system setting.

To change the default currency settings per organization:

1. Navigate to **System > Configuration > User Management > Organizations** in the main menu.
2. For the necessary organization, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the <i class="fas fa-cog" aria-hidden="true"></i> **Configure** icon to start editing the configuration.
3. Select **System Configuration > General Setup > Currency** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
4. Remove the **Use System** checkbox to enable the currency configuration for the organization.

## Currency Settings

The following sections become available within the **Currency** tab:

![image](user/img/system/user_management/org_configuration/general/currency_org.png)

| **Name**               | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Allowed currencies** | **Allowed currencies** list allows you to select some of all available currencies to enable them in your<br/>Oro application.<br/><br/>To add the allowed currency, select it from the list and click **Add**.<br/><br/>The new row is added to the allowed currencies options table, where you can configure the exchange rates<br/>for the newly added currency and may set it as a base currency.<br/><br/>**Note:** You cannot add the currency that is not set at the system level.<br/>See [Allowed Currencies Options for Organization]() for more information.                                                                                                                                                                                                                                                               |
| **Display format**     | This setting controls how the currencies will be displayed within the system, as a 3-letter ISO code<br/>(e.g. GBP) or as the currency symbol (e.g. £).<br/><br/>To customize the **Display Format**:<br/><br/>1. Clear the **Use System** checkbox next to the option.<br/>2. Select the new option value (either *Currency Code* or *Currency Symbol*).<br/><br/>**Note:** Not all currencies might have symbols. For such currencies, ISO codes are used instead.<br/><br/>The order subtotal when the display format is set to *Currency Code*:<br/><br/>![image](user/img/system/user_management/org_configuration/general/currency_code.png)<br/><br/>The order subtotal when the display format is set to *Currency Symbol*:<br/><br/>![image](user/img/system/user_management/org_configuration/general/currency_symbol.png) |

## Allowed Currencies Options for Organization

The information about the allowed currencies options is grouped in the following columns:

#### NOTE
This feature is only available in the Enterprise edition.

| **Name**            | Description                                                                                                                                                                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Base**            | A flag helps you to select the base currency.<br/>Base currency is used by default to display totals, budgets, and amounts.                                                                                                                 |
| **Currency Name**   | International name of the currency that follows ISO 4217 standard (e.g. US dollar).                                                                                                                                                         |
| **Currency Code**   | International currency code that follows ISO 4217 standard (e.g. USD).                                                                                                                                                                      |
| **Currency Symbol** | Graphical symbol that is used to denote a currency (e.g. $).                                                                                                                                                                                |
| **Rate From**       | The conversion rate from the selected currency to the base currency. Used to calculate transaction amounts<br/>(e.g. opportunity budget) in the base currency if they were entered in other currencies.<br/>Maximum precision is 10 digits. |
| **Rate To**         | The conversion rate from the base currency to the selected currency. Used to calculate new exchange rates<br/>when the base currency is changed. Maximum precision is 10 digits.                                                            |
1. To change the base currency, click the **Base** option in the corresponding row. This will lead to reconversion of all multi-currency data to the new base currency, and all values will be re-converted according to the current rates. Keep in mind that multi-currency is only available in the Enterprise edition.

   Before:
   ![image](user/img/system/user_management/org_configuration/general/currency_base1.png)

   After:
   ![image](user/img/system/user_management/org_configuration/general/currency_base3.png)

   #### IMPORTANT
   Changing base currency requires manual update of the money values (budgets, totals, revenues, etc.). You will be prompted to confirm the change.

   In the example below, the base currency is British pounds but the budget of the opportunity deal is in US dollars.
   ![image](user/img/system/user_management/org_configuration/general/example_base_and_us_budget.png)

   When you close a deal (determined by opportunity status), the exchange rate for it becomes locked and will no longer take rate changes into account.

   Dashboard widgets with monetary values (e.g. Forecast) and monetary metrics work in the base currency irrespective of the currency that the deals were made in.

> ![image](user/img/system/user_management/org_configuration/general/widgets_base_currency.png)
1. To modify the currency exchange rate to and from the base currency, edit the **Rate To** and **Rate From** values in the corresponding row.

   For example, if the rate of US dollar to British pound is 1:0.76, enter 0.76 in the empty Rate From field for US Dollar. The system will automatically calculate the Rate To value for US Dollar which will constitute 1.315789.
   ![image](user/img/system/user_management/org_configuration/general/rate_recalculation.png)

   #### NOTE
   The base currency rate is always 1 to 1 and cannot be changed.
2. To add a currency to the allowed currencies list:
   1. Select the currency from the **Allowed Currencies** list and click **Add** next to it.

      #### NOTE
      Keep in mind that if the currency is not set at the system level, it cannot be added to the list. For example, if at the system level the admin has set up 4 currencies – US dollars, Australian dollars, British pounds, and Euro, then at the organization level, you can see no more than these 4 currencies. In other words, it is possible to remove unnecessary currencies but not add new ones (which are not set at the system level).
      ![image](user/img/system/user_management/org_configuration/general/currency_add_org.png)
   2. Fill in the exchange rate to and from the base currency.
3. To delete a currency from the allowed currencies list, click the <i class="fa fa-times fa-lg" aria-hidden="true"></i> **Delete Currency** icon at the end of the corresponding row.

   #### NOTE
   Deleting base currency is restricted. To unlock delete action for the currency that is set as base, switch to a different base currency.

   If you delete a currency at organization level, it would appear in the **Allowed Currencies** field, so it would be possible to add it back if necessary. However, you cannot delete the currency that is already in use. In later releases, if you wish to delete the currency that is used by an entity, you would have an option of converting it into a different currency.
4. To change the currency sort order, click and hold the <i class="fas fa-arrows-alt-v" aria-hidden="true"></i> **Sort** icon, and drag the currency up or down the list.
5. To roll back any changes to the currency settings, click **Reset** on the top right.
6. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
