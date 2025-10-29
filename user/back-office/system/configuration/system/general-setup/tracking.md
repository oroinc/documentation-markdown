<a id="admin-configuration-tracking-settings"></a>
<!-- updated on 06 July 2017 -->

# Configure Global Tracking Settings

You can set up the settings that apply to all the [Tracking records](../../../../marketing/tracking-websites/index.md#user-guide-marketing-tracking) created in the Oro application.

To tune the tracking configuration:

1. In the main menu, navigate to **System > Configuration**.
2. Select **System Configuration > General Setup > Tracking** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

![Tracking configuration](user/img/system/config_system/tracking.png)

| Option                                     | Description                                                                                                                                                                                                                            | Default   |
|--------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| **Enable Tracking Statistics Aggregation** | If enabled, website visits information is aggregated for the statistics report. This improves statistics calculation time, but may have impact on the performance.                                                                     | Enabled   |
| **Enable Dynamic Tracking**                | If enabled, tracking data is processed in the real-time mode, and the event is registered as soon as it occurs. Please note that this may affect performance.                                                                          | Disabled  |
| **Log Rotation Interval**                  | Defines how often log files must be processed if **Dynamic Tracking** is disabled.                                                                                                                                                     | 1 hour    |
| **Piwik Host**                             | The field must be specified if you want the tracking data to be sent to a Matomo (previously known as Piwik) account. The value corresponds to the Matomo analytics URL of your account.                                               | None      |
| **Piwik Token Auth**                       | The field must be specified if you want the tracking data to be sent to a Matomo (previously known as Piwik) account. The value corresponds to the <a href="https://matomo.org/faq/general/faq_114/" target="_blank">Matomo</a> field. | None      |

#### NOTE
To enable the data transfer to a Matomo account, the **identifier** field of the Tracking Website record should be the same as the <a href="https://matomo.org/faq/general/faq_19212/" target="_blank">Website ID</a> used by Matomo.

1. Clear the **Use Default** checkbox to customize the required option.
2. Select the checkbox next to the option, choose a new value from the list, or type in the necessary information.
3. Click **Save Settings**.

#### IMPORTANT
The **Reset** button in the upper right corner of the page restores the latest saved values.

#### NOTE
You can navigate to the tracking website management page using the tracking website link at the bottom of the page.

**Related Articles**

* [Marketing Features](../../marketing/general-setup-marketing/index.md#marketing-system-configuration)
* [Tracking Websites](../../../../marketing/tracking-websites/index.md#user-guide-marketing-tracking)

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
