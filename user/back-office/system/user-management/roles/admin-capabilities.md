<a id="admin-capabilities"></a>

# Configure Entity and System Capabilities in the Back-Office

#### NOTE
The Entity and System Capabilities topic is part of the section on [Understanding Roles and Permissions](index.md#user-guide-user-management-permissions-roles), and provides the list of capabilities that you can enable or disable when creating or modifying roles in OroCommerce.

Access to different capabilities in the back-office depends on the capabilities enabled for a specific user role. In the application, these capabilities are grouped under categories, such as accounts management, orders or system capabilities. An example of a capability is enabling a selected user to manage menus or passwords.

You can enable or disable entity-specific and system-specific capabilities in the **Entity** section when creating or updating a role in your application, as illustrated below:

#### WARNING
Keep in mind that capabilities available in your instance depend on the Oro application installed.

![image](user/img/system/user_management/all_capabilities.png)

Read on to learn more about the capabilities available for users in the back-office.

<a id="admin-capabilities-acc"></a>

<a id="admin-capabilities-data-audit"></a>

<a id="admin-capabilities-system-info"></a>

## Account Management

In the Account Management section, the following capabilities are available:

* **Access System Information** — Enables a user to view the system information page under **System > System Information** in the main menu. This page contains the list of Oro packages and third-party packages that are installed, and is usually only used by system administrators and integrators.
  ![image](user/img/system/user_management/system_information_enabled.png)
* **Enter The Billing Address Manually** — Enables a user to provide the billing address manually.
* **Enter The Shipping Address Manually** — Enables a user to provide the shipping address manually.
* Override Customer Payment Term

<!-- comment: Enables to change the existing payment term for the customer and its customer users. -->
* **Login as Customer User** — Enables a back-office user to access and operate the OroCommerce storefront as if they were logged in as a specific customer user. Keep in mind that this feature is available in the Enterprise edition.
  ![User impersonation button](user/img/system/user_management/user-impersonation-button.png)
* **Receive Notification Messages For The System Mailboxes That Were Configured Incorrectly** — Enable this option to receive an email notification if synchronization of the system mailbox is unsuccessful as the result of incorrect credentials.
* **Use Any Billing Address From The Customer User’s Address Book** — Enables a user to select any billing address available in the customer user’s address book from the list.
* **Use Any Billing Address From The Customer’s Address Book** — Enables a user to select any billing address available in the customer’s address book from the list.
* **Use Any Shipping Address From The Customer Address Book** — Enables a user to select any shipping address available in the customer’s address book from the list.
* **Use Any Shipping Address From The Customer User’s Address Book** — Enables a user to select any shipping address available in the customer user’s address book from the list.
* **Use The Default Billing Address From The Customer User’s Address Book** — Enables a user to select the default billing address from the customer user’s address book.
* **Use The Default Shipping Address From The Customer User’s Address Book** — Enables a user to select the default shipping address from the customer user’s address book.
* Work With Payments
  > <!-- comment: Apparently, Work with Payments is responsible for enabling users to capture payments from the back-office. When the capability is disabled for certain roles, users with these roles cannot withdraw any payments for orders. This needs to be checked, however. -->

## Catalog

In the Catalog section, the following capabilities are available:

* **[Product Attribute] Create Attribute** — Enables a user to create product attributes in the application.
  ![image](user/img/system/user_management/create_attribute_enabled.png)
* **[Product Attribute] Edit Attribute** — Enables a user to edit product attributes in the application.
* **[Product Attribute] Remove Attribute** — Enables a user to remove product attributes from the application.
* **[Product Attribute] View Attributes** — Enables a user to view product attributes in the application.
* **[Related Products] Edit Related Products** — Enables a user to view, add and edit related products.
  <!-- comment: Per discussion with PO, should be renamed to Manage Related Products -->![image](user/img/system/user_management/related_products_enabled.png)
* **[Up-Sell Products] Edit Up-Sell Products** — Enables a user to view, add and edit up-sell products.
  <!-- comment: Per discussion with PO, should be renamed to Manage Ups-sell Products -->![image](user/img/system/user_management/upsell_products_enabled.png)

  #### NOTE
  When both **Edit Related Products** and **Edit Up-sell Products** are disabled for a role, the **Related Items** section disappears from the product page.

## Quotes

In the Quotes section, the following capabilities are available:

* **Add Free-Form Items** — Enables a user to provide product details (SKU, product name) using free-form entry when creating a quote in the back-office.
  ![image](user/img/system/user_management/free_form_entry.png)
* **Enter The Shipping Address Manually** — Enables a user to provide the shipping address for quotes manually when creating or editing a quote in the back-office.
  ![image](user/img/system/user_management/shipping_address_quote.png)
* Override Customer Payment Term
* **Override Quote Prices** — Enables a user to override prices in quotes. When disabled, the price fields on quote edit pages are inactive.
  ![image](user/img/system/user_management/override_quote_price_disabled.png)
* **Review And Approve Quotes** — Enables a user to manage quotes (e.g. sent to customer) without approval. When disabled, the user has to submit quotes for review first. This capability affects quotes when [Backoffice Quotes Flow with Approvals](../../workflows/system-workflows/backoffice-quote-flow-with-approvals.md#doc-workflows-backoffice-quote-flow-with-approvals) is enabled in the application.
  ![image](user/img/system/user_management/approve_quotes_disabled.png)
* **Use Any Shipping Address From The Customer Address Book** — Enables a user to select any shipping address available in the customer’s address book from the list.
* **Use Any Shipping Address From The Customer User’s Address Book** — Enables a user to select any shipping address available in the customer user’s address book from the list.
* **Use The Default Shipping Address From The Customer User’s Address Book** — Enables a user to select the default shipping address from the customer user’s address book from the list.

<a id="admin-capabilities-campaign-emails"></a>

## Marketing

In the Marketing section, the following capabilities are available:

* **Send Campaign Emails** — Enables a user to launch a campaign manually. When the capability is enabled, the user can [send emails](../../../marketing/email-campaigns/index.md#user-guide-email-campaigns-send) specified by the campaign which is not scheduled to send emails at a specific time (campaigns that have *Manual* selected for **Schedule**). This capability does not affect the user’s ability to define and edit campaign settings and create templates.
  ![image](user/img/system/user_management/email_campaign_emabled.png)

<a id="admin-capabilities-jobs"></a>

<a id="admin-capabilities-system-config"></a>

<a id="admin-capabilities-export-grid"></a>

<a id="admin-capabilities-tags"></a>

<a id="admin-capabilities-passwords"></a>

<a id="admin-capabilities-mailchimp"></a>

<a id="admin-capabilities-share-grid"></a>

<a id="admin-capabilities-org-calendar-events"></a>

<a id="admin-capabilities-sys-calendar-events"></a>

## System Capabilities

In the System Capabilities section, the following capabilities are available:

### Application

* **Access Job Queue** — Enables a user to review jobs that have been started in the system, as well as view their current status and their performance log (by default, this information can be found by navigating to **System > Jobs** in the main menu).
* **Access Personal Configuration** — Enables a user to access their [profile configuration settings](../users/configuration/index.md#doc-my-user-configuration) where they can localize the application, change the display settings, and otherwise modify how the application will appear to them. Changes made by a user on the personal configuration page do not affect other users.
  ![image](user/img/system/user_management/user_level_config.png)
* **Access System Configuration** — Enables a user to access system configuration settings under **System > Configuration** in the main menu.
  ![image](user/img/system/user_management/sys_config.png)
* **Debug Prices** – Enables a user to access the Price Calculation Details menu under Sales to understand how prices for a particular product are created, what the current prices are for a given customer and website, and what the prices will be for a specific date.
  ![Illustration of the permission that enables Pricing Debug Menu](user/img/sales/prices-debug/prices-debug-ACL.png)
* **Assign/Unassign Tags** — Enables a user to assign/unassign [tags](../../tags-management/index.md#admin-guide-tag-management) to records.
* **Connect to Mailchimp** — Enables a user to map the contents of a marketing list in OroCommerce to use a segment of the subscribers list in [Mailchimp](../../../marketing/email-campaigns/sending-email-campaign-via-mailchimp.md#user-guide-mailchimp-campaign). When the capability is enabled, the **Connect to Mailchimp** button appears on the page of the selected marketing list. Make sure that the integration between OroCommerce and [Mailchimp is configured](../../integrations/mailchimp-integration.md#user-guide-mc-integration) for the capability to work.
* **Export Grid View** — Enables a user to export the grid views that they have configured.
* **Manage Menus** — Enables a user to access [menus configuration at different levels](../../menus/index.md#doc-config-menus).

  #### IMPORTANT
  The ability to configure menus is controlled by the two capabilities: **Manage Menus** and **Access System Configuration**.
  - To enable a user to personalize menus for themselves and configure menus for each organization individually, include the **Manage Menus** capability into the user role.
  - To enable a user to configure menus for the whole enterprise (all organizations that exist in the Oro application) at once, in addition to the **Manage Menus** capability, include also the **Access System Configuration** capability into the user role.

  #### WARNING
  for the Enterprise Edition only:
  - If your enterprise includes several organizations, changes made at **System > Menus** affect all organizations.
  - To apply changes only to a specific organization, make changes at the organization level.
* **Manage Passwords** — Enables a user to change passwords of other users. See the [User Management](../users/index.md#user-management-users) section for more information.

  #### HINT
  This capability does not influence a user’s ability to edit their own password from the **My User** page.

  ![image](user/img/system/user_management/manage_passwords.png)
* **Share Data View** — Enables a user to [share and unshare the grid views](../../../getting-started/navigation/record-tables.md#doc-grids-actions-grid-views-share) that they have configured.
  ![image](user/img/system/user_management/grid_share.png)![image](user/img/system/user_management/grid_unshare.png)
* **Update User Profile** — Enables a user to update their own profile regardless of which permission for the **Edit** action on the **User** entity the user’s role includes. That is, when the **Update User Profile** capability is included in the user’s role, even if the role has *None* selected for the **Edit** action on the **User** entity, the user will be able to update their profile.
* **View SQL Query of a Report/Segment** — Enables a user to review the SQL request that is sent to the system for a report/segment. When the capability is enabled, the **Show SQL Query** link appears below the report.This capability is usually only granted to system administrators, so they can check if a report has been developed correctly.
  ![image](user/img/system/config_system/user_configuration_showsql.png)

  #### HINT
  This capability must be also enabled in the report settings. For this, in the main menu, navigate to **System Configuration > Display Settings > Report settings**, and select the **Display SQL in Reports And Segments** checkbox.

### Calendar

* **Assign Calendar Events** — Enables a user to assign [calendar events](../../../activities/calendar-events/index.md#doc-activities-events) to the calendars of other users.
* **Manage Organization Calendars (and their events)** — Enables a user to manage [organization-wide calendars](../../system-calendars/index.md#user-guide-calendars) in the application (create, view, edit and delete). Organization calendars are system calendars with *Organization* selected for **Scope**.

  #### HINT
  When this capability is disabled, users can still view organization-wide calendars, add them to their own calendar views, and copy related events to their own calendars.
* **Manage System Calendars (and their events)** — Enables a user to manage [system-wide calendars](../../system-calendars/index.md#user-guide-calendars) in the application (create, view, edit and delete). System calendars have *System* selected for **Scope**.

  #### IMPORTANT
  When both **Manage Organization Calendars** and **Manage System Calendars** capabilities are disabled, the **System Calendar** menu disappears from under **System** in the main menu. When at least one capability is enabled, the **System Calendars** menu appears under **System**.
  ![image](user/img/system/user_management/system_calendars_enabled.png)

<a id="admin-capabilities-config-entities"></a>

<a id="admin-capabilities-merge"></a>

<a id="admin-capabilities-search"></a>

<a id="admin-capabilities-export-entities"></a>

<a id="admin-capabilities-import-entities"></a>

### Entity

* **Access Entity Management** — Enables a user to access entity management section under **System > Entities > Entity Management** in the main menu. Many entities in OroCommerce can be configured from the interface, as described in the [Entity Management topic](../../entities/index.md#doc-entities) and [Entity Fields](../../entities/entity-fields/index.md#doc-entity-fields) topics.
* **Merge Entities** — Enables users to [merge](../../../getting-started/information-management/manage-records/index.md#doc-grids-actions-records-merge) several records of the same entity.
* **Search** — Enables users to [search](../../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search) for specific records within the application. The setting does not influence the user’s ability to [search by tag](../../../../concept-guides/catalog-promotions/search/index.md#user-guide-getting-started-search-tag).
* **Export Entity Records** — Enables users to export entity records. When the capability is enabled, the **Export** button appears on the top right of the page with the table of selected records.
  ![image](user/img/system/user_management/export_data.png)
* **Import Entity Records** — Enables users to import records from a file to OroCommerce. When the capability is enabled, the **Import File** button appears on the top right of the page with the table of selected records.
  ![image](user/img/system/user_management/import_data.png)

**Related Articles**

* [Introduction to Role Management](index.md#user-guide-user-management-permissions-roles)
* [Field Level Permissions](field-level-acl.md#user-guide-user-management-permissions-roles-field-level-acl)
* [End-to-end Access Configuration in Context](access-in-context.md#user-guide-user-management-permissions-roles-examples)
