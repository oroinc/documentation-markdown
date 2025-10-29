<a id="import-contacts"></a>

# Import Contacts

#### HINT
This section is part of the [Data Import](../../../concept-guides/administration/data-import/index.md#concept-guide-data-import) concept guide topic that provides guidelines on import operations in Oro applications.

<!-- start -->

**Import File** option helps import a large bulk of contact information into the contact list using the .csv file.

**Example of contact bulk import template**

|   ID | Name prefix   | First name   | Last name   | Gender   | Birthday   | Owner Username   |
|------|---------------|--------------|-------------|----------|------------|------------------|
|  111 | Mr.           | Jerry        | Coleman     | male     | 03-07-1973 | james.valenzuela |

To import a bulk of contacts:

1. In the main menu, navigate to **Customers > Contacts**.
2. Click **Import File** on the top right.
3. Click **Choose File** and select the .csv file you prepared.

#### NOTE
Ensure that your .csv file is saved in the Unicode (UTF-8) encoding. Otherwise, the content of the file can be rendered improperly.

1. Click **Download Import Template** to download a sample .csv file with the necessary headers.
2. **Prepare data for import**: Based on the downloaded file, create your bulk information in the .csv format. Once your file is ready, click **Choose File** and select the prepared comma-separated values (.csv) file.
3. Select the strategy for uploading the file:
   * **Add and Replace** strategy overrides the existing contact information with the new one from the imported file.
   * **Add** strategy adds new contacts from the .csv file to the existing list.

   ![The steps you need to take to import contacts](user/img/customers/contacts/import_contacts.png)
4. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
5. **Launch import:** After successful validation, click **Import File**.
6. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. Additionally, an email message with the import status is delivered to your mailbox.

Follow the on-screen guidance for any additional actions. For example, for the inventory template, select one of the options: a) inventory statuses only or b) detailed inventory levels.

<iframe width="560" height="315" src="https://www.youtube.com/embed/p5HrsdMUB7A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<!-- finish -->
