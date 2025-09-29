<a id="doc-my-user-configuration-display"></a>

# Configure Display Settings per User

In the Display section, you can configure the following display options for a particular user:

1. Navigate to **System > User Management > Users** in the main menu.
2. For the necessary user, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **System Configuration > General Setup > Display Settings** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![Settings menu options available on the user level](user/img/system/user_management/my_user_config_display.png)
4. Clear the **Use Organization** checkbox to change the organization-wide setting for the following options:
5. In the **User Bar** section, configure the setting:
   * **Show Recent Emails** — Enable the checkbox to display the recent emails on the user bar. They will appear next to the user name.

   ![A recent emails icon displayed on the user bar](user/img/system/user_management/user_configuration_showemailsuserbar.png)
6. In the **Navigation bar** section, configure the setting:
   * **Position** — Select whether the OroCommerce main menu will be positioned at the top of the page or on its left.
7. In the **Data Grid Settings** section, configure the options to display all the record lists (grids) in the back-office:
   * **Items Per Page By Default** — Defines the number of items displayed on one page of the grid by default (every time you open the grid).
   * **Lock Headers In Grids** — Ensures that grid headers stay visible while you scroll.
   * **Row Link Navigation** — Enables the ability for the row in the grid to behave like a native link. By right-clicking on the item in the grid, you can open it in a new tab/window.
   * **Record Pagination** — Enables the user navigation to the previous or next grid record from a record view page.
   * **Record Pagination Limit** — Type the maximum number of records that the user can navigate from a record view page.

   ![A record pagination sample](user/img/system/config_system/user_configuration_pagination.png)
8. In the **Activity Lists** section, configure the options to display [activities](../../../../activities/index.md#user-guide-activities).
   * **Sort By Field** — Select whether to sort activity records by the date when they were created or by the date when they were updated for the last time.
   * **Sort Direction** — Select whether to sort records in the ascending or descending direction.
   * **Items Per Page By Default** — Select how many records will appear on one page of the activity grids.
9. In the **WYSIWYG Settings** section, enable the [WYSIWYG Editor](../../../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) setting:
   * **Enable WYSIWYG Editor** — Select this checkbox to enable text formatting tools for emails, notes and comments.

   ![A formatting tool bar that enables editing a text for emails, notes, and comments](user/img/system/config_system/user_configuration_wysiwyg.png)
10. In the **Sidebar Settings** section, enable or disable the left and/or right sidebar to keep your sticky notes and task lists:

> * **Enable Left Sidebar** — Select **Yes** to enable the user to see and utilize the left sidebar.
> * **Enable Right Sidebar** — Select **Yes** to enable the user to see and utilize the right sidebar.
1. In the **Reports Settings** section, configure the following settings:
   * **Display SQL In Reports And Segments** — Select this checkbox to enable the user to review the SQL request sent to the system for a report or a segment. This way, users can check if a report has been developed correctly.

> ![A sample of the enabled display SQL field](user/img/system/config_system/user_configuration_showsql.png)

#### HINT
The Quick Action Buttons feature is available starting from OroCommerce v5.0.8. To check which application version you are running, see the [system information](../../../system-information/index.md#system-information).

1. In the **Upcoming Changes** section, configure the following setting:

> * **Enable Quick Creation Buttons** — Select the option to add quick action buttons to the customer, customer user, and customer group view pages.

> ![Displaying quick action buttons on the customer view page](user/img/system/config_system/quick-creation-buttons.png)
1. In the **Window Settings** section, configure the following setting:

> * **Quick Create Actions** — Select the preferred way to display the quick creation buttons form. The buttons with quick actions appear on the customer, customer user, and customer group view pages. When clicked, the form can be displayed in a new browser tab, a popup dialog window, or replace the current page.
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
