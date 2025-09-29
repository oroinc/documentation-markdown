<a id="index-0"></a>

<a id="upgrade-application"></a>

<a id="upgrade"></a>

# Upgrade the Application to the Next Version

This guide explains how to upgrade OroCommerce, OroCRM, or OroPlatform application to the next version in a development environment.

An absolute path to the directory where an application is installed will be used in the guide and will
be referred to as **<application-root-folder>** further in this topic.

#### NOTE
We highly recommend running all the commands in this guide from the same user the web server runs (e.g., **nginx** or **www-data**).

To retrieve a new version and upgrade your Oro application instance, execute the following steps:

1. Navigate to the Oro application root folder.
   ```none
   cd <application-root-folder>
   ```
2. Make sure that no changes require the database schema update.
   ```none
   php bin/console oro:entity-extend:update --dry-run --env=prod
   ```

   The platform update is possible only when the database schema is up-to-date.
3. Switch the application to maintenance mode.
   ```none
   php bin/console lexik:maintenance:lock --env=prod
   ```
4. Stop the cron tasks.
   ```none
   crontab -e
   ```

   Comment this line.
   ```text
   */1 * * * * /usr/bin/php <application-root-folder>/bin/console --env=prod oro:cron >> /dev/null
   ```
5. Stop all running consumers.
6. Create backups of your Database and Code.
7. Get changes.

   **If You Checkout from the GitHub Repository:**

   Pull changes from the Oro application GitHub repository.
   * Add the corresponding ORO application repository as an additional remote by running one of commands below. In the example the new remote name is oro.
     ```bash
     # OroCommerce Community Edition
     git remote add oro git@github.com:oroinc/orocommerce-application.git
     # OroCommerce Enterprise Edition
     git remote add oro git@github.com:oroinc/orocommerce-enterprise-application.git
     # OroCRM Community Edition
     git remote add oro git@github.com:oroinc/crm-application.git
     # OroCRM Enterprise Edition
     git remote add oro git@github.com:oroinc/crm-enterprise-application.git
     # OroPlatform Community Edition
     git remote add oro git@github.com:oroinc/platform-application.git
     # OroCommerce Community Edition for Germany
     git remote add oro git@github.com:oroinc/orocommerce-application-de.git
     # OroCommerce Enterprise Edition for Germany
     git remote add oro git@github.com:oroinc/orocommerce-enterprise-application-de.git
     # OroCommerce Enterprise Edition (without CRM)
     git remote add oro git@github.com:oroinc/orocommerce-enterprise-nocrm-application.git
     ```
   * Fetch tags from the corresponding ORO application repository
     ```bash
     git fetch oro --tags
     ```
   * Checkout the new branch that will contain the code of the upgraded application to the next version
     ```bash
     git checkout -b feature/upgrade
     ```
   * Merge changes from the corresponding ORO application repository to the new branch
     ```bash
     git merge 5.0.7 --allow-unrelated-histories
     ```

     Replace `5.0.7` with the version you upgrade the application to.
   * Resolve conflicts if needed and commit changes

     #### NOTE
     If you have any customization or third-party extensions installed, make sure that:
     : - your changes to the `src/AppKernel.php` file are merged to the new file.
       - your changes to the `src/` folder are merged, and it contains the custom files.
       - your changes to the `composer.json` file are merged into the new file.
       - your changes to the `packages.json` file are merged to the new file.
       - your changes to configuration files in the `config/` folder are merged to the new files.

     ```bash
     git commit
     ```

   **If You Download the Source Code Archive:**

   Download the latest version of the application source code from the download section on <a href="http://www.oroinc.com/" target="_blank">the website</a>:
   * <a href="https://oroinc.com/b2b-ecommerce/download/#source" target="_blank">Download OroCommerce</a>
   * <a href="https://oroinc.com/orocrm/download/#source" target="_blank">Download OroCRM</a>
   * <a href="https://oroinc.com/oroplatform/download/#source" target="_blank">Download OroPlatform</a>

   <br/>

   #### NOTE
   If you have any customization or third-party extensions installed, make sure that:
   : - your changes to the `src/AppKernel.php` file are merged to the new file.
     - your changes to the `src/` folder are merged, and it contains the custom files.
     - your changes to the `composer.json` file are merged into the new file.
     - your changes to the `packages.json` file are merged to the new file.
     - your changes to configuration files in the `config/` folder are merged to the new files.
8. Remove old caches.
   ```none
   rm -rf var/cache/prod/
   ```
9. Set up your project source code with Composer.
   ```none
   composer install --prefer-dist --no-dev
   ```
10. Refer to the `UPGRADE.md` and `CHANGELOG.md` files in the application repository for a list of changes in the code that
    may affect the upgrade of some customizations.
11. Upgrade the platform.
    ```none
    php bin/console oro:platform:update --env=prod
    ```

    #### NOTE
    To speed up the update process, consider using `--schedule-search-reindexation` or `--skip-search-reindexation` option:
    > * `--schedule-search-reindexation` — postpone search reindexation process until the message queue consumer is started (on step 12 below).
    > * `--skip-search-reindexation` — skip search reindexation. Later, you can start it manually using commands
    >   oro:search:reindex to update search index for the specified entities and oro:website-search:reindex to rebuild storefront search index.
    >   See [Search Index: Indexation Process](../architecture/tech-stack/search/index.md#search-index-overview-indexation-process).

    #### NOTE
    When the following options are not provided, they are set up automatically for the `test` environment:
    > * –force
    > * –skip-assets
    > * –skip-translations
    > * –timeout=600

    The verbose mode is always set to debug in the `test` environment.
12. Remove the caches.
    ```none
    php bin/console cache:clear --env=prod
    ```

    or, as an alternative:
    ```none
    rm -rf var/cache/prod/
    php bin/console cache:warmup --env=prod
    ```
13. Enable cron.
    ```none
    crontab -e
    ```

    Uncomment this line.
    ```text
    */1 * * * * /usr/bin/php <application-root-folder>/bin/console --env=prod oro:cron >> /dev/null
    ```
14. Switch your application back to the normal mode from the maintenance mode.
    ```none
    php bin/console lexik:maintenance:unlock --env=prod
    ```
15. Run the consumer(s).
    ```none
    php bin/console oro:message-queue:consume --env=prod
    ```

    #### NOTE
    If PHP bytecode cache tools (e.g., opcache) are used, PHP-FPM (or Apache web server) should be restarted after the upgrade to flush cached bytecode from the previous installation.

**See Also**

* [Deploy Application Changes to a New Environment (Testing or Production)](deploy-the-update.md#deploy-the-update).

#### BUSINESS TIP
# Business Tip

Looking to harness the new trend of digital commerce? Check out our guide on a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B marketplace platform</a>.

<!-- Frontend -->
