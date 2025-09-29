<a id="sales-import-leads"></a>

# Import Leads

#### HINT
This section is part of the [Data Import](../../../concept-guides/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

You can import the bulk details of updated or processed leads information in the .csv format following the steps below.

1. In the main menu, navigate to **Sales > Leads**.
2. Click **Import File** on the top right.
3. In the **Import** dialog, click **Choose File**, select the .csv file you prepared, and then click **Import File**.

#### NOTE
Ensure that your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly.

![The steps you need to take to import leads](user/img/sales/leads/import_leads.png)

1. Click **Export Template** to download a sample .csv file with the necessary headers.
2. **Prepare data for import**: Based on the downloaded file, create your bulk information in the .csv format. Once your file is ready, click **Choose File**, select the prepared comma-separated values (.csv) file, and click **Import File**.
3. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
4. **Launch import:** After successful validation, click **Import File**.
5. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. Additionally, an email message with the import status is delivered to your mailbox.

**Example of leads bulk import template**

|   ID | Lead Name   | Name prefix   | First name   | Last Name   | Status Id   | Company name   | Address 1 Label   | Twitter   | LinkedIn   | Owner Username   |
|------|-------------|---------------|--------------|-------------|-------------|----------------|-------------------|-----------|------------|------------------|
|  111 | Gov Mart    | Mr            | Jerry        | Coleman     | new         | Gov Mart       | Primary Address   | @Jerry    | LinkedInID | Jerry            |
