<a id="orocloud-maintenance-use-upgrade"></a>

#### IMPORTANT
You are viewing the upcoming documentation for OroCloud, scheduled for release later in 2025. For accurate and up-to-date information, please refer only to the documentation of <a href="https://doc.oroinc.com/cloud/" target="_blank">the latest LTS version</a>.

# How to Run Upgrades

## Build

#### IMPORTANT
Migrate to [Environment Type Approach](dif-environments.md#orocloud-diff-environments-environment-type-approach), other approaches are not supported.

To create an application package, run the orocloud-cli app:package:build [git reference] [tag] command:

You will be prompted to enter a tag, branch, or commit to clone the application source file from.
Use a valid tag, branch, or commit from the Oro application repository, for example, the 6.0 branch, the 6.0.2 tag, or the fd05a85 commit.

```bash
$ orocloud-cli app:package:build 6.0.2 6.0.2-20240901

[OK] Build is successful. Package "harborio.oro.cloud/ocom-proj-dev1-reg1/orocommerce-enterprise-application:6.0.2-20240901"
    is ready.
```

Application packages contain vendors, assets, and other files and folders required for application runtime.
Application packages are shared between a single project’s different environment types (dev, stag, uat, prod).

Use –skip-assets-build option when assets are [pre-built](deploy-pre-built-assets.md#orocloud-skip-assets)

To list available application packages, run the orocloud-cli app:package:list command:

```bash
[user@ocom-proj-prod1-maint1 ~]$ orocloud-cli app:package:list
+---------------------+-----------------------------------------------------------------------------------------------+-------------------+
| Push Time           | Package                                                                                       | Label             |
+---------------------+-----------------------------------------------------------------------------------------------+-------------------+
| 2024-09-01 22:12:56 | harborio.oro.cloud/ocom-proj-dev1-reg1/orocommerce-enterprise-application:6.0.2-20240901      | Reference: 6.0.2  |
| 2024-08-01 20:37:28 | harborio.oro.cloud/ocom-proj-uat1-reg1/orocommerce-enterprise-application:6.0.1-20240801      | Reference: 6.0.1  |
+---------------------+-----------------------------------------------------------------------------------------------+-------------------+
```

## Deploy

#### IMPORTANT
Migrate to [Environment Type Approach](dif-environments.md#orocloud-diff-environments-environment-type-approach), other approaches are not supported by Application Packages feature.

<!-- * `orocloud-cli app:package:deploy --source [package]` `orocloud-cli upgrade:source`. -->

#### NOTE
Be aware that only those consumers that ran before the upgrade will run afterward.

#### NOTE
Edit the composer.json scripts section to change application upgrade flow.

#### WARNING
It is recommended that you create a backup before launching an upgrade. If the upgrade does not succeed, you can roll back the application to its previous state and preserve all the data and configuration.

To upgrade the Oro application, you can use the following modes:

#### WARNING
With the rolling upgrade, the source upgrade of the Oro application is not forced into maintenance mode; it runs and stays available for users during the entire upgrade process. This method is safe only when the database does not change during the upgrade, or the versions before, and after the upgrade is simultaneously compatible with the old and new database structure. Usually, these are upgrades to minor versions. Do not drop tables, columns, or entity fields, and do not alter columns or entity field types.

#### IMPORTANT
Upgrade commands remove patches applied using [orocloud-cli patch:apply](patches.md#orocloud-maintenance-patches) command. Use can confirm it interactively or using the –skip-check-patches option.

### Upgrade With Maintenance Mode

To upgrade the Oro application, run the orocloud-cli app:package:deploy [package] command:

```none
orocloud-cli app:package:deploy harborio.oro.cloud/ocom-proj-dev1-reg1/orocommerce-enterprise-application:6.0.2-20240901
```

This command executes the following operations:

1. Enables the maintenance mode
2. Stops the services (consumers, cron, websocket)
3. Performs oro:platform:update
4. Warms up caches

Once the cache warmup is complete, the maintenance mode is turned off, and the upgraded application is ready for use.

### Upgrade Without Maintenance Mode (Rolling Upgrade)

#### WARNING
With the rolling upgrade, the Oro application is not forced into maintenance mode; it runs and stays available for users during the entire upgrade process. This method is safe only when the database does not change during the upgrade, or the versions before and after the upgrade are compatible with the old and new database structure simultaneously. Usually, these are upgrades to minor versions.

#### IMPORTANT
Do not drop tables, columns, or entity fields; do not alter columns and entity fields types.

To perform Oro application upgrade without maintenance mode, run the orocloud-cli app:package:deploy –rolling [package] command:

```none
orocloud-cli app:package:deploy --rolling harborio.oro.cloud/ocom-proj-dev1-reg1/orocommerce-enterprise-application:6.0.2-20240901
```

In the normal operation mode, this command executes the following operations:

1. Performs oro:platform:update
2. Warms up caches
3. Restarts services (consumers, cron, websocket)

### Upgrade Without Maintenance Mode (Source Upgrade)

#### WARNING
With the source upgrade, the Oro application is not forced into maintenance mode; it runs and stays available for users during the upgrade process. This method is safe only when the Doctrine metadata does not change during the upgrade, or the versions before and after the upgrade is simultaneously compatible with the old and new database structure. Usually, these are upgrades to minor versions.

#### IMPORTANT
Do not add new properties to existing Doctrine entities or new Doctrine entities.

To perform Oro application upgrade without maintenance mode, run the orocloud-cli app:package:deploy –source [package] command:

```none
orocloud-cli app:package:deploy --source harborio.oro.cloud/ocom-proj-dev1-reg1/orocommerce-enterprise-application:6.0.2-20240901
```

The purpose of this command is to deploy code changes as quickly as possible.
The difference between this command and the original upgrade:

1. Warms up caches
2. Restarts the related services (consumers, cron, websocket).

#### NOTE
oro:platform:update is not executed.

## Build and Deploy

To build and deploy an application packages at the same time, run the orocloud-cli app:package:upgrade [git reference] [–rolling] [–source] command:

* orocloud-cli app:package:upgrade [git reference] equal to orocloud-cli app:package:build with orocloud-cli app:package:deploy.
* orocloud-cli app:package:upgrade –rolling [git reference] equal to orocloud-cli app:package:build with orocloud-cli app:package:deploy –rolling.
* orocloud-cli app:package:upgrade –source [git reference] equal to orocloud-cli app:package:build with orocloud-cli app:package:deploy –source.
