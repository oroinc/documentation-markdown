<a id="op-structure-mq-logging"></a>

# Logging, Error Handling and Debugging

While consuming a message queue, you may encounter unexpected errors.
This page highlights how to handle errors, work with logs, and investigate unplanned issues that occur during message processing.

## Logs, Output, and Verbosity

Message Queue Consumer uses <a href="https://github.com/symfony/monolog-bundle" target="_blank">MonologBundle</a> to output logs.
To log a message at any level or priority, inject **LoggerInterface** into your *processor* and log errors as described in <a href="https://symfony.com/doc/5.4/logging.html#logging-a-message" target="_blank">Logging with Monolog" Symfony doc</a>.
The consumer console command has different <a href="https://symfony.com/doc/5.4/console/verbosity.html" target="_blank">verbosity levels</a> that determine which messages appear in the output.

| Console option    | Output Errors                  |
|-------------------|--------------------------------|
| `-q` or `--quiet` | `LogLevel::ERROR` and higher   |
| (none)            | `LogLevel::WARNING` and higher |
| `-v`              | `LogLevel::NOTICE` and higher  |
| `-vv`             | `LogLevel::INFO` and higher    |
| `-vvv`            | `LogLevel::DEBUG` and higher   |

`LogLevel::ERROR` and higher are also printed to the `prod.log` file.
To change the minimum log level printed to `prod.log`, use the `oro:logger:level` command, which temporarily changes the configured logging level.
For more details, see the [Temporarily Decrease Log Level](../../../bundles/platform/LoggerBundle/index.md#bundle-docs-platform-logger-bundle) documentation.

#### NOTE
Keep in mind that `prod.log` is just an example. Your log file name may differ depending on your Monolog handlers configuration.

### Processors

Sometimes, it is necessary to add your own data to log extra data. For more details on how to create your own processor and add the `monolog.processor` DIC tag to it, see the related [Processors](../../api/processors.md#web-api-processors) documentation.

### Handlers

Consumer output is based on <a href="https://github.com/Seldaek/monolog" target="_blank">Monolog</a>, so it supports a stack of handlers that write log entries to different locations (for example, files, a database, or Slack).
For more information, see the <a href="https://symfony.com/doc/5.4/logging.html#handlers-writing-logs-to-different-locations" target="_blank">related Symfony documentation</a>.

Handlers are useful when your production environment uses a real-time log service such as <a href="https://cloud.google.com/stackdriver" target="_blank">Google Stackdriver</a>. Read more in the [How to write logs to Stackdriver](../stackdriver.md#dev-guide-mq-stackdriver).

### Formatters

To format the record before logging it to each logging handler, use a Formatter that implements `Monolog\Formatter\FormatterInterface`.

If your production is configured with a real-time log service (<a href="https://www.elastic.co/elk-stack" target="_blank">ELK Stack</a>), read the [related documentation](elk-stack.md#op-structure-mq-elk-stack) on how to write logs to it.

### Console Messages Output

Message Queue Consumer provides <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/MessageQueueBundle/Log/Handler/ConsoleHandler.php" target="_blank">ConsoleHandler</a> that listens to console events and writes log messages to the console output depending on the console verbosity. It uses a <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/MessageQueueBundle/Log/Formatter/ConsoleFormatter.php" target="_blank">ConsoleFormatter</a> to format the record before logging it. The record format pattern is shown below:

```php
"%datetime% %start_tag%%channel%.%level_name%%end_tag%: %message%%context%%extra%\n"
```

## Consumer Heartbeat

An administrator must be informed about the state of consumers in the system (whether there is at least one alive).

This is covered by the Consumer Heartbeat functionality that works in the following way:

* On start and after every configured time period, each consumer calls the `tick` method of the <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/MessageQueueBundle/Consumption/ConsumerHeartbeat.php" target="_blank">ConsumerHeartbeat</a> service that informs the system that the consumer is alive.
* The <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/MessageQueueBundle/Command/ConsumerHeartbeatCommand.php" target="_blank">oro:cron:message-queue:consumer_heartbeat_check</a> cron command is periodically executed to check consumers’ state. If no alive consumers found, the `oro/message_queue_state` socket message is sent notifying all logged-in users that the system may work incorrectly (because consumers are not available).
* The same check is also performed when a user logs in. This is done to notify users about the problem as soon as possible.

The check period can be changed in the application configuration file using the `consumer_heartbeat_update_period` option:

```yaml
oro_message_queue:
    consumer:
        heartbeat_update_period: 20 #the update period was set to 20 minutes
```

The default value of the `heartbeat_update_period` option is 15 minutes.

To disable the Consumer Heartbeat functionality, set the `heartbeat_update_period` option to 0.

## Consumer Interruption

### Friendly Consumer Interruption

Sometimes you need to interrupt the consumer while it consumes and processes messages, for example to avoid **not actual cached data**, **maintenance mode**, or **memory leaks**. You may also want to limit the messages or processing time during **debugging**, or for any other reason to stop the consumer. Below is a list of friendly consumer interruptions:

| Output                                                                                                         | Description                                                                                                                                                                                                      |
|----------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: Interrupt execution.`                       | Consumer was interrupted with stop signal: `SIGTERM`, `SIGQUIT` or `SIGINT`                                                                                                                                      |
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: The limit time has passed.`                 | Passed time limit configured with command option `--time-limit`                                                                                                                                                  |
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: The message limit reached.`                 | Passed message limit configured with command option `--message-limit`                                                                                                                                            |
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: The memory limit reached.`                  | Passed time limit configured with command option `--memory-limit`                                                                                                                                                |
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: The cache was cleared.`                     | Cache was cleared (it also will be triggered after saving *System Configuration*), more details <a href="http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#paragraphs" target="_blank">here</a> |
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: The cache was invalidated.`                 | Schema was updated, and cache was cleared                                                                                                                                                                        |
| `app.WARNING: Consuming interrupted. Queue: "oro.default", reason: The Maintenance mode has been deactivated.` | Maintenance mode was turned off                                                                                                                                                                                  |

Normal interruption occurs only after a message is processed. If an event fires during message processing, the consumer finishes processing the message and then interrupts.

### Unfriendly Consumer Interruption

If the consumer is interrupted abruptly, check the prod.log file. It should contain the following message.

```none
app.ERROR: Consuming interrupted, reason: Something went wrong.
```

The **full exception stack trace** is printed in the console output.

To find the reason for the interruption, use the Fingers Crossed Handler in the monolog configuration. It buffers all logs at the configured log level and prints them to prod.log when an error occurs (triggered by the `console.error` event).

#### NOTE
All logs buffer collected before the error occurred will be erased before receiving the related message. The message will contain the logs record.

#### Example of Fingers Crossed Handler Configuration

To log into all environments, add the following code to `config.yml`. To log only in `prod`, add the code to `config_prod.yml`:

#### NOTE
Out of the box, the Fingers Crossed Handler is already enabled, and you don’t have to configure it manually.

*config/config_prod.yml*
```yaml
 monolog:
     handlers:
         # ...
         main:
             type:         fingers_crossed
             action_level: error
             handler:      grouped
             buffer_size:  100
```

### Interrupting Consumer from Code

Create consumption extension with its own logic:

*src/Acme/Bundle/DemoBundle/Consumption/Extension/CustomExtension.php*
```php
namespace Oro\Component\MessageQueue\Consumption\Extension;

use Oro\Component\MessageQueue\Consumption\AbstractExtension;
use Oro\Component\MessageQueue\Consumption\Context;

class CustomExtension extends AbstractExtension
{
    /**
     * {@inheritdoc}
     */
    public function onPostReceived(Context $context)
    {
        // ... own logic

        if (!$context->isExecutionInterrupted()) {
            $context->setExecutionInterrupted(true);
            $context->setInterruptedReason('Message with reason of interruption.');
        }
    }
}
```

Declare service:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
 services:
     acme_demo.consumption.custom_extension:
         class: Acme\Bundle\DemoBundle\Consumption\Extension\CustomExtension
         public: false
         tags:
             - { name: 'oro_message_queue.consumption.extension', persistent: true }
```

## Errors and Crashes

When the application is running and the consumer is configured, you may encounter unforeseen errors.
Some common errors that may occur during your application’s daily operations:

* Database related errors (connection errors, accessing errors, query errors, data errors)
* File system errors (permission errors, no disk space errors)
* Third-party integrations errors

If one of these errors occurs, the processor returns **REQUEUE** and the message is redelivered.

## Profiling

Below is a list of key variables added to **extra** and shown in the output.

| Variable             | Description                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------|
| `extension`          | Extension class which was caused by log message                                                                         |
| `processor`          | Processor that processes queue messages                                                                                 |
| `message_id`         | Unique message ID                                                                                                       |
| `message_body`       | Message body                                                                                                            |
| `message_properties` | List of message properties that were received from message broker                                                       |
| `message_headers`    | List of message headers that were received from message broker                                                          |
| `message_priority`   | Message priority (responsible for the order in which messages are processed)                                            |
| `memory_usage`       | Current memory usage                                                                                                    |
| `memory_taken`       | Memory usage difference (current memory usage minus memory usage at the beginning of current message processing)        |
| `peak_memory`        | Peak memory usage (maximum value of `memory_usage` from all previous log records related to current message processing) |
| `elapsed_time`       | Time passed since the consumer started current message processing                                                       |

## Separate Message Queue Consumer Logs

If you want to log the **consumer** channel to a different file, create a new handler and configure it to log only messages from the **consumer** channel. You can add this to `config.yml` to log into all environments, or just `config_prod.yml` to log only in `prod`:

```yaml
monolog:
 handlers:
   consumer_buffer:
       type:         fingers_crossed
       action_level: error
       handler:      consumer
       buffer_size:  100
       channels:     [ 'consumer' ] # The channels configuration only works for top-level handlers
   consumer:
       type:         stream
       path:         "%kernel.logs_dir%/consumer_%kernel.environment%.log"
       level:        debug

   # ...

   filtered:
       type:       filter
       min_level: info
       handler:   main
       channels:  [ '!consumer' ] # Exclude 'consumer' channel for main handlers chain
```

## Third Party Logging Systems

* [Writing Logs to Stackdriver](../stackdriver.md#dev-guide-mq-stackdriver)
* [Writing Logs to ELK Stack](elk-stack.md#op-structure-mq-elk-stack)

For more information, see the following external resources:

* <a href="https://github.com/Seldaek/monolog" target="_blank">Monolog</a>
* <a href="https://github.com/symfony/monolog-bundle" target="_blank">MonologBundle</a>
* <a href="https://symfony.com/doc/5.4/logging.html#logging-a-message" target="_blank">Symfony "Logging with Monolog"</a>
* <a href="https://symfony.com/doc/5.4/console/verbosity.html" target="_blank">Symfony Verbosity Levels</a>
* <a href="https://symfony.com/doc/5.4/logging/processors.html" target="_blank">Symfony Logging Processors</a>
* <a href="https://symfony.com/doc/5.4/logging.html#handlers-writing-logs-to-different-locations" target="_blank">Symfony Logging Handlers</a>
* <a href="https://cloud.google.com/stackdriver" target="_blank">Google Stackdriver</a>
* <a href="https://www.elastic.co/elk-stack" target="_blank">ELK Stack: Elasticsearch, Logstash, Kibana</a>

<!-- Frontend -->
