<a id="doc-my-user-configuration-display"></a>

# Configure Display Settings per User

In the Display section, you can configure the following display options for a particular user:

1. Navigate to **System > User Management > Users** in the main menu.
2. For the necessary user, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **System Configuration > General Setup > Display Settings** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

   ![Settings menu options available on the user level](user/img/system/user_management/my_user_config_display.png)
4. Clear the **Use Organization** check box to change the organization-wide setting for the following options:

   **User bar**

   | Field              | Description                                                                                                                                                                                                                                  |
   |--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Show Recent Emails | Select this check box to display the recent emails on the user bar (they will appear next to the user name).<br/>![A recent emails icon displayed on the user bar](user/img/system/user_management/user_configuration_showemailsuserbar.png) |

   **Navigation bar**

   | Field    | Description                                                                                        |
   |----------|----------------------------------------------------------------------------------------------------|
   | Position | Select whether the OroCommerce main menu will be positioned at the top of the page or on its left. |

   **Data Grid settings**

   | Field                     | Description                                                                                                                                                                                                       |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Items Per Page By Default | Select how many records will appear on one page of record grids.                                                                                                                                                  |
   | Lock Headers In Grids     | Select this check box to ensure that headers of a record grid will stay visible while you scroll.                                                                                                                 |
   | Record Pagination         | Select this check box to enable the user navigate to the previous or next grid record from a record view page.<br/>![A record pagination sample](user/img/system/config_system/user_configuration_pagination.png) |
   | Record Pagination Limit   | Type the maximum number of records that the user can navigate from a record view page.                                                                                                                            |

   **Activity lists**

   | Field                     | Description                                                                                                                         |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
   | Sort By Field             | Select whether to sort activity records by the date when they were created or by the date when they were updated for the last time. |
   | Sort Direction            | Select whether to sort records in the ascending or descending direction.                                                            |
   | Items Per Page By Default | Select how many records will appear on one page of the activity grids.                                                              |

   **WYSIWYG settings**

   | Field                 | Description                                                                                                                                                                                                                                  |
   |-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Enable WYSIWYG Editor | Select this check box to enable text formatting tools for emails, notes and comments.<br/>![A formatting tool bar that enables editing a text for emails, notes, and comments](user/img/system/config_system/user_configuration_wysiwyg.png) |

For more details on WYSIWYG management, see the [WYSIWYG Editor](../../../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) topic.

> **Sidebar settings**

> | Field                | Description                                                             |
> |----------------------|-------------------------------------------------------------------------|
> | Enable Left Sidebar  | Select **Yes** to enable the user to see and utilize the left sidebar.  |
> | Enable Right Sidebar | Select **Yes** to enable the user to see and utilize the right sidebar. |

> **Reports settings**

> | Field                               | Description                                                                                                      |
> |-------------------------------------|------------------------------------------------------------------------------------------------------------------|
> | Display SQL In Reports And Segments | Select this check box to enable the user to review the SQL request sent to the system for a report or a segment. |
> ![A sample of the enabled display SQL field](user/img/system/config_system/user_configuration_showsql.png)
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
