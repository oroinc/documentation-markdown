<a id="bundle-docs-platform-asset-bundle-commands"></a>

# CLI Commands (AssetBundle)

## oro:assets:build

The `oro:assets:build` command runs bin/webpack to build the web assets in all themes.

```none
php bin/console oro:assets:build
```

The assets can be build only for a specific theme if its name is provided as an argument:

```none
php bin/console oro:assets:build <theme-name>[,<theme-name>]
```

```none
php bin/console oro:assets:build default
```

```none
php bin/console oro:assets:build blank
```

```none
php bin/console oro:assets:build admin.oro
```

```none
php bin/console oro:assets:build default,admin.oro
```

The assets can be built by running webpack separately for each enabled theme if the option `--iterate-themes` is provided.

```none
php bin/console oro:assets:build --iterate-themes
```

With `--env=dev`, the assets are built without minification and with source-maps, while with `--env=prod`, the assets are minified and do not include source-maps:

```none
php bin/console oro:assets:build --env=dev
```

or

```none
php bin/console oro:assets:build --env=prod
```

The `--watch (-w)` option can be used to continuously monitor all resolved files and rebuild the necessary assets automatically when any changes are detected:

```none
php bin/console oro:assets:build --watch
```

or

```none
php bin/console oro:assets:build -w
```

#### NOTE
When using the `--watch`, option you should restart the command after you modify the assets configuration in assets.yml files, or it will not be able to detect the changes otherwise.

The `--hot` option turns on the hot module replacement feature. It allows all styles to be updated at runtime without the need for a full page refresh:

```none
php bin/console oro:assets:build --hot
```

The `--key`, `--cert`, `--cacert`, `--pfx` and `--pfxPassphrase` options can be used with the `--hot` option to allow the hot module replacement to work over HTTPS:

```none
php bin/console oro:assets:build --hot --key=<path> --cert=<path> --cacert=<path> --pfx=<path> --pfxPassphrase=<passphrase>
```

The `--force-warmup` option can be used to warm up the asset-config.json cache:

```none
php bin/console oro:assets:build --force-warmup
```

The `--npm-install` option can be used to reinstall npm dependencies in vendor/oro/platform/build folder. It may be required when node_modules contents become corrupted:

```none
php bin/console oro:assets:build --npm-install
```

The `--skip-css`, `--skip-js`, `--skip-babel`, `--skip-sourcemap` and `--skip-rtl` options allow to skip building CSS and JavaScript files, skip transpiling Javascript with Babel, skip building sourcemaps and skip building RTL styles respectively:

```none
php bin/console oro:assets:build --skip-css
```

```none
php bin/console oro:assets:build --skip-js
```

```none
php bin/console oro:assets:build --skip-babel
```

```none
php bin/console oro:assets:build --skip-sourcemap
```

```none
php bin/console oro:assets:build --skip-rtl
```

The `--analyze` option can be used to run BundleAnalyzerPlugin:

```none
php bin/console oro:assets:build --analyze
```

The `--verbose` option can be used to show expanded output information about failed build such as list of processed files and stack trace:

```none
php bin/console oro:assets:build --verbose
```

## oro:assets:install

The `oro:assets:install` command installs and builds assets, dumps JavaScript routes, JavaScript translations, etc.

```none
php bin/console oro:assets:install
```

If the `--symlink` option is provided this command will create symlinks instead of copying the files (it may be especially useful during development):

```none
php bin/console oro:assets:install --symlink
```

The `--relative-symlink` option tells the asset installer to create symlinks with relative paths (available since v5.0.6 of the application):

```none
php bin/console oro:install --relative-symlink
```

You may run individual steps if necessary as follows:

```none
php bin/console fos:js-routing:dump
```

```none
php bin/console oro:localization:dump
```

```none
php bin/console assets:install [--symlink]
```

```none
php bin/console oro:assets:build --npm-install
```

The `--force-debug` option will launch the child commands in the debug mode (be default they are launched with `--no-debug`):

```none
php bin/console oro:assets:install --force-debug other options
```

The `--timeout` option can be used to limit execution time of the child commands:

```none
php bin/console oro:assets:install --timeout=<seconds> other options
```

The `--iterate-themes` option can be used to run webpack for each enabled theme separately:

```none
php bin/console oro:assets:install --iterate-themes other options
```
