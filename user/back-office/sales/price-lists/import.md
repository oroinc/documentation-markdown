<a id="import-price-lists"></a>

# Import Prices Into the Price List

#### HINT
This section is part of the [Data Import](../../../concept-guides/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

**Import File** option helps import a large bulk of product prices into the price list using the .csv file.

**Example of prices bulk import template**

| Product SKU   |   Quantity | Unit Code   |   Price | Currency   |
|---------------|------------|-------------|---------|------------|
| sku_001       |         42 | kg          |     100 | USD        |

#### NOTE
The unit and currency should be created before the inventory levels import.

To import a bulk of product prices:

1. In the main menu, navigate to **Sales > Price Lists** and click the necessary price list to open its details.
2. Click **Import File** on the top right.
3. Click **Choose File** and select the .csv file you prepared.

<!-- note: Ensure your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly. -->
1. Click **Download Import Template** to download a sample .csv file with the necessary headers.
2. **Prepare data for import**: Create your bulk information in the .csv format based on the downloaded file. Once your file is ready, click **Choose File** and select the prepared comma-separated values (.csv) file.
3. Select the strategy for uploading the file:
   * **Add and Replace** strategy overrides the existing prices with the ones mentioned in the file for the corresponding product item. Also, it adds new prices to the products with empty values.
   * **Reset and Add** strategy removes all the existing prices and adds only the ones listed in the .csv file.
     ![The steps you need to take to import prices to price lists](user/img/sales/pricelist/import_price_list.png)
4. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
5. **Launch import:** After successful validation, click **Import File**.
6. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. An email message with the import status is also delivered to your mailbox.

Follow the on-screen guidance for any additional actions. For example, select one option for the inventory template: a) inventory statuses only or b) detailed inventory levels.

<iframe width="560" height="315" src="https://www.youtube.com/embed/p5HrsdMUB7A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<!-- finish -->
