<a id="import-business-customers"></a>

# Import Business Customers

#### HINT
This section is part of the [Data Import](../../../concept-guides/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

<!-- start -->

**Import File** option helps import a large bulk of information on business customers using the .csv file.

To import a bulk of business customers:

1. In the main menu, navigate to **Customers > Business Customers**.
   ![Import business customers](user/img/customers/business_customers/import_bc.png)
2. Click **Import File** on the top right.
3. Click **Choose File** and select the .csv file you prepared.

#### NOTE
Ensure that your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly.

1. Click **Export Template** to download a sample .csv file with the necessary headers.
2. **Prepare data for import**: Based on the downloaded file, create your bulk information in the .csv format. Once your file is ready, click **Choose File** and select the prepared comma-separated values (.csv) file.
3. Select the strategy for uploading the file:
   * **Add and Replace** strategy overrides the existing information with the new one from the imported file.
   * **Add** strategy adds new business customers from the .csv file to the existing list.
4. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
5. **Launch import:** After successful validation, click **Import File**.
6. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. Additionally, an email message with the import status is delivered to your mailbox.
