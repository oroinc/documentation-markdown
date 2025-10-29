# Configure Scheduled Tasks in the Back-Office

<a id="index-0"></a>

<a id="book-time-based-command-execution"></a>

## Time-Based Command Execution

Some recurring tasks should be executed on schedule, for example, IMAP synchronization or sending email campaigns to customers). Usually, the operating system should be configured to execute a script to perform these tasks.

With Oro, you can use the <a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/CronBundle" target="_blank">OroCronBundle</a>, which makes it easy to run Symfony Console commands through [cronjobs](../../../../backend/cron.md#dev-guide-system-cron-jobs) (on UNIX-based operating systems) or Windows task scheduler.

Oro applications provide an admin UI page for admin users that displays all scheduled cron commands.

The admin UI located in the **System > Scheduled Tasks** main menu.

On the page, you can see the list of scheduled commands with their names, schedule definition strings, and the filters that allow searching for the required command in the list.

![Scheduled Tasks UI page](user/img/system/scheduled_tasks/scheduled_tasks.png)
<!-- Frontend -->
