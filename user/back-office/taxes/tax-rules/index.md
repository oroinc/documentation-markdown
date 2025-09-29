<a id="tax-rules"></a>

# Manage Tax Rules in the Back-Office

<!-- begin -->

#### HINT
This section is part of the [Tax Management](../../../concept-guides/taxes/index.md#concept-guide-taxes) concept guide that provides a general understanding of the tax configuration and management in OroCommerce.

Tax rules help OroCommerce find the correct tax rate that should be used for the products listed in the purchase order by matching the product tax code that indicates:

* Tax status of the product
* Customer tax code that indicates the tax status of the buying company
* Tax jurisdiction where the tax is due

The sections below provide guidance on how to create and manage tax rules.

## Create a Tax Rule

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-tax-rules" target="_blank">how to create tax rules in OroCommerce</a> or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ma0JOwn9VVs" frameborder="0" allowfullscreen></iframe>

To create tax rules for a particular tax jurisdiction, you need to complete the configuration of the tax options described in the [Tax Rule Prerequisites](../index.md#tax-rule-prerequisites) section.

Once all the necessary actions are performed, you need to create a tax rule for every valid combination of the tax rates, product types, and customer types to ensure that they are properly taxed at every checkout.

1. Navigate to **Taxes > Tax Rules** and click **Create Tax Rule**.
   ![Create a new tax rule](user/img/taxes/tax_rules_create.png)
2. Select a customer and a product tax codes in the respective fields.
3. Select a tax jurisdiction in the **Tax Jurisdiction** field and a tax rate in the **Tax** field.
4. Describe this tax rule if necessary in the **Description** field.
5. Click **Save and Close**.

## Manage Tax Rules

To view all tax rules, navigate to **Taxes > Tax Rules** in the main menu.

![The list of all available tax rules](user/img/taxes/all_tax_rules.png)

#### NOTE
To handle a big volume of data, use the page switcher, increase *View Per Page* or use filters to narrow down the list to just the codes you need.

In the tax rules list, you will find the information about customer and product tax codes, tax jurisdiction, and tax rates that are linked to the tax rules, detailed description, and the dates when the tax rule was created and updated.

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> to open its details page, <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to edit, or  <i class="fas fa-trash-alt" aria-hidden="true"></i> to remove the tax rule.

### View Tax Rule Details

To view tax rule details:

1. Navigate to **Taxes > Tax Rules** in the main menu.
2. Find the line with the necessary tax rule and click on it to open its details page.
   ![View the tax rule details](user/img/taxes/tax_rules_view.png)

You can <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** or <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** the tax rule by clicking the required button on the top right.

<a id="tax-rules-edit"></a>

### Edit a Tax Rule

To edit the tax rule:

1. Navigate to **Taxes > Tax Rules** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details.
3. Update the links between the tax rule and the tax rule components (a tax rate, a tax jurisdiction, a customer tax code, and a product tax code) to modify the tax rule.
4. Click **Save and Close**.

## Export Tax Rules

You might need to export the necessary tax rule details, download it as a .csv file, and reuse it in the third-party systems.

Another scenario for using export is when you plan bulk data update that is easily automated in the spreadsheet software.

To export the tax rules in a .csv format:

1. In the main menu, navigate to **Taxes > Tax Rules**.
2. Click **Export** on the top right.
3. Once the export is complete, you will receive an email to download the .csv file.

## Import Tax Rules

**Import File** option helps import a large bulk of tax rules information into the tax rules list using the .csv file.

**Example of tax rules bulk import template**

| Customer Tax Code Code   | Product Tax Code Code   | Tax Jurisdiction Code   | Tax Code                     |
|--------------------------|-------------------------|-------------------------|------------------------------|
| NON_EXEMPT               | TAXABLE_ITEMS           | LOS_ANGELES_COUNTY      | LOS_ANGELES_COUNTY_SALES_TAX |

To import a bulk of tax rules information:

1. In the main menu, navigate to **Taxes > Tax Rules**. The tax rule list opens.
2. Click **Import File** on the top right.
3. **Prepare data for import**: Create your bulk information in the .csv format. Once your file is ready, click **Choose File**, select the prepared comma-separated values (.csv) file, and click **Import File**.

#### NOTE
Ensure that your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly.

![The steps that are necessary to perform to import the tax rules successfully](user/img/taxes/import_tax_rules.png)
1. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
2. **Launch import:** After successful validation, click **Import File**.
3. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. Additionally, an email message with the import status is delivered to your mailbox.

Follow the on-screen guidance for any additional actions. For example, for the inventory template, select one of the options: a) inventory statuses only or b) detailed inventory levels.

<iframe width="560" height="315" src="https://www.youtube.com/embed/p5HrsdMUB7A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<!-- finish -->

**Related Articles**

* [Taxes](../index.md#user-guide-taxes)
* [Customer Tax Codes](../customer-tax-codes/index.md#user-guide-taxes-customer-tax-codes)
* [Product Tax Codes](../product-tax-codes/index.md#taxes-product-tax-code)
* [Tax Jurisdictions](../tax-jurisdictions/index.md#taxes-tax-jurisdiction)
* [Tax Rates](../taxes/index.md#user-guide-taxes-tax-rates)

<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
