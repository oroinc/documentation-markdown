<a id="organization-config-website-sitemap"></a>

# Configure Website Sitemap Settings per Organization

You can control the way sitemap is generated for specific organization in OroCommerce:

1. Navigate to **System > Configuration > User Management > Organizations** in the main menu.
2. For the necessary organization, click the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu at the end of the row, and then click the <i class="fas fa-cog" aria-hidden="true"></i> **Configure** icon to start editing the configuration.
3. Select **System Configuration > Websites > Sitemap** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
4. Under **Robots.txt** (available as of OroCommerce version 5.1.9), a user can modify **Robots.Txt Template**, granting or restricting permission for site crawlers to navigate through the specified URLs within your website domain. Initially, the system obtains the default values from the *config/robots.txt.dist* or *robots.%domain.name%.txt* files automatically. Once a user modifies the values in the **Robots.Txt Template** configuration, the system starts adhering to these adjusted values only, subsequently updating the *robots.txt* and *sitemap* files accordingly.
   ![image](user/img/system/user_management/org_configuration/websites/sitemap_org.png)
5. Click **Save**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
