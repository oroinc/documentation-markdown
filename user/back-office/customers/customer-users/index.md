<a id="user-guide-customers-customer-users"></a>

<a id="user-guide-customers-create-customer-user"></a>

# Manage Customer Users in the Back-Office

#### HINT
This section is part of the [Customer Management](../../../concept-guides/customers-sales/customers/index.md#concept-guide-customers) topic that provides a general understanding of accounts, contacts, customers, and customer hierarchy available in Oro applications.

[Customer users](../../../glossary.md#term-Customer-User) act on behalf of the company (i.e., customers in Oro context) and may have a limited set of permissions in OroCommerce, depending on their function in the customer organization.

In the main menu, navigate to **Customers > Customer Users** for customer management.

In the Customer Users section, you can:

* View, edit, and create new customer users.
* Select their roles in OroCommerce to define their level of permissions and access to the actions and data in the OroCommerce storefront.
* Manage customer user information (name, birthday, billing and shipping address, phone number, etc).
* View requests for quotes, quotes, sales orders, and shopping lists created by the customer user.
* View communication with the customer that happened using email, notes, or scheduled events.
* View additional information attached to customer user.
* Enable and disable the customer user.
* Reset the customer user password.
* Unlock the customer user locked out when the maximum number of login attempts is reached.
* Add OAuth applications

#### NOTE
You can delegate this function to the customer who will access user and role management in the OroCommerce storefront (see the [Delegating Users and Role Management to the Customer](#user-guide-customers-customer-user-delegate) section for more information).

Quick action buttons enable you to create a new address, order, and quote directly from the customer user view page. Click the button to open the required form for data input. The form can be displayed in a new browser tab, a popup dialog window, or replace the current page, [depending on its system configuration](../../system/configuration/system/general-setup/display.md#doc-configuration-display-settings-quick-actions).

Alternatively, click **More Actions** at the top right and select the entity to be created from the customer user view page.

![Displaying the quick action buttons on the customer user view page](user/img/customers/customer_users/quick-buttons-customer-user.png)

**Customer Account Confirmation**

Upon registration, a customer user receives an email confirmation request. Once they follow up with the requested action, their account is marked as confirmed.

![The list of confirmed accounts](user/img/customers/customer_users/CustomerUsers.png)

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary customer user to perform the following actions:

* <i class="fa fa-ban fa-lg" aria-hidden="true"></i> **Disable** a customer user.
* <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View** customer user details. Alternatively, click on the item to open its details page.
* <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** customer user details.
* ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) **Delete** existing customer users.

## Create a Customer User

To create a new customer user:

1. Navigate to **Customers > Customer Users** in the main menu.
2. Click **Create Customer User**.
   ![The customer user creation form](user/img/customers/customer_users/CustomerUsersCreate.png)
3. Select the **Enabled** checkbox to enable the user to log into the system and to do their work within it upon creation.
4. Fill in the customer **Name** and other personal information.
5. Select a customer this user represents.
6. Select a parent customer if you are adding a subsidiary of the existing customer.
7. Assign a sales representative who will be assisting this customer user. By default, the customer sales representative applies to the customer user.
8. Select the **Generate Password** and **Send Welcome Email** checkboxes.
9. Select the website of customer user registration. While the customer user may have access to other websites within the same organization, the email notifications concerning their user account will point to this website. See [Managing Websites](../../system/websites/index.md#user-guide-system-websites) for more information.
10. Select a **Preferred Localization** for the customer user. This field is displayed if more than one [localization](../../system/localization/index.md#sys-config-sysconfig-general-setup-localization) is enabled for any of the websites of the current organization. If you change the website for the customer user, you will need to select a new preferred localization.
11. Add billing and shipping address as described in the [Address Book](../customers/address-book.md#user-guide-getting-started-address-book) section.
12. In the **Roles** section, select the roles that should apply to the customer user. When several roles are selected, granted permissions are accumulated from all the assigned roles. See [Managing Customer User Roles](../customer-user-roles/index.md#user-guide-customers-customer-user-roles) for more information.

    #### IMPORTANT
    At least one role must be assigned if the **Enabled** checkbox is selected. Disabled customer users can be saved without roles, but you will need to assign roles to them later before enabling them.
13. Click **Save** on the top right.

<a id="user-guide-customers-customer-users-consents"></a>

## View Accepted Consents

When at least one consent to process personal data has been accepted by a customer user in the storefront, you can view this information in the dedicated **Consents** section on the page of a particular customer user under **Customers > Customer Users**.

> ![View the Consents section of a customer user](user/img/customers/customer_users/consents_section_customer_user_page.png)

You can read more information on consent management in the following related topics:

* [Configure Consents](../../system/configuration/commerce/customer/global-interactions.md#configuration-guide-commerce-configuration-consents)
* [Create Consents](../../system/consent-management/index.md#user-guide-consents-create)
* [Add a Consent Landing Page to a Web Catalog](../../../concept-guides/administration/consents/add-consent.md#user-guide-consents-add)
* [View and Accept Consents in the Storefront](../../../storefront/account/my-profile/index.md#frontstore-guide-profile-consents)
* [Revoke Consents](../../activities/contact-requests/index.md#user-guide-activities-requests)

<a id="user-guide-customers-customer-user-delegate"></a>

## Delegate Account Management to a Customer User

You may want to delegate some of the customer user management capabilities to the customer users with an administrator role by enabling *Account Management* permissions and capabilities. See the [Customer User Roles](../customer-user-roles/index.md#user-guide-customers-customer-user-roles) section for more information about permissions and capability management.

![The list of account management capabilities](user/img/customers/customer_user_roles/CustomerUserRolesManageAccounts_cust.png)

<a id="user-guide-customers-customer-user-impersonate"></a>

## Impersonate a Customer User

#### HINT
This feature is available in the Enterprise edition.

For troubleshooting purposes or to place orders on behalf of a customer user, you can use user impersonation to allow back-office users with the **Login as Customer User** [role capability](../../system/user-management/roles/admin-capabilities.md#admin-capabilities) to access and operate the OroCommerce storefront as if they were logged in as a specific customer user. Such back-office user is redirected to the website assigned to the customer user they are impersonating (i.e., the website where the customer user registered).

#### HINT
Before proceeding, make sure this feature is enabled in the system configuration [globally](../../system/configuration/commerce/customer/global-customer-users.md#system-configuration-user-impersonation) or [per organization](../../system/user-management/organizations/org-configuration/commerce/customers/organization-customer-users.md#organization-user-impersonation).

You can perform impersonation from the customer user grid or the selected customer’s view page.

To impersonate a customer user from the customer user grid, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the selected customer user and click <i class="fas fa-user-secret" aria-hidden="true"></i>.

![Impersonating a customer user from the customer user grid](user/img/customers/customer_user_roles/impersonate-customer-user-grid-icon.png)

Click <i class="fas fa-user-secret" aria-hidden="true"></i> **Log in as a User** on the top right to impersonate a customer user from the customer user view page.

![Impersonating a customer user from the customer user view page](user/img/system/user_management/user-impersonation-button.png)

The storefront session in impersonation mode opens in a new browser tab.

![Impersonation mode in the storefront](user/img/customers/customer_user_roles/impersonation-mode.png)

To exit impersonation mode, click **Log out** in the blue banner.

#### NOTE
If a back-office user placed an order on behalf of the customer user, this will be reflected on the order view page in the storefront with the following note: *This order was created on your behalf by a member of our staff.*

![An order view page with a note saying "This order was created on your behalf by a member of our staff".](user/img/storefront/orders/order-impersonated.png)

In the back-office you can view who created the order on the order view page and in the grid.

![image](user/img/customers/customer_users/created-by.png)

<a id="user-guide-customers-customer-user-reset-password"></a>

## Reset User Passwords

An administrator can request the customer user to change their password by clicking the <i class="fa fa-unlock-alt" aria-hidden="true"></i> **Reset Password** button on the customer user’s profile page:

![image](user/img/customers/customer_users/customer-user-reset-password-button.png)

A customer user will receive an email with the link to update their password.

![image](user/img/customers/customer_users/customer_user_reset_password.png)

When resetting their password, users can only log into the application once their password is changed, in which case their password status changes to **Reset** in the back-office. The status switches to **Active** as soon as the customer user changes the password.

![image](user/img/customers/customer_users/customer_user_password_reset.png)

Alternatively, you can reset the password for a specific customer user from the grid of all customer users. For this, hover over the ellipsis menu at the end of the row of the selected customer user, and click **Reset Password**.

![image](user/img/customers/customer_users/customer_user_reset_password_from_grid.png)

The same functionality is available for the storefront administrators.

You can change the contents of the password change email by updating the **customer_user_force_reset_password** [email template](../../system/emails/email-templates.md#user-guide-using-emails-create-template) of the Customer User entity.

The link in the email will have a refresh token to enable password change for a customer user. By default, this token and the reset password link in the email are valid for 24 hours from the moment the reset request is thrown.

An administrator can change this ttl in the [configuration of the Customer bundle](../../../../backend/configuration/yaml/bundles-config.md#yaml-bundles-configuration-reset-password).

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
2. Click on the name of your selected customer user to open their details page.
3. In the **OAuth Applications** section, click **Add Application** and provide the following details in the pop-up dialog:
   * **Organization** — If you are adding an application within the organization with *global* access, you can select which other available organization to add the application to.
   * **Application Name** — Provide a meaningful name for the application you are adding.
   * **Active** — Select the **Active** checkbox to activate the new application.
4. Click **Create**.

A corresponding notification is sent to the user’s primary email address, the owner of the OAuth application. You can change the default recipient, localization, or email content if needed by updating the [OAuth email templates](../../system/emails/email-templates.md#user-guide-using-emails-create-template) and the related [notification rule](../../system/emails/notification-rules.md#user-guide-using-emails-notifications) set out-of-the-box in the system configuration.

Once the application is created, you are provided with a Client ID and a Client Secret. Click on the <i class="fa fa-copy" aria-hidden="true"></i> icon to copy the credentials to the clipboard.

![OAuth credentials](user/img/getting_started/user_menu/oauth/oauth_credentials.png)

#### IMPORTANT
For security reasons, the Client Secret is displayed only once – immediately after you have created a new application. You cannot view the Client Secret anywhere in the application once you close this dialog, so make sure you save it somewhere safe to access it later.

You can add as many applications as you need for any of your existing organizations. All added applications are displayed in the grid; you can filter them by name, organization, and status.

#### HINT
Use the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to edit, deactivate or delete an application.

![Manage auth applications](user/img/getting_started/user_menu/oauth/manage_oauth_application.png)

Use the generated Client ID and Client Secret to retrieve an access token to connect to your Oro application.

#### NOTE
For the aggregated information on all OAuth applications created by customer users in the back-office, refer to the general [Customer User OAuth Applications](../customer-user-oauth-app/index.md#customer-user-oauth-app) topic.

**Related Articles**

* [Password Change Policy](../../system/configuration/commerce/customer/global-customer-users.md#user-guide-customers-customer-user-password-change-policy)
* [Password History Policy](../../system/configuration/commerce/customer/global-customer-users.md#configuration-guide-commerce-configuration-customer-user-password-change-policy)

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

* [Export Customer User Details](export.md)
* [Import Customer User Details](import.md)
