<a id="user-guide-system-configuration-commerce-sales-invoices-org"></a>

# Configure Invoice Settings per Organization

You can configure invoice-related sales [globally](../../../../../configuration/commerce/sales/global-invoices.md#configuration-guide-commerce-configuration-sales-invoices), per organization, [website](../../../../../websites/web-configuration/commerce/sales/website-invoices.md#user-guide-system-configuration-commerce-sales-invoices-per-website), [customer group](../../../../../../customers/customer-groups/customer-group-configuration/commerce/sales/customer-group-invoices-settings.md#user-guide-customer-group-invoice-settings) and [customer](../../../../../../customers/customers/customer-configuration/commerce/sales/customer-invoices-settings.md#user-guide-customers-invoice-settings).

To configure invoices per organization:

1. Navigate to **System > User Management > Organizations** in the main menu.
2. For the necessary organization, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary organization and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Sales > Invoices** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![The organization-wide invoice configuration settings](user/img/sales/invoices/invoice_org.png)
1. In the **General** section, toggle the following options:
   * **Enable Invoices** —  enabling this option activates the Invoices feature in the back-office. Once enabled, you can access it via *Sales > Invoices* in the main menu.
   * **Invoice Number Prefix** — define the prefix to be used when generating invoice numbers (e.g., INV-).
   * **Show Invoices in the Storefront** — enable this option to display invoices in the storefront.
2. In the **Invoice PDF** section, configure the following options:
   * **Generate PDF When Invoice Becomes Posted** — Enable the option to generate a PDF file when the invoice is marked as *Posted*. Once created, the PDF will not be re-created, even if the invoice is modified later.

   ![The Download button appears on the Invoice details page once the invoice changes its status to Posted](user/img/sales/invoices/download-invoice.png)
   * **Enable Invoice PDF Download in Customer Portal** — Enable the option to display a **Download** button on invoice pages in the storefront, if a PDF file has been created and attached to the invoice.

   ![The Download button on the Invoice details page in the storefront](user/img/sales/invoices/download-invoice-storefront.png)
3. In the **Payments** section, toggle the following options:
   * **Enable Invoice Payments** — Enables or disables the invoice payment functionality system-wide. When enabled, a Pay button is displayed in the storefront, and a Payments section is added to the invoice view page in the back-office.
   * **Payment Method** — Specifies the payment method used for invoice payments in the storefront. Currently, only the [Stripe Integration Element](../../../../../integrations/payment-integration/stripe/index.md#user-guide-payment-payment-providers-stripe-element) and [OroPay](../../../../../integrations/payment-integration/oropay/index.md#user-guide-payment-oropay) are supported. Ensure that a Stripe integration or OroPay is configured under *System > Manage Integrations* before selecting it here.
4. Click **Save Settings**.

* [Invoices in the Storefront](../../../../../../../storefront/account/invoices/index.md#frontstore-guide-invoices)
* [Invoices in the Back-Office](../../../../../../sales/invoices/index.md#user-guide-sales-invoices)
* [Stripe Integration Element](../../../../../integrations/payment-integration/stripe/index.md#user-guide-payment-payment-providers-stripe-element)
* [OroPay Integration](../../../../../integrations/payment-integration/oropay/index.md#user-guide-payment-oropay)

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
