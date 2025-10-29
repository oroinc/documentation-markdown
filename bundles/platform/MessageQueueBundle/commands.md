# CLI Commands (MessageQueueBundle)

## oro:message-queue:consume

The `oro:message-queue:consume` command processes messages from the message-queue using an appropriate message processor based on message headers.

```none
php bin/console oro:message-queue:consume
```

It connects to the default queue, but a different name can be provided as the argument:

```none
php bin/console oro:message-queue:consume <clientDestinationName>
```

The `--message-limit` option can be used to limit the maximum number of messages to consume before exiting:

```none
php bin/console oro:message-queue:consume --message-limit=<number> other options and arguments
```

The `--time-limit` option can be used to restrict the run time. Accepts any date/time value recognized by PHP (see <a href="https://php.net/manual/datetime.formats.php" target="_blank">Supported Date and Time Formats</a>:

```none
php bin/console oro:message-queue:consume --time-limit=<date-time-string> other options and arguments
```

The `--memory-limit` option defines the maximum used memory threshold (megabytes):

```none
php bin/console oro:message-queue:consume --memory-limit=<number> other options and arguments
```

The `--object-limit` option defines the maximum amount of objects in runtime:

```none
php bin/console oro:message-queue:consume --object-limit=<number> other options and arguments
```

The `--gc-limit` option defines the maximum amount GC calls:

```none
php bin/console oro:message-queue:consume --gc-limit=<number> other options and arguments
```

## oro:message-queue:create-queues

The `oro:message-queue:create-queues` command creates the required message queues.

```none
php bin/console oro:message-queue:create-queues
```

## oro:message-queue:destinations

The `oro:message-queue:destinations` command lists available message queue destinations.

```none
php bin/console oro:message-queue:destinations
```

## oro:message-queue:topics

The `oro:message-queue:topics` command lists available message queue topics.

```none
php bin/console oro:message-queue:topics
```

## oro:message-queue:transport:consume

The `oro:message-queue:transport:consume` command consumes message from a specified message queue. The message processor service can be specified as the second argument.

```none
php bin/console oro:message-queue:transport:consume <queue> [processor-service]
```

<!-- Frontend -->
