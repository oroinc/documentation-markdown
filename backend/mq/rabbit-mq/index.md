<a id="op-structure-mq-rabbitmq-intro"></a>

<a id="op-structure-mq-rabbitmq"></a>

# RabbitMQ (Enterprise Edition Only)

## AmqpMessageQueue Component

The component adds a message queue to your application through
different transports. It is built from several layers.

The lowest layer, Transport, abstracts the transport protocol.

The Consumption layer runs on top of the Transport layer. It provides the
tools to consume messages, such as the CLI command, signal handling, logging,
and extensions.

The Client layer lets you start `producing\consuming` messages with as
little configuration as possible.

## Installation

To use the AMQP transport, install RabbitMQ **version 3.7.21** and above. Follow
the <a href="https://www.rabbitmq.com/download.html" target="_blank">download and installation manual</a>.

After installation, check that all the required plugins are installed and
enabled.

## Minimum Permissions

#### NOTE
You might want to read more on <a href="https://www.rabbitmq.com/access-control.html" target="_blank">access control</a>.

Your credentials must meet the following minimum requirements:

- You have access to the requested rabbitmq’s virtual host (`/` by
  default).
- You have the following permissions: `configure`, `write`,
  `read`. The value can be the default `.*` or a stricter
  `oro\..*`.

## RabbitMQ Plugins

### Required plugins

| Plugin name                                  | Version   | Appointment                                                                                                                                                                                                           |
|----------------------------------------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| rabbitmq_del<br/>ayed_message<br/>\_exchange | 3.8.0     | A plugin that adds delayed-messaging (or<br/>scheduled-messaging) to RabbitMQ.<br/><a href="https://github.com/rabbitmq/rabbitmq-delayed-message-exchange" target="_blank">Read more on Delayed Message Exchange</a>. |

The `rabbitmq_delayed_message_exchange` plugin is required but is not
installed by default, so you must download, install, and enable it.

To download it, use the following command:

```none
wget https://github.com/rabbitmq/rabbitmq-delayed-message-exchange/releases/download/v3.8.0/rabbitmq_delayed_message_exchange-3.8.0.ez -P $RABBITMQ_HOME/plugins
```

To enable it, use the following command:

```none
rabbitmq-plugins enable --offline rabbitmq_delayed_message_exchange
```

### Recommended plugins

| Plugin name         | Version   | Appointment                                                                                                                                                                                      |
|---------------------|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| rabbitmq_management | 3.8.\*    | Provides an HTTP-based API<br/>for management and<br/>monitoring of your RabbitMQ<br/>server.<br/><a href="https://www.rabbitmq.com/management.html" target="_blank">Read more on Management</a> |

### Plugins management

To enable plugins, use the `rabbitmq-plugins` tool:
`rabbitmq-plugins enable plugin-name`

And to disable plugins again, use:
`rabbitmq-plugins disable plugin-name`

To see the list of enabled plugins, use:
`rabbitmq-plugins list  -e`

You will see something like:

```none
[E*] rabbitmq_delayed_message_exchange 3.8.0
[E*] rabbitmq_management               3.8.2
[e*] rabbitmq_management_agent         3.8.2
[e*] rabbitmq_web_dispatch             3.8.2
```

The sign `[E*]` means that the plugin was explicitly enabled, i.e.
somebody enabled it manually. The sign `[e*]` means the plugin was
implicitly enabled, i.e. enabled automatically as it was required for
a different enabled plugin.

* <a href="https://www.rabbitmq.com/community-plugins.html" target="_blank">More about RabbitMQ plugins</a>
* <a href="https://www.rabbitmq.com/plugins.html" target="_blank">More about RabbitMQ plugins</a>

## Queues

If you use only this component, you can create as many queues as you
need. If you use the Client abstraction with this transport, two queues
are created: `oro.default` and `oro.default.delayed`. The first keeps
all sent messages; the second keeps broken messages that have to be delayed
and redelivered later. You can still add more queues by explicitly
configuring the message processor `destinationName` option.

## Default Queue Presets

### Exchanges

| Name                | Type              | Features                              |
|---------------------|-------------------|---------------------------------------|
| oro.default         | fanout            | durable: true                         |
| oro.default.delayed | x-delayed-message | durable: true; x-delayed-type: fanout |

### Queues

| Name        | Features                         |
|-------------|----------------------------------|
| oro.default | durable: true; x-max-priority: 4 |

## Delaying Messages

To use delayed messages with the RabbitMQ broker, you must install
its plugin. Read more on <a href="https://www.rabbitmq.com/blog/2015/04/16/scheduling-messages-with-rabbitmq/" target="_blank">scheduling messages on RabbitMQ website</a>.

## Usage

Usage is similar to the message queue component. This section shows how to
get an AMQP connection, assuming RabbitMQ is used as a broker with minimum
configuration.

```php
use Oro\Component\AmqpMessageQueue\Transport\Amqp\AmqpConnection;

$connection = AmqpConnection::createFromConfig([
    'host' => '127.0.0.1',
    'port' => 5672,
    'user' =>  'guest',
    'password' => 'guest',
    'vhost' => '/',
]);
```

To use the component with a Symfony application, first register the AMQP
transport factory, then tell the message queue bundle to use it.

```php
namespace Oro\Bundle\AmqpMessageQueueBundle;

use Oro\Bundle\MessageQueueBundle\DependencyInjection\OroMessageQueueExtension;
use Oro\Component\AmqpMessageQueue\DependencyInjection\AmqpTransportFactory;
use Symfony\Component\DependencyInjection\ContainerBuilder;
use Symfony\Component\HttpKernel\Bundle\Bundle;

class AcmeCoreBundle extends Bundle
{
    /**
     * {@inheritdoc}
     */
    public function build(ContainerBuilder $container): void
    {
        parent::build($container);

        /** @var OroMessageQueueExtension $extension */
        $extension = $container->getExtension('oro_message_queue');
        $extension->addTransportFactory(new AmqpTransportFactory());
    }
}
```

#### TIP
You can use AmqpMessageQueueBundle to register the factory automatically

You can use the `ORO_MQ_DSN` environment variable:

```bash
ORO_MQ_DSN=amqp://guest:guest@localhost:5672/%2Fmaster
```

When configuring a virtual host (vhost), make sure the vhost is URL encoded.
If no vhost is provided, the default value `/` is used.
For example, the vhost `/master` is URL encoded as `%2Fmaster`, and the vhost `master` is URL encoded as `master`.

## RabbitMQ Useful Hints

- If the `rabbitmq_management` plugin is enabled, you can view the
  RabbitMQ default web interface at `http://localhost:15672/`.
  <a href="https://www.rabbitmq.com/management.html" target="_blank">Read more on Management</a>.
- To temporarily stop RabbitMQ, run `rabbitmqctl stop_app`. This stops
  the RabbitMQ application but leaves the Erlang node running. Resume it
  with `rabbitmqctl start_app`. <a href="https://www.rabbitmq.com/rabbitmqctl.8.html" target="_blank">Read more on rabbitmqctl(8)</a>.

<!-- Frontend -->
