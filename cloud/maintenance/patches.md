<a id="orocloud-maintenance-patches"></a>

# How to Apply Patches

## Apply Patches During Deployment

### Apply Patches Using the <a href="https://github.com/cweagans/composer-patches/blob/1.x/README.md" target="_blank">Composer Patches</a> Plugin

Using the composer patches plugin is a convenient and preferred way to apply patches to files in vendor packages.

The plugin is designed to work with patches applied to files in vendor packages only.

Perform the initial setup and install the plugin with the following sequence of commands:

```bash
composer config --no-plugins allow-plugins.cweagans/composer-patches true
composer config extra.composer-exit-on-patch-failure true
composer config extra.patches-file composer.patches.json
composer require cweagans/composer-patches:~1.0 --no-scripts
```

Regarding the previous block of commands, the plugin is configured to use the list of patches declared in the separate composer.patches.json file.

The contents of the commonly used patch list file look like this:

```json
{
   "patches": {
      "oro/platform": {
         "Oro Platform Readme Comment": "patch/oro/platform/readme_doc_comment.patch"
      }
   }
}
```

The patches node defines the group of patches by package name, and the oro/platform package is one of those. Each item under a group is keyed with a patch description and its path relative to the application root.

It’s important to remember that patches must reference the patched file by relative path to the package it belongs to.

For example, suggest that the patches/oro/platform/readme_doc_comment.patch patch file given above adds a simple comment to the oro/platform package readme file:

```none
--- README.md
+++ README.md
@@ -29,3 +29,5 @@
   * [OroCommerce, OroCRM and OroPlatform Documentation](https://doc.oroinc.com)
   * [Contributing](https://doc.oroinc.com/community/contribute/)
   * [Reporting a Security Issue](https://doc.oroinc.com/community/report-issues/security/)
+
+<!-- This package contains changes made by patches -->
```

Once you have added and configured the patches, you can check their application against the requested files:

```bash
rm -rf vendor; composer install -v
```

### Apply Patches From the Dedicated patch Directory

To unify the process of applying patches during application deployment, the maintenance agent is configured to do it once the code is deployed and the composer installation is completed.

If you need to apply patches to the application, create a patch directory in the root repository location and insert the appropriate files with the .patch extension there.

Remember that if your application supports patch application on its own (for example, via a specific bundle), you need to ensure there are no conflicts between these approaches, and that the same patch is not applied twice.

#### NOTE
Use the following command to make sure that the patch is correct and can be applied before deploying it into production:

```bash
patch -p0 < patch/file.patch
```

## Apply Patches to a Deployed Application

To unify the process of applying patches during application deployment, the maintenance agent has the functionality for applying/reverting patches.

Use the following commands to work with patches:

* **patch:list** - shows the list of applied patches to the current application deployment

```none
➤ Executing task patch:list
 +---------------------+-----------------------------------------------------------------+
 | DATE                | FILE                                                            |
 +---------------------+-----------------------------------------------------------------+
 | 2021-11-03 15:14:54 | /mnt/ocom/app/persistent_shared/patch/20211016150803/test.patch |
 +---------------------+-----------------------------------------------------------------+
```

#### NOTE
Please note that the value in the `FILE` column is used for the patch:revert and patch:view commands as an argument.

* **patch:view** - shows the content of the specified patch, requires the full path to the patch file as an argument.

```none
[ ~]$ orocloud-cli patch:view /mnt/ocom/app/persistent_shared/patch/20211016150803/test.patch
➤ Executing task patch:view
[localhost]
Index: web/app.php
IDEA additional info:
Subsystem: com.intellij.openapi.diff.impl.patch.CharsetEP
<+>UTF-8
===================================================================
--- web/app.php    (date 1536073001000)
+++ web/app.php    (date 1539170812000)
@@ -1,5 +1,9 @@
 <?php

+echo 'testing patches';
+die();
+
+
 use Symfony\Component\ClassLoader\ApcClassLoader;
 use Symfony\Component\HttpFoundation\Request;
✔ Ok
```

* **patch:apply**  - applies a patch. Requires the full path to the patch file as an argument (/mnt/maint-data is suggested), by default the command runs in DRY-RUN mode, which means that changes will not be applied, only validated. Passing the –force option causes the specified patch to be physically applied against your codebase.
* **patch:revert** - reverts a patch, requires the full path to the patch file as an argument (/mnt/maint-data is suggested), by default the command runs in DRY-RUN mode, which means that changes will not be applied, only validated. Passing the –force option causes the specified patch to be physically reverted against your codebase.

Usage examples:

* Revert by a patch, dry-run mode (only shows what will be done):
  ```bash
  orocloud-cli patch:revert /mnt/ocom/app/persistent_shared/patch/20211016150803/test.patch
  ```
* Revert by a patch, force mode (patch will be physically reverted against your codebase):
  ```bash
  orocloud-cli patch:revert /mnt/ocom/app/persistent_shared/patch/20211016150803/test.patch --force
  ```
