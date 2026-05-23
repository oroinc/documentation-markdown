<a id="user-guide-zendesk-integration"></a>

<a id="user-guide-zendesk-channel-integration-synchronization"></a>

# Configure Zendesk Integration in the Back-Office

Oro applications support out-of-the-box integration with Zendesk, enabling you to load data from your Zendesk account and process it in the Oro application.

OroCommerce supports two authentication methods for Zendesk integration:

* **Basic** — authenticate using a Zendesk account email and API token.
* **OAuth** — use OAuth 2.0 for secure, delegated authorization.

<a id="user-guide-zendesk-generate-api-token"></a>

## Generate API Token in Zendesk

If you plan to use **Basic** as the **Authorization Type**, generate an API token in Zendesk first.

To retrieve your API token on the Zendesk side:

1. Open your account profile.
2. Click the cog icon in the panel to the left to open the **Admin** menu.
   ![Zendesk Admin menu in the left panel](user/img/system/integrations/zendesk/zendesk_admin.png)
3. Navigate to **Apps & Integrations > API Configuration**.
   ![Zendesk API configuration page](user/img/system/integrations/zendesk/zendesk_api.png)
4. Make sure the **Token Access** is enabled.
5. Click **API Tokens** in the panel to the left to open the API Tokens page.
6. Click **Add API Token** to create a new one.
   ![Zendesk API Tokens page with Add API Token button](user/img/system/integrations/zendesk/zendesk_api_token.png)
7. Provide a description for the new token, and click **Save**. This will prompt generation of a new token.
   ![Zendesk new API token generation dialog](user/img/system/integrations/zendesk/new-token.png)
8. Copy and store the token as you will need it to connect to OroCommerce. Please be aware that it will not be shown again after you click **Save**.

<a id="user-guide-zendesk-add-oauth-client"></a>

## Add OAuth Client in Zendesk

If you plan to use **OAuth** as the **Authorization Type**, add an OAuth client in Zendesk first.

To add your OAuth client on the Zendesk side:

1. Open your account profile.
2. Click the cog icon in the left panel to open the **Admin** menu.
   ![Zendesk Admin menu in the left panel](user/img/system/integrations/zendesk/zendesk_admin.png)
3. In the left sidebar, navigate to **Apps and integrations > OAuth clients**.
   ![Zendesk Apps and integrations section with OAuth clients selected](user/img/system/integrations/zendesk/zendesk_dashboard_oauth_token.png)
4. Click **Add OAuth client**.
   ![Zendesk OAuth clients page with Add OAuth client button](user/img/system/integrations/zendesk/zendesk_oauth_page.png)
5. Fill in the required fields and click **Save**. This generates a new secret for the client. When filling in the form, keep the following in mind:
   * Set the **Client kind** field to **Public**.
   * Use the **Identifier** value as the **OAuth Client ID** in the OroCommerce integration.
   * Copy the **OAuth Callback URL** from the OroCommerce integration page and paste it into the **Redirect URLs** field in Zendesk.

   ![Zendesk OAuth client form with the generated secret](user/img/system/integrations/zendesk/zendesk_oauth_form_secret_generation.png)

## Create a New Integration

To create an integration with Zendesk:

1. Navigate to **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** on the top right.
3. On the **Create Integration** page, set the integration type to **Zendesk**.
4. In the **General** section, define the following mandatory details:

   | Field                          | Description                                                                                                                                                                                                                                                                                                                                                                                             |
   |--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Type\***                     | The integration type. Must be set to **Zendesk**.                                                                                                                                                                                                                                                                                                                                                       |
   | **Name\***                     | The integration name used to refer to the integration within the system.                                                                                                                                                                                                                                                                                                                                |
   | **URL\***                      | A URL of your Zendesk account (e.g., `https://username.zendesk.com`).                                                                                                                                                                                                                                                                                                                                   |
   | **Authorization Type\***       | The authentication method to use when connecting to Zendesk. Select **Basic** to authenticate<br/>using a Zendesk email address and API token, or **OAuth** to use OAuth 2.0 authorization.<br/>![Zendesk integration create form with Basic and oAuth authorization types selected on two different forms shown side by side](user/img/system/integrations/zendesk/zendesk_create_connection-type.png) |
   |                                |                                                                                                                                                                                                                                                                                                                                                                                                         |
   | **API Email\***                | *(Basic only)* The email address used to register your Zendesk account.                                                                                                                                                                                                                                                                                                                                 |
   | **API Token\***                | *(Basic only)* The API token generated in your Zendesk account.                                                                                                                                                                                                                                                                                                                                         |
   | **OAuth Client ID\***          | *(OAuth only)* The unique identifier of the OAuth client registered in Zendesk.                                                                                                                                                                                                                                                                                                                         |
   | **OAuth Callback URL**         | *(OAuth only, read-only)* The callback URL for OAuth authorization. Copy this URL and paste<br/>it into the **Redirect URLs** field when configuring your OAuth client in Zendesk.                                                                                                                                                                                                                      |
   | **Default Zendesk User Email** | User with this email will be assigned tickets that come from the Oro application and for which<br/>there are no Zendesk users with a matching email address.                                                                                                                                                                                                                                            |
   | **Owner**                      | Limits the list of users that can manage the integration, subject to the access and permission settings<br/>etc.) Used as an Oro application user for Zendesk tickets if there are no users with a matching email address.                                                                                                                                                                              |
5. In the **Synchronization Settings** section, enable/disable the two-way synchronization.

   Select the **Enable Two-Way Sync** checkbox if you want to download data both from Zendesk to your Oro application and back.

   If the box is left unselected, data from Zendesk is loaded into the Oro application, but changes performed within it are not loaded back into Zendesk.

#### NOTE
If using **OAuth**, changing the **Enable Two-Way Sync** setting later requires you to authorize the connection again so the access scope is updated.

1. If the two-way synchronization is enabled, define the priority used for the conflict resolution (e.g., if the same customer details were edited from both Oro application and Zendesk):
   * **Remote wins** — Zendesk data is applied to both Zendesk and the Oro application.
   * **Local wins** — Oro application data is applied to both Zendesk and the Oro application.

#### NOTE
In the **Synchronization Settings** section, select the **Log Warnings** checkbox if you want all synchronization errors to be written into the application log.

1. Click **Save** to save the integration.
2. If you selected **OAuth** as the **Authorization Type**, make sure the Zendesk OAuth client is configured as described in the [Add OAuth Client in Zendesk](#user-guide-zendesk-add-oauth-client) section above, and then proceed to the [Authorize OAuth Connection to Zendesk](#user-guide-zendesk-authorize-oauth-connection) section below to complete the authorization.

<a id="user-guide-zendesk-authorize-oauth-connection"></a>

## Authorize OAuth Connection to Zendesk

#### NOTE
This section applies only when **Authorization Type** is set to **OAuth**.

1. To authorize connection to Zendesk, click the **Connect to Zendesk** button at the top of the integration form.
   ![Not Connected status with Connect to Zendesk button](user/img/system/integrations/zendesk/zendesk_not_connected.png)
2. Once you see a pop-up message about redirection to Zendesk click **Continue to Zendesk** to proceed:
   ![Connect to Zendesk ORO modal dialog](user/img/system/integrations/zendesk/oro_oauth_modal.png)
3. Next, sign in to your Zendesk account.
4. On the Zendesk authorization page, review the permissions that OroCommerce is requesting:
   * If **Enable Two-Way Sync** is disabled: OroCommerce requests **Read** access only.
   * If **Enable Two-Way Sync** is enabled: OroCommerce requests **Read** and **Write** access.

   ![Zendesk OAuth authorization page](user/img/system/integrations/zendesk/zendesk_oauth_authorization.png)
5. Click **Allow** to authorize OroCommerce to access your Zendesk account.
6. The authorization window will close automatically, and the label on the integration form will update from **Not Connected** to **Connected**, confirming that the connection has been authorized.
   ![Connected status after successful authorization](user/img/system/integrations/zendesk/zendesk_connected.png)

<a id="user-guide-zendesk-channel-integration-details-edit"></a>

## Manage the Integration

As an illustration, we have created a sample Zendesk integration with two-way synchronization enabled and sync priority set to **Remote Wins**. This means that if the same data is changed from both Zendesk and Oro application, Zendesk changes take precedence.

![image](user/img/system/integrations/zendesk/zendesk_connected.png)

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
