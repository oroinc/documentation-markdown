<a id="index-0"></a>

<a id="upgrade-application"></a>

<a id="upgrade"></a>

# Upgrade

This guide explains how to upgrade OroCommerce, OroCRM or OroPlatform application to the next version.

An absolute path to the directory where an application is installed will be used in the guide and will
be referred to as **<application-root-folder>** further in this topic.

#### NOTE
We highly recommend running all the commands in this guide from the same user the web server runs (e.g., **nginx** or **www-data**).

## 1. Checkout from the GitHub Repository

To retrieve a new version and upgrade your Oro application instance, execute the following steps:

1. Make sure that there are no changes that require the database schema update.
   ```none
   php bin/console oro:entity-extend:update --dry-run --env=prod
   ```

   The platform update is possible only when the database schema is up-to-date.
2. Go to the Oro application root folder and switch the application to the maintenance mode.
   ```none
   cd <application-root-folder>
   php bin/console lexik:maintenance:lock --env=prod
   ```
3. Stop the cron tasks.
   ```none
   crontab -e
   ```

   Comment this line  .
   ```text
   */1 * * * * /usr/bin/php <application-root-folder>/bin/console --env=prod oro:cron >> /dev/null
   ```
4. Stop all running consumers.
5. Create backups of your Database and Code.
6. Pull changes from the repository.

   #### NOTE
   If you have any customization or third party extensions installed, make sure that:
   : - your changes to `src/AppKernel.php` file are merged to the new file.
     - your changes to `src/` folder are merged and it contains the custom files.
     - your changes to `composer.json` file are merged to the new file.
     - your changes to configuration files in `config/` folder are merged to the new files.

   ```none
   git pull
   git checkout <VERSION TO UPGRADE>
   ```
7. Upgrade the composer dependency and set up the right owner to the retrieved files.
   ```none
   composer install --prefer-dist --no-dev
   ```
8. Refer to the `UPGRADE.md` and `CHANGELOG.md` files in the application repository for a list of changes in the code that
   may affect the upgrade of some customizations.
9. Remove old caches.
   ```none
   rm -rf var/cache/*
   ```
10. Upgrade the platform.

> ```none
> php bin/console oro:platform:update --env=prod
> ```

> #### NOTE
> To speed up the update process, consider using `--schedule-search-reindexation` or
> `--skip-search-reindexation` option:

> * `--schedule-search-reindexation` — postpone search reindexation process until
>   the message queue consumer is started (on step 12 below).
> * `--skip-search-reindexation` — skip search reindexation. Later, you can start it manually using commands
>   oro:search:reindex to update search index for the specified entities and oro:website-search:reindex to rebuild storefront search index.
>   See [Search Index: Indexation Process](../architecture/tech-stack/search-index.md#search-index-overview-indexation-process).

> #### NOTE
> When the following options are not provided, they are set up automatically for the `test` environment:
> : * –force
>   * –skip-assets
>   * –skip-translations
>   * –timeout=600

> The verbose mode is always set to debug in the `test` enviroment.
1. Remove the caches.
   ```none
   php bin/console cache:clear --env=prod
   ```

   or, as alternative:
   ```none
   rm -rf var/cache/*
   php bin/console cache:warmup --env=prod
   ```
2. Enable cron.
   ```none
   crontab -e
   ```

   Uncomment this line.
   ```text
   */1 * * * * /usr/bin/php <application-root-folder>/bin/console --env=prod oro:cron >> /dev/null
   ```
3. Switch your application back to the normal mode from the maintenance mode.
   ```none
   php bin/console lexik:maintenance:unlock --env=prod
   ```
4. Run the consumer(s).
   ```none
   php bin/console oro:message-queue:consume --env=prod
   ```

   #### NOTE
   If PHP bytecode cache tools (e.g., opcache) are used, PHP-FPM (or Apache web server) should be restarted
   after the uprgade to flush cached bytecode from the previous installation.

## 2. Download the Source Code Archive

To retrieve a new version and upgrade your Oro application instance, please execute the following steps:

1. Make sure that there are no changes that require the database schema update.
   ```none
   php bin/console oro:entity-extend:update --dry-run --env=prod
   ```

   The platform update is possible only when the database schema is up-to-date.
2. Go to the Oro application root folder and switch the application to the maintenance mode.
   ```none
   cd <application-root-folder>
   php bin/console lexik:maintenance:lock --env=prod
   ```
3. Stop the cron tasks.
   ```none
   crontab -e
   ```

   Comment this line.
   ```text
   */1 * * * * /usr/bin/php <application-root-folder>/bin/console --env=prod oro:cron >> /dev/null
   ```
4. Stop all running consumers.
5. Create backups of your Database and Code.
6. Download the latest version of the application source code from the download section on <a href="http://www.oroinc.com/" target="_blank">the website</a>:
   * <a href="https://oroinc.com/b2b-ecommerce/download/#source" target="_blank">Download OroCommerce</a>
   * <a href="https://oroinc.com/orocrm/download/#source" target="_blank">Download OroCRM</a>
   * <a href="https://oroinc.com/oroplatform/download/#source" target="_blank">Download OroPlatform</a>
7. Unpack archive and overwrite existing system files.

   #### NOTE
   If you have any customization or third party extensions installed, make sure that:
   : - your changes to `src/AppKernel.php` file are merged to the new file.
     - your changes to `src/` folder are merged and it contains the custom files.
     - your changes to `composer.json` file are merged to the new file.
     - your changes to configuration files in `config/` folder are merged to the new files.
     - upgrade the composer dependency and set up right owner to the retrieved files.
       ```none
       composer update --prefer-dist --no-dev
       ```
8. Refer to the `UPGRADE.md` and `CHANGELOG.md` files in the application folder for a list of changes in the code that
   may affect the upgrade of some customizations.
9. Remove old caches.
   ```none
   rm -rf var/cache/*
   ```
10. Upgrade the platform.

> ```none
> php bin/console oro:platform:update --env=prod
> ```
1. Remove the caches.

> ```none
> php bin/console cache:clear --env=prod
> ```

> or, as alternative:

> ```none
> rm -rf var/cache/*
> php bin/console cache:warmup --env=prod
> ```
1. Enable cron.
   ```none
   crontab -e
   ```

   Uncomment this line.
   ```text
   */1 * * * * /usr/bin/php <application-root-folder>/bin/console --env=prod oro:cron >> /dev/null
   ```
2. Switch your application back to normal mode from the maintenance mode.
   ```none
   php bin/console lexik:maintenance:unlock --env=prod
   ```
3. Run the consumer(s).
   ```none
   php bin/console oro:message-queue:consume --env=prod
   ```

   #### NOTE
   If PHP bytecode cache tools (e.g. opcache) are used, PHP-FPM (or Apache web server) should be restarted
   after the upgrade to flush cached bytecode from the previous installation.

#### BUSINESS TIP
## Business Tip

Looking to harness the new trend of digital commerce? Check out our guide on a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B marketplace platform</a>.

<!-- Frontend -->
