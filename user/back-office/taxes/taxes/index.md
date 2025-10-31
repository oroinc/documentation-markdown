<a id="user-guide-taxes-tax-rates"></a>

# Manage Taxes (Tax Rates) in the Back-Office

<!-- begin -->

#### HINT
This section is part of the [Tax Management](../../../concept-guides/administration/taxes/index.md#concept-guide-taxes) concept guide that provides a general understanding of the tax configuration and management in OroCommerce.

Tax or tax rate is a particular percentage of tax with unique identifier and description that helps you associate the tax rate with other tax components using [tax rules](../tax-rules/index.md#tax-rules).

## Create a Tax Rate

To create a new tax rate:

1. Navigate to **Taxes > Taxes** in the main menu.
2. Click **Create Tax**.
3. Fill in **Code**, **Description**, and **Rate (%)**.
4. Click **Save and Close**.

## Manage Tax Rates

To view all tax rates, navigate to **Taxes > Tax Rates** in the main menu.

![The page of all available tax rates](user/img/taxes/tax_rates_all.png)

#### NOTE
To handle big a volume of data, use the page switcher, increase *View Per Page* or use filters to narrow down the list to just the codes you need.

In the tax rate list, you will find the information about the tax rates’ codes (unique identifier), detailed description, and the dates when the tax rate was created and updated.

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> to open its details page, <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to edit, or  ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) to remove the tax rate.

### View Tax Rate Details

To view tax rate details:

1. Navigate to **Taxes > Taxes** in the main menu.
2. Find the line with the necessary tax rate and click on it to open its details page.

You can <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** or ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** the tax rate by clicking the required button on the top right.

### Edit a Tax Rate

To edit the tax rate code, description, and rate:

1. Navigate to **Taxes > Taxes** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details.
3. Update the **Code**, **Description**, and **Rate (%)** with new information about the tax rate.
4. Click **Save and Close**.

## Link a Tax Rate to the Tax Rule

You can edit the association of the tax rate with other tax components when [editing the tax rule details](../tax-rules/index.md#tax-rules-edit) (see the respective topic for more information).

## Export Tax Rates

You might need to export the necessary tax rate details, download it as a .csv file, and reuse it in the third-party systems.

Another scenario for using export is when you plan bulk data update that is easily automated in the spreadsheet software.

To export the tax rates in a .csv format:

1. In the main menu, navigate to **Taxes > Taxes**.
2. Click **Export** on the top right.
3. Once the export is complete, you will receive an email to download the .csv file.

## Import Tax Rates

**Import File** option helps import a large bulk of tax information into the tax list using the .csv file.

**Example of tax bulk import template**

| Code                         | Description   |   Rate |
|------------------------------|---------------|--------|
| LOS_ANGELES_COUNTY_SALES_TAX | Sales Tax     |   0.09 |

To import a bulk of tax information:

1. In the main menu, navigate to **Taxes > Taxes**. The tax list opens.
2. Click **Import File** on the top right.
3. **Prepare data for import**: Create your bulk information in the .csv format. Once your file is ready, click **Choose File**, select the prepared comma-separated values (.csv) file, and click **Import File**.

#### NOTE
Ensure that your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly.

![The steps that are necessary to perform to import the taxes successfully](user/img/taxes/import_taxes.png)
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
* [Tax Rules](../tax-rules/index.md#tax-rules)
* [Tax Jurisdictions](../tax-jurisdictions/index.md#taxes-tax-jurisdiction)
* [Customer Tax Codes](../customer-tax-codes/index.md#user-guide-taxes-customer-tax-codes)
* [Product Tax Codes](../product-tax-codes/index.md#taxes-product-tax-code)

<!-- finish -->
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
