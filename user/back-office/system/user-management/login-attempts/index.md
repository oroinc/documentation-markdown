<a id="user-guide-user-management-login-attempts"></a>

# Back-Office User Login Attempts

#### HINT
Starting from v5.0.7, the Login Attempts page is available under the global [organization](../../../getting-started/navigation/org-selector.md#user-guide-getting-started-switch-organization) only, unless there are no organizations marked as global in the Oro application. To check which application version you are running, see the [system information](../../system-information/index.md#system-information).

To simplify investigation of any security-related incidents, the administrator can check the successful and unsuccessful
login attempts.

The login info data is stored in the database and in the logs in the **security** log channel. The logs have the ID parameter used in the database to enable you to find a particular log item quickly.

The list of all login attempts is available under **System > User Management > Login Attempts** in the main back-office menu.

![Login Attempts](user/img/system/user_management/login_attempts/login_attempts.png)

The administrator can also open this list directly from the back-office user view page by clicking on the link with the date of the last login:

![Link to Login Attempts on View Page](user/img/system/user_management/login_attempts/user_view_page.png)

In this case, the data in datagrid will be filtered by this user:

![Filtered Login Attempts](user/img/system/user_management/login_attempts/filtered_login_attempts.png)

**Related Topics**

* [Customer User Login Attempts](../../../customers/login-attempts/index.md#user-guide-customers-customer-login-attempts)
* [Audit of Login Attempts](../../data-audit/index.md#admin-guide-data-audit-login-attempts)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
