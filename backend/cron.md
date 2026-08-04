<!-- meta: description = Instructions on the time-based cron jobs setup and configuration in the Oro applications for the backend developers -->

<a id="dev-guide-system-cron-jobs"></a>

# Cron

Business applications often need to run regular time-based background jobs. These jobs can be maintenance tasks, such as checking for updates or synchronizing data between integrated systems, or business-related tasks, such as generating reports, sending emails, or making timely-based shifts in tasks determined by your business process flows.

These time-based tasks can be diverse and complicated, so a good way to implement them is to create specific program components.

To help you create and schedule such components, OroPlatform provides the [OroCronBundle](../bundles/platform/CronBundle/index.md#bundle-docs-platform-cron-bundle). It makes it considerably easier to run Symfony Console commands through cronjobs (on UNIX-based operating systems) or the Windows task scheduler.

The OroCronBundle provides two interfaces that help to implement console commands that should be executed by the cron:

- <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/CronCommandScheduleDefinitionInterface.php" target="_blank">CronCommandScheduleDefinitionInterface</a> allows defining the console command along with its schedule in a crontab compatible string in the command class.
- <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/CronCommandActivationInterface.php" target="_blank">CronCommandActivationInterface</a> allows defining a conditional logic for the cron command.

The **oro:cron:definitions:load** command scans for all commands from the oro:cron namespace that implement the <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/CronCommandScheduleDefinitionInterface.php" target="_blank">CronCommandScheduleDefinitionInterface</a>. For each detected command, it creates a new <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Entity/Schedule.php" target="_blank">Schedule</a> entry and saves it in the database. This command runs on install and update, and you can also run it manually if some cron commands or command definitions change.

The second command is **oro:cron**. It takes all schedules from the database (created by the oro:cron:definitions:load command) and adds the commands that are due to the Message Queue. This command should run every minute.

#### NOTE
Note that oro:cron:definitions:load removes all previously loaded commands from the database. So if other commands add cron commands to the db (such as oro:workflow:definition:load), run them after **oro:cron:definitions:load**.

## Setup and Configuration

To run a set of commands from your application regularly, configure your system to run the **oro:cron** command every minute.

* For UNIX-based systems, set up a crontab entry, as illustrated below:
  > ```none
  > */1 * * * * /path/to/php /path/to/bin/console oro:cron --env=prod > /dev/null
  > ```

  > #### NOTE
  > Some OS flavors require a username (usually root) in the crontab entry:
  > ```none
  > */1 * * * * root /path/to/php /path/to/bin/console oro:cron --env=prod > /dev/null
  > ```
* For Windows, use the Control Panel to configure the Task Scheduler to do the same.
  > #### NOTE
  > This crontab entry does not mean cron commands run every minute. The oro:cron command only adds the due commands to the scheduler, which in turn executes them at the desired time.

<a id="dev-cookbook-system-cron-create-commands"></a>

## Scheduled Commands in OroPlatform

A scheduled command in OroPlatform is a regular Symfony console command that implements additional <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/CronCommandScheduleDefinitionInterface.php" target="_blank">CronCommandScheduleDefinitionInterface</a> and has the **oro:cron** namespace.

Implementing <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/CronCommandScheduleDefinitionInterface.php" target="_blank">CronCommandScheduleDefinitionInterface</a> requires the implementation of the **getDefaultDefinition()** method. It returns the <a href="http://www.unix.com/man-page/linux/5/crontab/" target="_blank">crontab compatible</a> description of when the command should be executed. For example, if a command should run every day five minutes after midnight, the appropriate
value is **5 0 \* \* \***.

*src/Acme/Bundle/DemoBundle/Command/SomeCronCommand.php*
```php
namespace Acme\Bundle\DemoBundle\Command;

use Oro\Bundle\CronBundle\Command\CronCommandScheduleDefinitionInterface;
use Symfony\Component\Console\Command\Command;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class SomeCronCommand extends Command implements CronCommandScheduleDefinitionInterface
{
    protected static $defaultName = 'oro:cron:acme_demo_some';

    #[\Override]
    public function getDefaultDefinition(): string
    {
        return '5 0 * * *';
    }

    #[\Override]
    protected function configure()
    {
        // ...
    }

    #[\Override]
    protected function execute(InputInterface $input, OutputInterface $output)
    {
        // ...
    }
}
```

### Conditional Activation of Cron Commands

By default, cron runs every command each time it triggers. To run a command only when certain conditions are met, implement the <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/CronCommandActivationInterface.php" target="_blank">CronCommandActivationInterface</a> interface and provide the custom activation logic in the **isActive()** method.

### Synchronous Cron Commands

By default, **all cron commands are executed asynchronously** by sending a message to the queue.

To execute a cron command **immediately** when cron triggers it, without sending the message to the queue, implement the <a href="https://github.com/oroinc/platform/blob/7.0/src/Oro/Bundle/CronBundle/Command/SynchronousCommandInterface.php" target="_blank">SynchronousCommandInterface</a> interface. The command then runs as a background process.

#### NOTE
Please note that the synchronous commands must be designed well-performed and should not block process execution as it may affect scheduled execution of other commands.

### Scheduling Cron Commands in DB

After creating the cron command classes, run the **oro:cron:definitions:load** command to schedule them in the DB. The cron command is then ready to be evaluated and executed during the next **oro:cron** command tick.

**Related Topics**

* [View the List of Scheduled Tasks in UI](../user/back-office/system/scheduled-tasks/index.md#book-time-based-command-execution)

<!-- Frontend -->
