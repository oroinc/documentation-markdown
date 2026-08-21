<a id="admin-guide-data-audit"></a>

<a id="user-guide-data-audit"></a>

# Configure Data Audit in the Back-Office

Data Audit shows the full history of changes made to an entity and its fields, provided the entity and the fields are marked as **auditable**. Data Audit also enables you to see the changes made to any configuration setting at any of the six levels: system (global), organization, website, customer group, customer, and user (My Configuration). You can also build reports based on these changes.

![Data audit grid under System > Data Audit](user/img/system/data_audit/all-audits.png)

All changes made to auditable entities, their fields, and configuration settings appear under **System > Data Audit** in the back-office main menu. You can filter this table by the criteria you need. You can also save the filtered view for future reference.

The report grid contains the following columns:

| Name         | Description                                                                                                                                                                                                                                                                                                                                                           |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ACTION       | The kind of change made to the record: created, updated, or removed.<br/><br/>> * **Create** — The record received a value for the first time. Before this change, the record used its default value.<br/>> * **Update** — An existing custom value was replaced with another custom value.<br/>> * **Remove** — The record was reset to its default or parent value. |
| VERSION      | The sequential number of the change made to the specific record.                                                                                                                                                                                                                                                                                                      |
| ENTITY TYPE  | The type of the entity to which the entity record belongs. For configuration settings, the type shows the configuration level at which the change occurred, for example *Configuration: System*, *Configuration: Website*, or *Configuration: User*, etc.                                                                                                             |
| ENTITY NAME  | The name of the specific record that changed.                                                                                                                                                                                                                                                                                                                         |
| ENTITY ID    | The ID of the entity to which the record belongs.                                                                                                                                                                                                                                                                                                                     |
| DATA         | For **entities and entity fields**, DATA displays the details of the change made to the entity. For **configuration settings**, DATA displays the location of the changed setting, followed by its old and new values. The location is shown as a path, for example *Commerce › Product › Promotions › New Arrivals › Maximum Items*.                                 |
| AUTHOR       | The name and email address of the user who made the change.                                                                                                                                                                                                                                                                                                           |
| ORGANIZATION | Organization in which the change was made.                                                                                                                                                                                                                                                                                                                            |
| LOGGED AT    | The date and time when the event was logged.                                                                                                                                                                                                                                                                                                                          |

Use filters to find the required audit record. Use the **Data** filter to search a match in the name of the changed entity or setting (within old and new values) or its location.

## Mark an Entity as Auditable

Marking an entity as *auditable* tells the system to log every change made to the entity, together with the name of the user who made the change.

To mark an entity as auditable:

1. Navigate to **System Configuration > Entities > Entity Management** in the main menu.
2. Locate the required entity and open its edit page.

   #### HINT
   To save time looking for the entity, use filters at the top of the record table.

   ![Select an entity to edit](user/img/system/data_audit/select_entity_for_data_audit.png)
3. In the **Other** section, set the *Auditable* field to **Yes**.
   ![Setting the Auditable field of the entity to Yes](user/img/system/data_audit/auditable_field.png)

   #### HINT
   For more information on entities, see the [Create an Entity](../entities/manage-entities.md#doc-entity-actions-create) topic.
4. Click **Save and Close**.

## Mark an Entity Field as Auditable

Marking an entity as auditable does not automatically track its fields. For instance, if the **newArrival** entity field of the *Product* entity has the *Auditable* field set to **No**, then no changes made to this field are going to be tracked.

![Auditable column for entity fields](user/img/system/data_audit/entity_fields_auditable.png)

To set an entity field as *Auditable*:

1. Open its edit page.
2. In the **Back-Office options** section, select **Yes** from the drop-down list for the *Auditable* field.
   ![Set an entity field as auditable](user/img/system/data_audit/set_entity_field_to_auditable.png)

For instance, once you made the *newArrival* field as auditable, any changes to this field have become traceable, as illustrated in the screenshot below:

> ![Change history of a product](user/img/system/data_audit/change_history_for_product.png)

## View Entity Change History

You can review the change history of an auditable entity on its view or edit page. Click **Change History** in the top-right corner of the page to open it.

The history includes the author and the time of the change, and the difference between the previous and the new values.

![Changed history of the customer entity](user/img/system/data_audit/changed_history.png)

Make sure that both the entity and entity fields are marked as **Auditable** if you want to track the history of its changes.

## View Configuration Settings Changes

Data Audit also tracks changes to configuration settings, not only to entities. This tracking works automatically for every setting, so you do not need to mark individual settings as *auditable*.

The application can store configuration settings at up to six levels: system (global), organization, website, customer group, customer, and user (My Configuration).

Whenever someone changes a configuration setting at any of these levels, the application creates an audit record for that change. You can find this record on the same **System > Data Audit** page that lists entity changes.

![Configuration settings changes audit grid under System > Data Audit](user/img/system/data_audit/all-audits-config-settings.png)

If a single save changes several settings at once, the application creates one audit record for all of them. When the record mixes different kinds of change, for example one setting was created and another was updated, the application labels the entire record as **Update**.

![Configuration settings changes audit grid with multiple settings changes in one record](user/img/system/data_audit/multiple-config-settings.png)

Use the **Data** filter to find a match in the name of the changed setting or its location, for example *User Login* or *always_require*.

#### IMPORTANT
If a setting stores **sensitive information**, such as a password or a client secret, the application does not display its value in the audit record. Instead, the record shows `***`. You can still see who changed the setting and when they changed it.

![Audit grid displaying changes to settings with sensitive information via ***](user/img/system/data_audit/all-audits-sensitive-info.png)

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
