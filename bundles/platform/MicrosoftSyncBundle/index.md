<a id="bundle-docs-platform-microsoft-sync-bundle"></a>

# OroMicrosoftSyncBundle

#### HINT
Microsoft 365 calendar synchronization is available starting from OroCRM v4.2.5 as part of the <a href="https://extensions.oroinc.com/orocommerce/extension/oro-microsoft-365-integration/" target="_blank">Oro-Microsoft 365 Integration</a> extension. Task synchronization is available starting from v4.2.6. To check which application version you are running, see the [system information](../../../user/back-office/system/system-information/index.md#system-information).

OroMicrosoftSyncBundle enables integration with Microsoft 365 in the Oro applications via <a href="https://docs.microsoft.com/en-us/graph/" target="_blank">Microsoft Graph API</a>.

The bundle allows to synchronize calendar events and tasks between the Oro application and Microsoft 365.

<a id="bundle-docs-platform-microsoft-sync-bundle-sync-status-command"></a>

## CLI Command to Check Sync Status

Use `oro:microsoft-sync:status` command to check the status of synchronizations with Microsoft 365.
This command shows the list of all supported synchronizations, as well as the following information for each synchronization:

* **Resource Type** - Synchronization type.
* **Enabled** - Indicates whether the synchronization is enabled.
* **In Progress** - Indicates whether the synchronization is currently running.
* **Last Sync At** - The date and time when synchronization was last performed.
* **Next Sync At** - The date and time when synchronization happens next.

```none
php bin/console oro:microsoft-sync:status --current-organization=1 --current-user=1
```

## Related Documentation

* [Configure Microsoft Integration in the Back-Office](../../../user/back-office/system/configuration/system/integrations/microsoft-settings/index.md#configuration-integrations-microsoft)

<!-- Frontend -->
