# Loading Demo Data

To load demo data during installation, run the `oro:install` command with the `--sample-data=y` option.

To load demo data after installation, run:

```none
php bin/console oro:migration:data:load --fixtures-type=demo --env=prod
```

#### TIP
You can use the `--dry-run` option to first check which fixtures will be loaded:

```none
php bin/console oro:migration:data:load --dry-run --fixtures-type=demo --env=prod
```

To load demo data fixtures from the specified package directories, run:

```none
php bin/console oro:package:demo:load
```

#### HINT
See the [oro:install](../../bundles/platform/InstallerBundle/commands.md#bundle-docs-platform-installer-bundle-oro-install-command) command description for more information.
