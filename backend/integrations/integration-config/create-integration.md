<a id="dev-integrations-integrations-config"></a>

# Basic Implementation

Integrating other applications requires to implement some services that form the integration
skeleton:

* [Create a New Channel](#cookbook-integration-channel)
* [Read Data Using a Transport](#cookbook-integration-transport)
* [Connect Data to Your Entities](#cookbook-integration-connector)

<a id="cookbook-integration-channel"></a>

## Create a New Channel

The first step is to define a new channel. A channel is the way to make your integration visible in
the integration section of the admin interface. A channel is a class that has to implement the
`Oro\Bundle\IntegrationBundle\Provider\ChannelInterface`:

```php
namespace AppBundle\Integration;

use Oro\Bundle\IntegrationBundle\Provider\ChannelInterface;

class TaskChannel implements ChannelInterface
{
    public function getLabel()
    {
        return 'app.task_channel.label';
    }
}
```

The `ChannelInterface` requires you to interface the `getLabel()` method which is a translation key
that will be shown to the user in the UI after being translated.

Additionally, you can implement the `Oro\Bundle\IntegrationBundle\Provider\IconAwareIntegrationInterface`
if you also like to display an icon. You then also need to implement the `getIcon()` method which
returns a path to the icon relative to the project’s web directory:

*src/AppBundle/Integration/TaskChannel.php*
```php
     namespace AppBundle\Integration;

     // ...
     use Oro\Bundle\IntegrationBundle\Provider\IconAwareIntegrationInterface;

     class TaskChannel implements ChannelInterface, IconAwareIntegrationInterface
     {
         // ...

         public function getIcon()
         {
             return 'icons/task.png';
         }
     }
```

After having created the class you need to make it available in the user interface by registering
it as a service and tag it with the `oro_integration.channel` tag and configure the `type`
attribute which must be a unique value that is used internally by the OroIntegrationBundle to refer
to the channel:

*src/AppBundle/Resources/config/integration.yml*
```yaml
 services:
     app.integration.task:
         class: AppBundle\Integration\TaskChannel
         tags:
             - { name: oro_integration.channel, type: app_channel }
```

<a id="cookbook-integration-transport"></a>

## Read Data Using a Transport

For every channel you can define several ways to read the data from your external application (for
example, either via SOAP or a HTTP REST API). This concept is called a transport. A class providing
such a transport must implement the `Oro\Bundle\IntegrationBundle\Provider\TransportInterface`.
This interface requires four methods to be implemented:

`init(Transport $transport)`
: Initializes the transport. The passed object contains the settings for this transport that was
  configured using the form type identified by the name returned by `getSettingsFormType()`. It
  is an instance of the class configured by the `getSettingsEntityFQCN()` method.

`getLabel()`
: The translation key used to display the transport label in the UI.

`getSettingsFormType()`
: The FQCN of the form type that is used to let the user configure transport specific settings
  (for example, access credentials for API endpoints).

`getSettingsEntityFQCN()`
: The fully-qualified class name of the entity that stores the settings configured through the
  aforementioned form type (this should be a subclass of `Oro\Bundle\IntegrationBundle\Entity\Transport`).

Then, register your transport as a service and tag it with the `oro_integration.transport` tag.
Use the `channel_type` attribute to define the channel the transport is connected with. You need
to give the transport an identifier using the `type` attribute that must be unique across the
channel:

*src/AppBundle/Resources/config/integration.yml*
```yaml
     services:
         app.integration.transport.rest:
              class: AppBundle\Integration\RestTransport
             tags:
                 - { name: oro_integration.transport, channel_type: app_channel, type: rest }
```

<a id="cookbook-integration-connector"></a>

## Connect Data to Your Entities

#### NOTE
Please note that this step is necessary when you need to import-export data between your database and the third-party system (e.g. synchronize tasks created in your Oro instance and other application, import/export cart items). Omit this step if you use this instruction to add an integration that requests and receives only credentials/tokens and a short list of available options.

Your final step is to implement the `Oro\Bundle\IntegrationBundle\Provider\ConnectorInterface`:

`getLabel()`
: The translation key used to display the connector label in the UI.

`getImportExportEntityFQCN()`
: The fully-qualified class name of the entities being imported.

`getImportJobName()`
: The job name that handles the import.

`getType()`
: A string that identifies the connector. This must be unique throughout the channel.

*src/AppBundle/Integration/TaskConnector.php*
```php
 namespace AppBundle\Integration;

 use Oro\Bundle\IntegrationBundle\Provider\ConnectorInterface;

 class TaskConnector implements ConnectorInterface
 {
     public function getLabel()
     {
         return 'app.connector.task.label';
     }

     public function getImportExportEntityFQCN()
     {
         return 'AppBundle\Entity\Task';
     }

     public function getImportJobName()
     {
         return 'app_task_import';
     }

     public function getType()
     {
         return 'task';
     }
 }
```

The class implementing the `ConnectorInterface` must then be registered as a service tagged with
`oro_integration.connector`. Use the `channel_type` attribute to define the channel that the
connector is associated with. The `type` attribute must get the same value that is returned by
the connector’s `getType()` method:

*src/AppBundle/Resources/config/integration.yml*
```yaml
         services:
             class: AppBundle\Integration\TaskConnector
             tags:
                 - { name: oro_integration.connector, channel_type: app_channel, type: task }
```

<!-- Frontend -->
