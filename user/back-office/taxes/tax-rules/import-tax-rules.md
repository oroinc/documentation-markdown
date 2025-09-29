<a id="import-tax-rules"></a>

# Import Tax Rules

#### HINT
This section is part of the [Data Import](../../../concept-guides/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

<!-- start -->

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
