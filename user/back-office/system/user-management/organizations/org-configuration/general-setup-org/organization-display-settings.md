<a id="configuration-general-setup-display-settings-organization"></a>

# Configure Display Settings per Organization

In this section, you can specify the display settings for the organization.

#### NOTE
The organization-level configuration has higher priority and overrides the system settings.

1. Navigate to **System > User Management > Organization** in the main menu.
2. For the necessary organization, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the <i class="fas fa-cog" aria-hidden="true"></i> **Configure** icon to start editing the configuration.
3. Select **System Configuration > General Setup > Display Settings** in the menu to the left.
   ![Settings menu configuration for organization](user/img/system/user_management/org_configuration/general/organization_display_settings.png)
4. Clear the **Use System** check box to change the system-wide setting.

**Map Settings**

| Field              | Description                                                                                     |
|--------------------|-------------------------------------------------------------------------------------------------|
| Enable Map Preview | When the Map Preview is enabled, the addresses location are shown on the map in the storefront. |

**Navigation bar**

| Field    | Description                                                                                             |
|----------|---------------------------------------------------------------------------------------------------------|
| Position | Select whether your Oro application main menu will be positioned at the top of the page or on its left. |

**WYSIWYG settings**

| Field                 | Description                                                                                                                                                                                                                                                                   |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Enable WYSIWYG Editor | Select this check box to enable text formatting tools for emails, notes and comments.<br/><br/>![A formatting tool bar that enables editing a text for emails, notes, and comments](user/img/system/user_management/org_configuration/general/user_configuration_wysiwyg.png) |

For more details on WYSIWYG management, see the [WYSIWYG Editor](../../../../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) topic.

**Activity lists**

| Field                     | Description                                                                                                                         |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Sort By Field             | Select whether to sort activity records by the date when they were created or by the date when they were updated for the last time. |
| Sort Direction            | Select whether to sort records in the ascending or descending direction.                                                            |
| Items Per Page By Default | Select how many records will appear on one page of the activity grids.                                                              |

**Data Grid settings**

| Field                     | Description                                                                                                                                                                                                          |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Items Per Page By Default | Select how many records will appear on one page of record grids.                                                                                                                                                     |
| Record Pagination         | Select this check box to enable user navigation to the previous or next record list from a record view page.<br/><br/>![A record pagination sample](user/img/system/config_system/user_configuration_pagination.png) |
| Record Pagination Limit   | Type the maximum number of records that the user can navigate from a record view page.                                                                                                                               |

**Calendar settings**

| Field           | Description                                                                  |
|-----------------|------------------------------------------------------------------------------|
| Calendar Colors | A set of colors available for color coding different organization calendars. |
| Event Colors    | A set of colors available for color coding different organization event.     |

To change any color in the set:

1. Click it. The color picker opens.
2. Drag and drop a dot on the color picker wheel to select a new color.
3. Adjust the color brightness by dragging the level on the shades bar.

**Sidebar settings**

| Field                | Description                                                             |
|----------------------|-------------------------------------------------------------------------|
| Enable Left Sidebar  | Select **Yes** to enable the user to see and utilize the left sidebar.  |
| Enable Right Sidebar | Select **Yes** to enable the user to see and utilize the right sidebar. |

**Reports settings**

| Field                               | Description                                                                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| Display SQL In Reports And Segments | Select this check box to enable the user to review the SQL request sent to the system for a custom<br/>report or a segment. |
![A sample of the enabled display sql field](user/img/system/config_system/user_configuration_showsql.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
