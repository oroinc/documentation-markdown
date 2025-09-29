<a id="admin-configuration-dotmailer-integration-settings"></a>

# Configure Global Dotmailer Settings

To enable data synchronization, make sure you configure dotmailer integration on the Oro application side (see [dotmailer Integration](../../../integrations/dotmailer/dotmailer-configuration.md#user-guide-dotmailer-configuration-dotmailer-side)) and on the dotmailer side (see [dotmailer Configuration](../../../integrations/dotmailer/dotmailer-configuration.md#user-guide-dotmailer-configuration-oro-side)).

To configure dotmailer synchronization settings:

1. Navigate to **System > Configuration** in the main menu.
2. In the panel to the left, click **System Configuration > Integrations > dotmailer Settings**.
   ![Global Dotmailer settings](user/img/marketing/marketing/dotmailer/dotmailer_settings.png)
3. To change the default settings, clear the **Use Default** option, and update the settings as required:

   | **Setting**                                                  | **Description**                                                                                                                                                                                                                                                                         |
   |--------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Enable Daily Force Synchronization of Mapped Data Fields** | Once a day, trigger the data fields check. All contacts from entity’s marketing lists will be automatically checked for updated fields and scheduled for sync with dotmailer, if needed. The available options are *None*, *For mappings with virtual fields only*, *For all mappings*. |
   | **Data Fields Sync Interval**                                | This interval is used to update data fields from dotmailer. By default, the number is set to 1 day.                                                                                                                                                                                     |

1. Click **Save Settings**.

**Related Articles**

- [dotmailer Integration Overview](../../../integrations/dotmailer/index.md#user-guide-dotmailer-overview)
- [Configure dotmailer Integration](../../../integrations/dotmailer/dotmailer-configuration.md#user-guide-dotmailer-configuration)
- [Manage dotmailer Data Fields and Mappings](../../../../marketing/email-campaigns/dotmailer-data-fields-mappings.md#user-guide-dotmailer-data-fields)
- [Configure dotmailer Single Sign-on](../../../integrations/dotmailer/dotmailer-single-sign-on.md#user-guide-dotmailer-single-sign-on)
- [Send Email Campaigns via dotmailer](../../../../marketing/email-campaigns/sending-email-campaign-via-dotmailer.md#user-guide-dotmailer-campaign)
