<a id="admin-guide-data-audit"></a>

<a id="user-guide-data-audit"></a>

# Configure Data Audit in the Back-Office

Data Audit enables you to see the full history of changes made to any entity and its fields that have been marked as *auditable*, and create out-of-the-box reports based on these changes.

## Mark an Entity as Auditable

Marking a particular entity as auditable defines whether the system logs the actions performed to this entity and who performed these actions.

To mark an entity as auditable:

1. Navigate to **System Configuration > Entities > Entity Management** in the main menu.
2. Locate the required entity and open its edit page.

   #### HINT
   To save time looking for the entity, use filters at the top of the record table.

   ![Select an entity to edit](img/backend/architecture/select_entity_for_data_audit.png)
3. In the **Other** section, set the *Auditable* field to **Yes**.
   ![Setting the Auditable field of the entity to Yes](img/backend/architecture/auditable_field.png)

   #### HINT
   For more information on entities, see the [Create an Entity](../entities/manage-entities.md#doc-entity-actions-create) topic.
4. Click **Save and Close**.

## View Entity Change History

You can monitor changes to auditable entities on their view and edit pages by clicking on the **Change History** link on the top right.

The history includes the author and the time of the change, and the difference between the previous and the new version.

![Changed history of the customer entity](img/backend/architecture/changed_history.png)

Make sure that the entity field of the entity are also marked as auditable if you want to track the history of its changes. For instance, if the *newArrival* entity field of the *Product* entity has the *Auditable* field set to *No*, then no changes made to this field are going to be tracked.

![Auditable column for entity fields](img/backend/architecture/entity_fields_auditable.png)

To set an entity field as *Auditable*:

1. Open its edit page.
2. In the **Back-Office options** section, select **Yes** from the dropdown list for the *Auditable* field.
   ![Set an entity field as auditable](img/backend/architecture/set_entity_field_to_auditable.png)

   For instance, once we made the *newArrival* field as auditable, any changes to this field have become traceable, as illustrated in the screenshot below:
   ![Change history of a product](img/backend/architecture/change_history_for_product.png)

## Create a Data Audit Report

You can create reports based on the changes that have taken place in auditable entities.

As an illustration, we are going to create a report of products that have been discontinued this year, i.e., the items that have **Inventory Status** changed to *Discontinued*.

#### HINT
First, make sure that the *Inventory Status* entity field is auditable.

1. Navigate to **Reports & Segments > Manage Custom Reports**.
2. Click **Create Report**
3. Provide the following key details in the **General** section:
   * Name — Give the report a name.
   * Entity — Select *Product* for entity type.
   * Report Type — Select *Table*.
4. In **Filters**, drag and drop the **Data Audit** field to the area on the right.
5. Set the following conditions:
   * Product > Inventory Status
   * Has been changed to > is any of > Discontinued
   * Interval equals > today

   > ![Data audit report](img/backend/architecture/data_audit_report.png)
6. Add the following columns to the table:
   * SKU
   * Inventory Status
   * Created At
   * Update At
7. Click **Save and Close**.
   > ![Data audit report generated](img/backend/architecture/data_audit_report_generated.png)

## View Changes of Auditable Entities

All changes made to auditable entities and fields are logged into the system and saved under **System > Data Audit**. You can filter the table by required parameters and save the filtered page for future reference.

> ![Data audit grid under System > Data Audit](img/backend/architecture/data_audit_grid.png)

The report grid contains the following columns:

| Name         | Description                                                                                                                                                         |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ACTION       | Defines the action that has been performed with the [record](../../../glossary.md#term-Record). You can see if the record has been<br/>created, updated or removed. |
| VERSION      | Corresponds to the consecutive number of changes performed with the specific record.                                                                                |
| ENTITY TYPE  | Type of the [entity](../../../glossary.md#term-Entity) to which the record belongs.                                                                                 |
| ENTITY NAME  | Name of the specific record tracked.                                                                                                                                |
| ENTITY ID    | ID of the entity to which the record belongs.                                                                                                                       |
| DATA         | Details of the change.                                                                                                                                              |
| AUTHOR       | Name and email of the [user](../../../glossary.md#term-User) that has performed the change.                                                                         |
| ORGANIZATION | [Organization](../../../glossary.md#term-Organization), within which the change has been performed.                                                                 |
| LOGGED AT    | Date and time when the event was logged.                                                                                                                            |

## Audit of Login Attempts

#### NOTE
This is a Platform Enterprise feature.

To simplify investigation of any security-related incidents, the application keeps track of all back-office login attempts and the following related security events:

* Successful login
* Unsuccessful login
* Account is locked
* Autodeactivation email has been sent
* Reset password email has been sent

The log is stored in the *security* log channel.

![Record login details in a database table](user/img/system/data_audit/oro_logger_log_entry.png)

In addition to the type of the security event, the following details are recorded in the table:

* user ID
* username
* email
* full name
* user status (enabled or disabled)
* last login date and time
* user creation date and time
* IP address

Login attempts can be accessed from the back-office UI. See [Login Attempts UI](../user-management/login-attempts/index.md#user-guide-user-management-login-attempts) for more information.

**Related Topics**

* [Entity Management](../entities/index.md#entities-management)
* [Reports](../../reports-segments/reports/index.md#user-guide-reports)
