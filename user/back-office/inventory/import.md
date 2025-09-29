<a id="import-inventory-levels"></a>

# Import Inventory Levels and Statuses

When your need your Oro application and other systems (like asset management and accounting software) exchange and synchronize product inventory information, you may transfer the inventory data from and into the Oro application in the .csv format.

#### HINT
This section is part of the [Data Import](../../concept-guides/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

## Inventory Statuses and Levels

**Import File** option helps import the product inventory statuses (*In Stock*, *Out of Stock*, or *Discontinued*) and levels (quantity and unit) for the warehouses using the .csv file that follows the inventory details data structure.

**Example of inventory levels bulk import template**

| SKU       | Product      | Inventory Status   | Warehouse       |   Quantity | Unit   |
|-----------|--------------|--------------------|-----------------|------------|--------|
| product.1 | Product Name | In Stock           | First Warehouse |         50 | kg     |

#### HINT
* Inventory status should be *In Stock*, *Out of Stock*, or *Discontinued*.
* The warehouse and unit should be created prior to the inventory levels import.

To import a bulk of inventory levels or statuses:

1. In the main menu, navigate to **Inventory > Manage Inventory**. The inventory levels list opens.
2. Click **Import File** on the top right.
3. In the **Import** dialog, click **Choose File**, select the .csv file you prepared, and then click **Import File**.

#### NOTE
Ensure that your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly.

![image](user/img/inventory/import_inventory_levels.png)

1. Click **Export Template** to download a sample .csv file with the necessary headers.
2. **Prepare data for import**: Based on the downloaded file, create your bulk information in the .csv format. Once your file is ready, click **Choose File**, select the prepared comma-separated values (.csv) file, and click **Import File**.
3. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
4. **Launch import:** After successful validation, click **Import File**.
5. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. Additionally, an email message with the import status is delivered to your mailbox.

Follow the on-screen guidance for any additional actions. For example, for the inventory template, select one of the options: a) inventory statuses only or b) detailed inventory levels.

<iframe width="560" height="315" src="https://www.youtube.com/embed/p5HrsdMUB7A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<!-- finish -->

<a id="import-inventory-status"></a>

## Inventory Statuses Only

**Import File** option helps import the global product inventory statuses (*In Stock*, *Out of Stock*, or *Discontinued*) using the .csv file that follows the high-level inventory details data structure.

**Example of inventory statuses bulk import template**

| SKU       | Product      | Inventory Status   |
|-----------|--------------|--------------------|
| product.1 | Product Name | In Stock           |

#### NOTE
Inventory status should be *In Stock*, *Out of Stock*, or *Discontinued*.

Inventory status import process is similar to the [inventory level](#import-inventory-levels) import.
