<a id="user-guide-zendesk-integration"></a>

<a id="user-guide-zendesk-channel-integration-synchronization"></a>

# Configure Zendesk Integration in the Back-Office

Oro applications support out of the box integration with Zendesk, enabling you to load data from your Zendesk account and process it in the Oro application. This article describes how to define and edit the integration and synchronization settings.

#### HINT
While Zendesk integration capabilities are pre-implemented, Oro application can be integrated with different third-party systems.

## Generate API token in Zendesk

To retrieve your API token on the Zendesk side:

1. Open your account profile.
2. Click on the cog icon in the panel to the left to open the **Admin** menu.
   ![image](user/img/system/integrations/zendesk/zendesk_admin.png)

1. Navigate to the **Apps & Integrations > API Configuration**.
   ![image](user/img/system/integrations/zendesk/zendesk_api.png)
2. Make sure the **Token Access** is enabled.
3. Click on API Tokens in the panel to the left to open the API Tokens page.
4. Click **Add API Token** to create a new one.
   ![image](user/img/system/integrations/zendesk/zendesk_api_token.png)
5. Provide a description for the new token, and click **Save**. This will prompt generation of a new token.
   ![image](user/img/system/integrations/zendesk/new-token.png)
6. Copy and store this the token as you will need it to connect to the OroCommerce application. Please be aware that it will not be shown again after you click **Save**.

## Create the Integration

To create an integration with Zendesk:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu:
2. Click **Create Integration** on the top right.
3. On the **Create Integration** page, set the integration type to **Zendesk**
4. In the **General** section, define the following mandatory details:

   | Field                          | Description                                                                                                                                                                                                                |
   |--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Type\***                     | The integration type. Must be set to **Zendesk**                                                                                                                                                                           |
   | **Name\***                     | The integration name used to refer to the integration within the system.                                                                                                                                                   |
   | **URL\***                      | A URL of your Zendesk account (e.g., `https://username.zendesk.com`).                                                                                                                                                      |
   | **API Email\***                | The email used to register your Zendesk account.                                                                                                                                                                           |
   | **API Token\***                | The API token generated and/or copied in the Zendesk (as described above).                                                                                                                                                 |
   | **Default Zendesk User Email** | User with this email will be assigned tickets that come from the Oro application and for which<br/>there are no Zendesk users with a matching email address.                                                               |
   | **Owner**                      | Limits the list of users that can manage the integration, subject to the access and permission settings<br/>etc.) Used as an Oro application user for Zendesk tickets if there are no users with a matching email address. |
5. In the **Synchronization Settings** section, enable/disable the two-way synchronization.

   Select the **Enable Two Way Sync** checkbox, if you want to download data both from Zendesk to your Oro application and back.

   If the box is left unselected, data from Zendesk is loaded into the Oro application, but changes performed within it are not loaded back into Zendesk.
6. If the two-way synchronization is enabled, define the priority used for the conflict resolution (e.g., if the same customer details were edited from both Oro application and Zendesk):
   * **Remote wins** — Zendesk data is applied to both Zendesk and the Oro application.
   * **Local wins** — Oro application data is applied to both Zendesk and the Oro application.

#### NOTE
In the **Synchronization Settings** section, select the **Log Warnings** checkbox if you want all synchronization errors to be written into the application log.

<a id="user-guide-zendesk-channel-integration-details-edit"></a>

## Manage the Integration

As an illustration, we have created a sample Zendesk integration with two-way synchronization enabled and sync priority set to **Remote Wins**. This means that if the same data is changed from both Zendesk and Oro application, Zendesk changes take precedence.

![image](user/img/system/integrations/zendesk/zendesk_create.png)

Initially the integration is inactive. In order to activate it, click **Activate** on the integration details page.

#### NOTE
To edit, deactivate, schedule sync or delete the integration, navigate to the page with all integrations **System > Integrations > Manage Integrations**.

![image](user/img/system/integrations/zendesk/zendesk_edit.png)

<a id="user-guide-zendesk-channel-start-synchronization"></a>

## Synchronize Data

Once integration has been created, the data is automatically synchronized.

To start the synchronization manually:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. For the integration with Zendesk, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right and click <i class="fas fa-sync-alt" aria-hidden="true"></i> to schedule sync.

#### NOTE
Alternatively, open the integration details page and click **Schedule Sync** on the top right.

1. Wait for data to synchronize. Click the **Check progress** link to see the synchronization status.

### Sync from Zendesk to the Oro Application

A new case is created in the Oro application for every Zendesk ticket. The ticket fields are mapped in the Oro application case fields as
follows:

| Zendesk Field   | Oro application case field   | Comments                                                                                                                                                                                                                                                                                                                                              |
|-----------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Subject         | Subject                      | Can be used to find the ticket/case in the grid                                                                                                                                                                                                                                                                                                       |
| Description     | Description                  | Is also added as the first public comment for both the Oro case and the Zendesk ticket                                                                                                                                                                                                                                                                |
| Assignee        | Assigned to                  | The email address of the assignee is checked against primary emails of the Oro application [User](../../../glossary.md#term-User)<br/>records:<br/><br/>> - If there is a matching email, the user is mapped to the **Assignee** field value.<br/>> - If there is no matching email, the integration owner is mapped to the **Assignee** field value. |
| Priority        | Priority                     | The values are mapped as follows:<br/><br/>| Zendesk   | Oro application   |<br/>|-----------|-------------------|<br/>| Low       | Low               |<br/>| Normal    | Normal            |<br/>| High      | High              |<br/>| Urgent    | High              |                                                                            |
| Status          | Status                       | The values are mapped as follows:<br/><br/>| Zendesk   | Oro application   |<br/>|-----------|-------------------|<br/>| New       | Open              |<br/>| Open      | Open              |<br/>| Pending   | In progress       |<br/>| Solved    | Closed            |                                                                            |
![image](user/img/system/integrations/zendesk/example_ticket.png)

For each case created as a result of synchronization with Zendesk, a ticket is created in the Oro application.

The following field values are defined as follows:

| Oro Application Ticket Field   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ticket Number                  | Zendesk ticket number. Used to<br/>determine if an existing case/ticket must  be updated or if a new one must be created.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Recipients Email               | Same as the **Recipients Email** field in the Zendesk ticket.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Status                         | Same as the **Status** field in the Zendesk ticket.(Does not map to the Oro application statuses).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Type                           | Same as the **Type** field in the Zendesk ticket.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Submitter                      | A contact or user. There are two possible cases:<br/><br/>- If the ticket has been submitted to Zendesk by an end user (e.g., by email or from Facebook) an<br/>  Oro application [Contact](../../../glossary.md#term-Contact) record is tied to it, as follows:<br/>  - The email address of the end user is checked against primary emails of Oro [Contact](../../../glossary.md#term-Contact) records:<br/>    - If there is a matching email, the contact is mapped to the **Submitter** field value.<br/>    - If there is no matching email, a new contact is created and mapped to the **Submitter** field value.<br/>  - The mapped Oro contact name and the link to it are displayed as a value for the **Submitter** field in the ticket<br/>    created in the Oro application.<br/><br/>    (So, for example, if the ticket was submitted by user ‘DreamWorks Founder’ in Zendesk and the user’s email<br/>    matches the email of the Oro application Contact ‘Steven Spielberg,’ the **Submitter** field in the ticket will be<br/>    filled with the value ‘Steven Spielberg’).<br/>- If the ticket has been submitted to Zendesk by an agent or administrator, Oro [User](../../../glossary.md#term-User) record<br/>  is tied to it, as follows:<br/>  - The email address of the submitter is checked against primary emails of the Oro application [User](../../../glossary.md#term-User) records:<br/>    - If there is a matching email, the user is mapped to the **Submitter** field value.<br/>    - If there is no matching email, the integration owner is mapped to the **Submitter** field value. |
| Assignee                       | The email address of the assignee is checked against primary emails of the Oro application [User](../../../glossary.md#term-User) records:<br/><br/>> - If there is a matching email, the user is mapped to the **Assignee** field value.<br/>> - If there is no matching email, the integration owner is mapped to the **Assignee** field value.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Requester                      | An Oro application [Contact](../../../glossary.md#term-Contact) record is tied to it, as follows:<br/><br/>- The email address of the requester in Zendesk is checked against primary emails of the Oro application [Contact](../../../glossary.md#term-Contact) records:<br/>  - If there is a matching email, the contact is mapped to the **Requester** field value.<br/>  - If there is no matching email, a new contact is created and mapped to the **Requester** field value.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Priority                       | Same as the **Priority** field of the Zendesk ticket (Does not map to the Oro priorities).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Problem                        | Same as the **Problem** field in the Zendesk ticket.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Collaborators                  | Same as the **Collaborators** field in the Zendesk ticket.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

### Sync from the Oro Application to Zendesk

If two-way synchronization is enabled, the **Publish to Zendesk** button is available on the Case details page. Click the button to submit the case to Zendesk.

The case fields are mapped to the Zendesk ticket fields as follows:

| Oro case field   | Zendesk field   | Comments                                                                                                                                                                                                                                                                                          |
|------------------|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Subject          | Subject         | Can be used to find the ticket/case in the grid                                                                                                                                                                                                                                                   |
| Description      | Description     | Is also added as the first public comment for the both Oro case and Zendesk ticket                                                                                                                                                                                                                |
| Assigned to      | Assignee        | The email address of the *Assigned to* user is checked against the emails of Zendesk<br/>users:<br/><br/>> - If there is a matching email, the ticket is assigned to the related user.<br/>> - If there is no matching email, the ticket is assigned to the user with default Zendesk user email. |
| Priority         | Priority        | The values are mapped as follows:<br/><br/>| Oro application   | Zendesk   |<br/>|-------------------|-----------|<br/>| Low               | Low       |<br/>| Normal            | Normal    |<br/>| High              | High      |                                                              |
| Status           | Status          | The values are mapped as follows:<br/><br/>| Oro application   | Zendesk   |<br/>|-------------------|-----------|<br/>| Open              | Open      |<br/>| In progress       | Pending   |<br/>| Resolved          | Solved    |<br/>| Closed            | Solved    |                        |
- After the ticket has been created in Zendesk, its details are saved in the Ticket related to the case in the Oro application.

### Review Further Sync Rules

- If some ticket details of a Zendesk ticket have been changed after the initial synchronization, the corresponding
  Oro application case details will also be updated in the course of the nearest synchronization.
- If some ticket details of an Oro application case have been changed after the initial synchronization, the corresponding
  Zendesk ticket details will also be updated automatically (if the two-way synchronization is enabled).
- If the same details have been updated in a related Zendesk ticket and Oro application case, and the two-way synchronization is
  enabled, the synchronization priority settings will be applied.

<!-- stop -->
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
