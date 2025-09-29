<a id="import-taxes"></a>

# Import Taxes Rates

#### HINT
This section is part of the [Data Import](../../../concept-guides/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

<!-- start -->

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
