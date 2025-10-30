<a id="bundle-docs-platform-platform-bundle-number-sequence-management"></a>

# Number Sequence Management

OroPlatform provides a thread-safe system for generating unique sequential numbers for entities such as invoices, orders, or other business documents.

## NumberSequence Entity

The `Oro\Bundle\PlatformBundle\Entity\NumberSequence` stores sequence states in the database with the following fields:

* `sequenceType` – Defines the sequence purpose (e.g., `invoice`, `order`).
* `discriminatorType` – Specifies the isolation level (e.g., `organization_periodic`).
* `discriminatorValue` – Provides the context (e.g., `42:2025-03` for organization 42 in March 2025).
* `number` – The current numeric value of the sequence.

## NumberSequenceManager

The `Oro\Bundle\PlatformBundle\NumberSequence\Manager\GenericNumberSequenceManager` class is used to manage numeric sequences for business entities.
It implements the `Oro\Bundle\PlatformBundle\NumberSequence\Manager\NumberSequenceManagerInterface` interface and provides the following methods:

* `nextNumber(): int`
  Returns the next available number in the sequence and increments it atomically.
* `resetSequence(int $number = 0): void`
  Resets the sequence to the specified number (default: 0).
* `reserveSequence(int $size): array<int>`
  Reserves a batch of sequential numbers for use in bulk operations.

**Thread Safety**
All operations are wrapped in transactions and use row-level database locking for concurrency control.

**Example**:

```php
$manager = new GenericNumberSequenceManager($doctrine, 'invoice', 'organization_periodic', '42:2025-03');
$nextNumber = $manager->nextNumber(); // Returns 124
```

## Reusing for Other Entities

To use number sequences for custom entities like orders:

* **Define Parameters**:
  : * `sequenceType`: e.g., `order`
    * `discriminatorType`: e.g., `organization_global`
    * `discriminatorValue`: e.g., `42`
* **Implement a Generator**: Use `NumberSequenceManager` to generate numbers.
* **Register a Listener**: Trigger generation during entity persistence.
* **Configure Services**: Register your components as services in your bundle.

**Example: Order Number Generator** (e.g., `ORD-00123`):

*src/Acme/Bundle/DemoBundle/Generator/CustomOrderNumberGenerator.php*
```php

namespace Acme\Bundle\DemoBundle\Generator;

use Doctrine\Persistence\ManagerRegistry;
use Oro\Bundle\OrderBundle\Entity\Order;
use Oro\Bundle\PlatformBundle\NumberSequence\Manager\GenericNumberSequenceManager;

class CustomOrderNumberGenerator
{
    public function __construct(
        private readonly ManagerRegistry $doctrine
    ) {
    }

    public function generate(Order $order): string
    {
        $organizationId = $order->getOrganization()?->getId();
        $sequenceManager = new GenericNumberSequenceManager(
            $this->doctrine,
            'order',
            'organization_global',
            (string)$organizationId
        );

        $number = $sequenceManager->nextNumber();
        return sprintf('ORD-%05d', $number); // e.g., ORD-00123
    }
}
```

*src/Acme/Bundle/DemoBundle/EventListener/CustomOrderNumberListener.php*
```php

namespace Acme\Bundle\DemoBundle\EventListener;

use Acme\Bundle\DemoBundle\Generator\CustomOrderNumberGenerator;
use Doctrine\ORM\Event\PostPersistEventArgs;
use Oro\Bundle\OrderBundle\Entity\Order;

class CustomOrderNumberListener
{
    public function __construct(
        private readonly CustomOrderNumberGenerator $generator
    ) {
    }

    public function postPersist(PostPersistEventArgs $args): void
    {
        $entity = $args->getObject();
        if (!$entity instanceof Order || $entity->getIdentifier()) {
            return;
        }

        $orderIdentifier = $this->generator->generate($entity);
        $entity->setIdentifier($orderIdentifier);
        $args->getObjectManager()->flush();
    }
}
```

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_demo.generator.order_number:
        class: Acme\Bundle\DemoBundle\Generator\CustomOrderNumberGenerator
        arguments:
            - '@doctrine'
        
    acme_demo.listener.order_number:
        class: Acme\Bundle\DemoBundle\EventListener\CustomOrderNumberListener
        arguments:
            - '@acme_demo.generator.order_number'
        tags:
            - { name: doctrine.event_listener, event: postPersist }
```

## Automatic Sequence Cleanup

OroPlatform provides a built-in mechanism to clean up old number sequences via a daily cron command.

1. **Cron command** `oro:cron:platform:delete-old-number-sequences` runs daily and schedules cleanup tasks.
2. **Message Queue** sends a message to the topic `Oro\Bundle\PlatformBundle\Async\Topic\DeleteOldNumberSequenceTopic`.
3. **Asynchronous handler** `Oro\Bundle\PlatformBundle\Async\DeleteOldNumberSequenceProcessor` dispatches a `Oro\Bundle\PlatformBundle\Event\DeleteOldNumberSequenceEvent`.
4. **Event listener** `Oro\Bundle\PlatformBundle\EventListener\DeleteOldNumberSequenceEventListener` receives the event and removes old sequences, keeping the latest one.

To enable automatic cleanup for your sequence type, you can:

* **Use built-in listener with service definition**

Use the provided `Oro\Bundle\PlatformBundle\EventListener\DeleteOldNumberSequenceEventListener` and supply the desired arguments via service definition:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_demo.event_listener.delete_old_number_sequence:
        class: Oro\Bundle\PlatformBundle\EventListener\DeleteOldNumberSequenceEventListener
        arguments:
            - '@doctrine'
            - 'invoice' # You can specify any sequence type here, e.g., 'order'
            - 'organization_periodic' # Likewise, this is a free-form discriminator type
        calls:
            - [ setLogger, [ '@logger' ] ]
        tags:
            - { name: kernel.event_listener, event: Oro\Bundle\PlatformBundle\Event\DeleteOldNumberSequenceEvent, method: onDeleteOldNumberSequence }
            - { name: monolog.logger, channel: oro_invoice }
```

* **Implement a custom listener**

If your application requires more advanced logic (e.g., keeping sequences for the last 3 months, or based on organization), you can create a custom listener for the `Oro\Bundle\PlatformBundle\Event\DeleteOldNumberSequenceEvent`:
Register the custom listener in your bundle’s service configuration, just like the default one, and subscribe it to the `Oro\Bundle\PlatformBundle\Event\DeleteOldNumberSequenceEvent`.

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_invoice.event_listener.custom_invoice_cleanup:
        class: Acme\Bundle\DemoBundle\EventListener\CustomOrderSequenceCleanupListener
        arguments:
            - '@doctrine'
        tags:
            - { name: kernel.event_listener, event: Oro\Bundle\PlatformBundle\Event\DeleteOldNumberSequenceEvent, method: onDeleteOldNumberSequence }
```

*src/Acme/Bundle/DemoBundle/EventListener/CustomOrderSequenceCleanupListener.php*
```php

namespace Acme\Bundle\DemoBundle\EventListener;

use Oro\Bundle\PlatformBundle\Event\DeleteOldNumberSequenceEvent;
use Doctrine\Persistence\ManagerRegistry;
use Oro\Bundle\PlatformBundle\Entity\NumberSequence;

class CustomOrderSequenceCleanupListener
{
    public function __construct(
        private readonly ManagerRegistry $doctrine
    ) {
    }

    public function onDeleteOldNumberSequence(DeleteOldNumberSequenceEvent $event): void
    {
        if (
            $event->getSequenceType() !== 'order' ||
            $event->getDiscriminatorType() !== 'organization_periodic'
        ) {
            return;
        }

        $cutoffDate = new \DateTime('-3 months');
        $repository = $this->doctrine->getRepository(NumberSequence::class);

        $oldSequences = $repository->findOldSequences('order', 'organization_periodic', $cutoffDate);

        $manager = $this->doctrine->getManagerForClass(NumberSequence::class);
        foreach ($oldSequences as $sequence) {
            $manager->remove($sequence);
        }

        $manager->flush();
    }
}
```
