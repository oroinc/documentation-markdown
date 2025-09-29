<a id="bundle-docs-platform-calendar-bundle-system-calendar"></a>

# System Calendars

You can use system calendars to provide everyday events for all users, such as employees’ birthdays, company weekends, vacations, etc. These calendars can be made available in a single organization or shared across all organizations in the system. To manage system calendars, navigate to **System > System Calendar** in the main menu. As soon as you [create a system calendar](../../../user/back-office/system/system-calendars/index.md#user-guide-calendars), it becomes visible for all users. The visibility of organization-wide calendars can be restricted by ACL against system-wide calendars, which are always visible.

## Configuration

By default, both organization and system-wide calendars are enabled, but you can disable any of them in the config.yml by adding the enabled_system_calendar option:

```yaml
oro_calendar:
    enabled_system_calendar: false
```

The possible values of this option:

- **true** - both organization and system-wide calendars are enabled
- **false** - both organization and system-wide calendars are disabled
- **organization** - only organization wide calendars are enabled
- **system** - only system-wide calendars are enabled

## Implementation

The list of system calendars is stored in the <a href="https://github.com/oroinc/OroCalendarBundle/blob/5.0/Entity/SystemCalendar.php" target="_blank">oro_system_calendar</a> table. The **public** field indicates whether a calendar is organization or system-wide. System-wide calendars are marked as `public`.

Both organization and system-wide calendars are implemented as [calendar providers](provider.md#bundle-docs-platform-calendar-bundle-provider). For more implementation details, see the following the source code:

- <a href="https://github.com/oroinc/OroCalendarBundle/blob/5.0/Provider/SystemCalendarProvider.php" target="_blank">SystemCalendarProvider</a> - responsible for **organization wide calendars**
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/5.0/Provider/PublicCalendarProvider.php" target="_blank">PublicCalendarProvider</a> - responsible for **system wide calendars**

<!-- Frontend -->
