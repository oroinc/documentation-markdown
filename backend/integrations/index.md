<!-- meta: description = Practical manuals on integrating data from external systems to the Oro applications for the backend developers -->

<a id="dev-integrations"></a>

# Integrations

Application integration is a layer that allows you to migrate your data or enable communication between two systems.

The topics below provide in-depth information about integrations’ concepts and components to help you get started with creating your integrations.

Choose the model of transferring data to build your integration flow:

* [Configuration](integration-config/index.md)
  * [Basic Implementation](integration-config/create-integration.md)
  * [Configuration Reference](integration-config/configuration-reference.md)
  * [Additional Serializable Fields](integration-config/additional-settings.md)
  * [Reverse Synchronization](integration-config/reverse-sync.md)
  * [Default Owner for Integration Related Entities](integration-config/default-integration-owner.md)
  * [Additional Capabilities](integration-config/additional-capabilities.md)
* [Import and Export](import-export/index.md)
  * [Overview](import-export/overview.md)
  * [Domain Model](import-export/domain-model.md)
  * [Gaufrette](import-export/gaufrette.md)
  * [Fields Configuration](import-export/fields-configuration.md)
  * [Import and Export Entities](import-export/import-export.md)
  * [Events](import-export/events.md)
  * [Extend Entities to Support Bulk Import and Export](import-export/customize-import-export.md)
  * [Accelerate Import](import-export/accelerate-import.md)
  * [Postponing Rows](import-export/rows-postponing.md)
* [Notification Alerts](notification-alerts.md)
  * [Implementation details](notification-alerts.md#implementation-details)
  * [Viewing alerts in back-office](notification-alerts.md#viewing-alerts-in-back-office)
  * [Manipulating alerts in CLI](notification-alerts.md#manipulating-alerts-in-cli)
  * [Automatic outdated alerts cleanup](notification-alerts.md#automatic-outdated-alerts-cleanup)
