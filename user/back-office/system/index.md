<!-- meta: description = Extensive manuals on the Oro application back-office system configuration -->

# Manage System Settings in the Back-Office

The **System** menu of the back-office contains post-install configuration settings of your Oro application. This is the starting point for setting up your application, from application display settings to payment integrations. Before proceeding with application configuration, please review the topics listed below to get a full understanding of general and domain-specific settings, and available configuration levels.

![System menu](user/img/system/configuration/system_menu.png)
* [Configuration](configuration/index.md#mc-system-configuration) — Manage system settings and settings specific for CRM, Commerce and marketing features.
* [User Management](user-management/index.md#user-guide-user-management) — Configure user, role and access management in the application and determine levels of access to data.
* [Contact Reasons](contact-reasons/index.md#admin-guide-contact-reasons) — Manage contact reasons used to categorize contact requests submitted through your website.
* [Contact Groups](contact-groups/index.md#contact-groups) — Create and manage contact groups.
* [Emails](emails/index.md#admin-guide-email-configuration) — Create and manage templates, notification rules and maintenance notifications.
* [Integrations](integrations/index.md#user-guide-integrations) — Create and manage pre-implemented integrations and integrations with third-party systems.
* [Channels](channels/index.md#user-guide-channels) — Create and manage multiple web and sales channels to aggregate data from different data sources.
* [Jobs](jobs/index.md#book-job-execution) — Monitor tasks executed in the background.
* [Data Audit](data-audit/index.md#user-guide-data-audit) — See the full history of changes made to any record of an auditable entity.
* [Scheduled Tasks](scheduled-tasks/index.md#book-time-based-command-execution) — View recurring tasks executed on schedule.
* [Entities](entities/index.md#doc-entities) — Create and manage entities and entity fields.
* [Tags Management](tags-management/index.md#admin-guide-tag-management) — Create tags and taxonomies to organize data in the application.
* [Menus](menus/index.md#doc-config-menus) — Customize default back-office menus.
* [Frontend Menus](frontend-menus/index.md#backend-frontend-menus) — Configure default storefront menus.
* [System Calendars](system-calendars/index.md#user-guide-calendars) — Create system and organization calendars and add events to them.
* [Shipping Rules](shipping-rules/index.md#sys-shipping-rules) — Add shipping rules to bind customers to specific shipping prices based on the shipping locations and the products they purchase.
* [Payment Rules](payment-rules/index.md#sys-payment-rules) —  Add payment rules to make payment options visible to buyers in the storefront.
* [Workflows](workflows/index.md#mc-system-wf) — Use system workflows and create custom workflows.
* [Processes](processes/index.md#user-guide-processes) — View and activate/deactivate processes in the application.
* [System Information](system-information/index.md#system-information) — Review system information on oro and third-party packages.
* [Consent Management](consent-management/index.md#system-consent-management) — Create and manage consents to comply with General Data Protection Regulations.
* [Websites](websites/index.md#system-websites) — Create multiple individually configured websites in the same application instance.
* [Localization](localization/index.md#sys-config-sysconfig-general-setup-localization) — Translate and adapt products for a specific country or region.
* [Alerts](../../../backend/integrations/notification-alerts.md#dev-integrations-notification-alerts) — System notification alerts.

<a id="configuration-guide-config-levels"></a>

<a id="doc-system-configuration"></a>

Oro applications enable you to configure system settings on four configuration levels (or scopes): global (system), organization, website and user.

* **Global**: To set up and manage settings globally, navigate to [System > Configuration](configuration/index.md#mc-system-configuration) in the main menu, and locate the options you need to configure in the panel to the left.
* **Organization**: To configure settings per [organization](../../glossary.md#term-Organization), navigate to [System > User Management > Organizations](user-management/organizations/org-configuration/index.md#doc-organization-configuration), and select the one that you wish to toggle the options for. Hover over the ellipsis menu to the right of the necessary organization and click *Configuration* to start editing it. Organization settings can fall back to system (or global) settings. Clearing the Use System checkbox next to the required option and changing its value means that you are configuring this option specifically for the selected organization.
* **Website**: To configure settings per [website](../../glossary.md#term-Website), navigate to [System > Websites](websites/web-configuration/index.md#doc-website-configuration), hover over the ellipsis menu to the right of the necessary website, and click *Configuration*. When Use Organization checkbox is enabled, organization settings override the global ones. Clear the Use Organization checkbox next to the required option, and change the default value to introduce changes at website level.
* **User**: To configure settings per [user](../../glossary.md#term-User), navigate to [System > User Management > Users](user-management/users/configuration/index.md#doc-my-user-configuration), hover over the ellipsis menu to the right of the necessary user, and click *Configuration*. When Use Organization checkbox is enabled, organization settings override the global ones. Clear the Use Organization checkbox next to the required option, and change the default value to introduce changes at user level.
* **Customer Group**: To configure settings per [customer group](../../glossary.md#term-Customer-Group), navigate to **Customers > Customer Groups**, hover over the ellipsis menu to the right of the necessary group and click *Configuration*. When Use Website checkbox is enabled, website settings override the customer group ones. Clear the Use Website checkbox next to the required option, and change the default value to introduce changes at customer group level.
* **Customer**: To configure settings per [customer](../../glossary.md#term-Customer), navigate to **Customers > Customers**, hover over the ellipsis menu to the right of the necessary customer and click *Configuration*. When Use Customer Group checkbox is enabled, customer group settings override the customer ones. Clear the Use Customer Group checkbox next to the required option, and change the default value to introduce changes at customer level.
