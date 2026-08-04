<!-- meta: description = Message queue concept and architecture guides -->

<a id="op-structure-mq-index"></a>

<a id="op-structure-mq"></a>

# Message Queue

## Concepts

Message queues provide an asynchronous communications protocol: the
sender and the receiver of the message do not need to interact with the
message queue at the same time. Messages placed onto the queue are stored
until the recipient retrieves them. A message has no information about the
previous and next messages.

Therefore, use a message queue if:

- A process can be executed asynchronously.
- A process does not affect user experience.
- Processes need to be executed in parallel for faster performance.
- You need a guarantee of processing.
- You need scalability.

For more information, see the following external resources:

- <a href="http://www.ibm.com/support/knowledgecenter/SSFKSJ_9.0.0/com.ibm.mq.pro.doc/q002620_.html" target="_blank">What is Message Queue</a>
- <a href="https://www.iron.io/top-10-uses-for-message-queue/" target="_blank">Message Queue Benefits</a>
  (most of them are applicable to Oro Message Queue Component)
- <a href="https://www.rabbitmq.com/tutorials/tutorial-one-php.html" target="_blank">RabbitMQ Introduction</a>

## DBAL Transport

[DBAL transport options](#op-structure-mq-mq-bundle-dbal)

### DBAL Broker

The <a href="https://github.com/oroinc/platform/tree/5.1/src/Oro/Bundle/MessageQueueBundle" target="_blank">OroMessageQueueBundle</a> implements the DBAL broker. Because the bundle is part of OroPlatform, this broker is available in all Oro applications out-of-the-box.

The DBAL broker uses application database tables for message storage.

This broker requires minimal setup and configuration and is available by default in every Oro application.

However, since RDBMS is not designed to work as a message queue, the DBAL broker type has some limitations:

* You cannot use an event-driven model to listen for new inserts into the DB. Instead, the DBAL broker polls the DB for new messages. By default it runs this query once per second, so each consumer receives only one message per second. Use the *polling_interval* option to change this value, but keep in mind that low values may cause DB load.
* When the consumer receives a message, it updates a DB record with a unique identifier so no other consumer can receive it. Once the job is done and the message is acknowledged, the consumer removes this record from the DB. This is the best case, but errors can happen. For instance, a fatal error can end the consumer process, leaving the message locked and stuck in the DB. To handle such cases, RedeliverOrphanMessagesExtension periodically searches for messages that are consumed but not acknowledged and redelivers them.

<a id="op-structure-mq-mq-bundle-dbal"></a>

### DBAL Transport Options and Limitations

#### Options

```yaml
oro_message_queue:
  transport:
    default: 'dbal'
    dbal:
      connection: default                  # doctrine dbal connection name
      table: oro_message_queue             # table name where messages will be stored
      pid_file_dir: /tmp/oro-message-queue # RedeliverOrphanMessagesExtension stores consumer pid files here
      consumer_process_pattern: ':consume' # used by RedeliverOrphanMessagesExtension to check the working or non-working consumers
                                           # (see limitations section for more details)
      polling_interval: 1000               # consumer polling interval in milliseconds
                                           # (see limitations section for more details)
```

#### Limitations

As RDBMS are not designed to work as message queue, the implementation has several limitations.

- You cannot use an event-driven model to listen for new inserts into the DB. Instead, the DBAL broker polls the DB for new messages. By default it
  runs this query once per second, so every consumer receives only one message per second. Use the `polling_interval` option
  to change this value, but low values may cause DB load.
- When the consumer receives a message, it updates the DB record with a unique identifier so no other consumer can receive it. After the job is done and the message is acknowledged, the consumer removes this record from the DB. This is the best case, but exceptions may occur. For instance, a fatal error can end the message consumer process while a blocking message remains in the DB. To handle such cases, the `RedeliverOrphanMessagesExtension` periodically searches for messages that are consumed but not acknowledged and redelivers them.

## AMQP Transport (RabbitMQ)

### RabbitMQ Broker

The RabbitMQ broker comes with Enterprise Editions of Oro applications.

<a href="https://www.rabbitmq.com/" target="_blank">RabbitMQ</a> is one of the most popular Message Queue brokers that supports many features and messaging protocols.

Oro’s RabbitMQ integration is built on the <a href="https://www.rabbitmq.com/tutorials/amqp-concepts.html" target="_blank">AMQP</a> protocol and supports most AMQP features actively used in Oro applications, including:

* Multiple Queues
* Separate Consumer pools for different queues
* Routing of messages from Exchange to the different queues based on Message Topic, Message Headers, etc.

The main drawback of the RabbitMQ broker is that it is more complicated to set up and configure than the DBAL broker.

### AMQP (RabbitMQ) Transport

RabbitMQ delivers messages better and faster than DBAL.
Use RabbitMQ when possible.

#### Options

The application reads the config settings from the `ORO_MQ_DSN`
environment variable (a user named guest with the default password guest,
granted full access to the / virtual host). The format is as follows: `amqp://guest:guest@localhost:5672`.
The default value for the `ORO_MQ_DSN` environment variable is set in the config/config.yml file:

*config/config.yml*
```yaml
 oro_message_queue:
     client: ~
 parameters:
     message_queue_transport_dsn: '%env(ORO_MQ_DSN)%'
     env(ORO_MQ_DSN): 'dbal:'
```

#### BUSINESS TIP
#### Business Tip

Looking for the <a href="https://oroinc.com/b2b-ecommerce/b2b-ecommerce-comparison" target="_blank">open-source B2B eCommerce platform</a>? Our platform comparison page can help you with the decision-making.

**See Also**

* [Message Queue Architecture Guide](../architecture/tech-stack/message-queue.md#op-structure-mq-complete)

<!-- Frontend -->
