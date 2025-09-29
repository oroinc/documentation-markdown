<a id="admin-configuration-dotmailer-integration-settings"></a>

# Configure Global Dotdigital Settings

To enable data synchronization, make sure you configure Dotdigital integration on the Oro application side (see [Dotdigital Integration](../../../integrations/dotdigital/dotdigital-configuration.md#user-guide-dotmailer-configuration-dotmailer-side)) and on the Dotdigital side (see [Dotdigital Configuration](../../../integrations/dotdigital/dotdigital-configuration.md#user-guide-dotmailer-configuration-oro-side)).

To configure Dotdigital synchronization settings:

1. Navigate to **System > Configuration** in the main menu.
2. In the panel to the left, click **System Configuration > Integrations > dotdigital Settings**.
   ![Global dotdigital settings](user/img/marketing/marketing/dotdigital/global_dotdigital_settings.png)
3. To change the default settings, clear the **Use Default** option, and update the settings as required:

   | **Setting**                                                  | **Description**                                                                                                                                                                                                                                                                          |
   |--------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Enable Daily Force Synchronization of Mapped Data Fields** | Once a day, trigger the data fields check. All contacts from entity’s marketing lists will be automatically checked for updated fields and scheduled for sync with Dotdigital, if needed. The available options are *None*, *For mappings with virtual fields only*, *For all mappings*. |
   | **Data Fields Sync Interval**                                | This interval is used to update data fields from Dotdigital. By default, the number is set to 1 day.                                                                                                                                                                                     |

1. Click **Save Settings**.

**Related Articles**

- [Dotdigital Integration Overview](../../../integrations/dotdigital/index.md#user-guide-dotmailer-overview)
- [Configure Dotdigital Integration](../../../integrations/dotdigital/dotdigital-configuration.md#user-guide-dotmailer-configuration)
- [Manage Dotdigital Data Fields and Mappings](../../../../marketing/email-campaigns/dotdigital-data-fields-mappings.md#user-guide-dotmailer-data-fields)
- [Configure Dotdigital Single Sign-on](../../../integrations/dotdigital/dotdigital-single-sign-on.md#user-guide-dotmailer-single-sign-on)
- [Send Email Campaigns via Dotdigital](../../../../marketing/email-campaigns/sending-email-campaign-via-dotdigital.md#user-guide-dotmailer-campaign)
