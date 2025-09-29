<a id="user-guide-customers-customer-users"></a>

<a id="user-guide-customers-create-customer-user"></a>

# Manage Customer Users in the Back-Office

#### HINT
This section is part of the [Customer Management](../../../concept-guides/customers/index.md#concept-guide-customers) topic that provides the general understanding of accounts, contacts, customers and customer hierarchy available in Oro applications.

[Customer users](../../../glossary.md#term-Customer-User) act on behalf of the company (i.e. customers in Oro context)  and may have a limited set of permissions in OroCommerce, depending on their function in the customer organization.

For customer user management, navigate to **Customers > Customer Users** in the main menu.

In Customer Users section, you can:

* View, edit, and create new customer users.
* Select their roles in OroCommerce to define their level of permissions and access to the actions and data in OroCommerce storefront.
* Manage customer user information (name, birthday, billing and shipping address, and phone number, etc).
* View requests for quotes, quotes, sales orders, and shopping lists created by the customer user.
* View communication with the customer that happened using email, notes or scheduled events.
* View additional information attached to customer user.
* Enable and disable the customer user.
* Reset the customer user password.
* Unlock the customer user that was locked out when the max number of login attempts is reached.
* Add OAuth applications

#### NOTE
You can delegate this function to the customer who will access user and role management in the OroCommerce storefront (see the [Delegating Users and Role Management to the Customer](#user-guide-customers-customer-user-delegate) section for more information).

**Customer Account Confirmation**

Upon registration, a customer user receives an email confirmation request. Once they follow up with the requested action, their account is marked as confirmed.

<!-- image::/img/customers/customer_users/CustomerUsers.png
:alt: The list of confirmed accounts -->

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer user to perform the following actions:

* <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** customer user details. Alternatively, click on the item to open its details page.
* <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** customer user details.
* <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** existing customer users.

## Create a Customer User

To create a new customer user:

1. Navigate to **Customers > Customer Users** in the main menu.
2. Click **Create Customer User**.
   ![The customer user creation form](user/img/customers/customer_users/CustomerUsersCreate.png)
3. Select the **Enabled** check box to enable the user to log into the system and to do their work within it upon creation.
4. Fill in the customer **Name** and other personal information.
5. Select a customer this user represents.
6. If you are adding a subsidiary of the existing customer, select a parent customer.
7. Assign a sales representative who will be assisting this customer user. By default, the customer sales representative applies to the customer user.
8. Select the **Generate Password** and **Send Welcome Email** check boxes.
9. Select the website of customer user registration. While the customer user may have access to other websites within the same organization, the email notifications concerning their user account will point to this website. See [Managing Websites](../../system/websites/index.md#user-guide-system-websites) for more information.
10. Select a **Preferred Localization** for the customer user. This field is displayed if more than one [localization](../../system/localization/index.md#sys-config-sysconfig-general-setup-localization) is enabled for any of the websites of the current organization. If you change the website for the customer user, you will need to select a new preferred localization.
11. Add billing and shipping address as described in the [Address Book](../customers/address-book.md#user-guide-getting-started-address-book) section.
12. In the **Roles** section, select the roles that should apply to the customer user. When several roles are selected, granted permissions are accumulated from all the assigned roles. See [Managing Customer User Roles](../customer-user-roles/index.md#user-guide-customers-customer-user-roles) for more information.

    #### IMPORTANT
    At least one role must be assigned if the **Enabled** check box is selected. Disabled customer users can be saved without roles, but you will need to assign roles to them later before enabling.
13. Click **Save** on the top right.

<a id="user-guide-customers-customer-users-consents"></a>

## View Accepted Consents

When at least one consent to process personal data has been accepted by a customer user in the storefront, you can view this information in the dedicated **Consents** section on the page of a particular customer user under **Customers > Customer Users**.

> ![View the Consents section of a customer user](user/img/customers/customer_users/consents_section_customer_user_page.png)

You can read more information on consent management in the following related topics:

* [Configure Consents](../../system/configuration/commerce/customer/global-consents.md#configuration-guide-commerce-configuration-consents)
* [Create Consents](../../system/consent-management/index.md#user-guide-consents-create)
* [Add a Consent Landing Page to a Web Catalog](../../../concept-guides/consents/add-consent.md#user-guide-consents-add)
* [View and Accept Consents in the Storefront](../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../activities/contact-requests/index.md#user-guide-activities-requests)

<a id="user-guide-customers-customer-user-delegate"></a>

## Delegate Account Management to a Customer User

You may want to delegate some of the customer user management capabilities to the customer users with administrator role by enabling *Account Management* permissions and capabilities. See the [Customer User Roles](../customer-user-roles/index.md#user-guide-customers-customer-user-roles) section for more information about permissions and capability management.

![The list of account management capabilities](user/img/customers/customer_user_roles/CustomerUserRolesManageAccounts_cust.png)

## Impersonate a Customer User

#### HINT
This feature is available in the Enterprise edition starting from OroCommerce v4.1.0. To check which application version you are running, see the [system information](../../system/system-information/index.md#system-information).

For troubleshooting purposes, user impersonation allows back-office users with the **Impersonate User** [role capability](../../system/user-management/roles/admin-capabilities.md#admin-capabilities) to access and operate the OroCommerce storefront as if they were logged in as a specific customer user. Such back-office user is redirected to the website assigned to the customer user that they are impersonating (i.e. the website where the customer user registered).

#### HINT
Before proceeding, make sure this feature is enabled in the system configuration [globally](../../system/configuration/commerce/customer/global-customer-users.md#system-configuration-user-impersonation) or [per organization](../../system/user-management/organizations/org-configuration/commerce/customers/organization-customer-users.md#organization-user-impersonation).

You can perform impersonation from the customer user grid, or from the view page of the selected customer.

To impersonate a customer user from the customer user grid, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the selected customer user and click <i class="fas fa-user-secret" aria-hidden="true"></i>.

![Impersonating a customer user from the customer user grid](user/img/customers/customer_user_roles/impersonate-customer-user-grid-icon.png)

To impersonate a customer user from the customer user view page, click <i class="fas fa-user-secret" aria-hidden="true"></i> **Log in as a User** on the top right.

![Impersonating a customer user from the customer user view page](user/img/system/user_management/user-impersonation-button.png)

The storefront session in impersonation mode opens in a new browser tab.

![Impersonation mode in the storefront](user/img/customers/customer_user_roles/impersonation-mode.png)

To exit impersonation mode, click **Log out** in the blue banner.

<a id="user-guide-customers-customer-users-oauth"></a>

## Add OAuth Applications

Oro applications support OAuth 2.0 credentials authorization grant type to enable connection of third-party applications to the web API. To connect a third-party application, you need to add it and configure its pre-generated credentials in the back-office of your Oro application. These credentials are managed on user level which enables generation of different credentials for various applications across multiple organizations (the multi-org functionality is only available in the Enterprise edition).

### Starting Conditions

To be able to create an OAuth application, make sure that you generate private and public encryption keys and add them to the /var directory of the installed Oro application. Although the path to the keys is predefined, you can change it by providing your custom location in the *config.yml* file.

#### NOTE
If no keys are found, the following warning message will be displayed in the back-office:

*OAuth authorization is not available as encryption keys configuration was not complete. Please contact your administrator.*

<!-- Install OAuth extension from Oro Extensions Store <link> (3.1). -->

### Add an Application

To add a new OAuth application for a customer user in the back-office:

1. Navigate to **Customers > Customer Users** in the main menu.
2. Click once on the name of your selected customer user to open their details page.
3. In the **OAuth Applications** section, click **Add Application** and provide the following details in the pop-up dialog:
   * **Organization** — If you are adding an application within the organization with *global* access, you can select which other available organization to add the application to.
   * **Application Name** — Provide a meaningful name for the application you are adding.
   * **Active** — Select the **Active** check box to activate the new application.
4. Click **Create**.

A corresponding notification is sent to the primary email address of the user, the owner of oauth application. You can change the default recipient, localization, or an email content if needed by updating the [OAuth email templates](../../system/emails/email-templates.md#user-guide-using-emails-create-template) and the related [notification rule](../../system/emails/notification-rules.md#user-guide-using-emails-notifications) set out-of-the-box in the system configuration.

Once the application is created, you are provided with a Client ID and a Client Secret. Click on the <i class="fa fa-copy" aria-hidden="true"></i> icon to copy the credentials to the clipboard.

![OAuth credentials](user/img/getting_started/user_menu/oauth/oauth_credentials.png)

#### IMPORTANT
For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you close this dialog, so make sure you save it somewhere safe so you can access it later.

You can add as many applications as you need for any of your existing organizations. All added applications are displayed in the grid, and you can filter them by name, organization, and status.

#### HINT
Use the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to edit, deactivate or delete an application.

![Manage auth applications](user/img/getting_started/user_menu/oauth/manage_oauth_application.png)

Use the generated Client ID and Client Secret to retrieve an access token to connect to your Oro application.

#### NOTE
For the aggregated information on all OAuth applications created by customer users in the back-office, refer to the general [Storefront OAuth Applications](../../system/storefront-oauth-app/index.md#storefront-oauth-app) topic.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->

* [Export Customer User Details](export.md)
* [Import Customer User Details](import.md)
