<a id="upload-settings-website"></a>

# Configure Upload Settings per Website

To configure the upload settings for a particular website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **System Configuration > General Setup > Upload Settings** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).
4. In the **File Names** section, you can control whether to use original file names. By default, the setting is enabled.
   ![File names section on website level](user/img/system/websites/web_configuration/upload_settings_websites.png)

   #### HINT
   The **File Names** setting is available starting from v5.0.2. and can be configured [globally](../../../../configuration/system/general-setup/upload.md#admin-configuration-upload-settings), [per organization](../../../../user-management/organizations/org-configuration/general-setup-org/organization-upload-settings.md#configuration-guide-system-configuration-general-setup-sysconfig-upload-settings-organization) and per website.

   **Enable Original File Names** — When enabled, the original file name is appended to the system-generated hash value. All non-alphanumeric characters (e.g., “:”, “)”, “,”, “~”) are replaced with “-” (dash).

   For example, the name of the file is **coffee_maker/bosch_#RND123.jpg**, the system-generated hash value is `media/cache/attachment/filter/product_gallery_main/b6d3b12a2194f276376d682d2e7e6bd1/1/5bae287538.jpg`. If the option is enabled, the file name is displayed in the storefront as follows `media/cache/attachment/filter/product_gallery_main/623364376a0e8125036727/1/5bae287538-coffee-maker-bosch-RND123.jpg`

   #### NOTE
   When this option is enabled, the **Enable Original File Names** setting for Product Images is  hidden from the system configuration page.
5. Click **Save Settings**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
