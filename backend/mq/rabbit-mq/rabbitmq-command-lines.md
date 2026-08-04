<a id="op-structure-mq-rabbit-command-lines"></a>

# Command Lines

RabbitMQ comes with command line tools which you can use to configure all of your queues, exchanges, etc:

* `rabbitmqctl` for service management and general operator tasks
* `rabbitmqadmin` for operator tasks over HTTP API
* `rabbitmq-plugins` for plugins management

For more information on command lines, see the <a href="https://www.rabbitmq.com/cli.html" target="_blank">RabbitMQ documentation</a>.

## rabbitmqctl

Rabbitmqctl is the original CLI tool that comes with RabbitMQ and does not require additional configuration. For more information, see the <a href="https://www.rabbitmq.com/rabbitmqctl.8.html" target="_blank">RabbitMQ documentation</a>.

## rabbitmqadmin

Rabbitmqadmin is part of the <a href="https://www.rabbitmq.com/management.html" target="_blank">RabbitMQ Management Plugin</a> and can perform the same actions as the Web-based UI.

## rabbitmq-plugins

Rabbitmq-plugins is the original CLI tool that comes with RabbitMQ and does not require additional configuration. For more information, see the <a href="https://www.rabbitmq.com/plugins.html" target="_blank">RabbitMQ documentation</a>.

### Command Line Installation

To use `rabbitmqadmin` as a command line tool, navigate to *http://{hostname}:15672/cli/rabbitmqadmin* and download it.
On UNIX-like operating systems, copy `rabbitmqadmin` to a directory in `PATH`, e.g., `/usr/local/bin`. For more information, see the <a href="https://www.rabbitmq.com/management-cli.html" target="_blank">RabbitMQ documentation</a>.

For more information, see the following external resources:

* <a href="https://www.rabbitmq.com/cli.html" target="_blank">RabbitMQ Command Line Tools</a>
* <a href="https://www.rabbitmq.com/rabbitmqctl.8.html" target="_blank">RabbitMQ CLI Tool</a>
* <a href="https://www.rabbitmq.com/management.html" target="_blank">RabbitMQ Management Plugin</a>
* <a href="https://www.rabbitmq.com/relocate.html" target="_blank">RabbitMQ Management Command Line Tool</a>
* <a href="https://www.rabbitmq.com/plugins.html" target="_blank">RabbitMQ Plugins</a>

<!-- Frontend -->
