<a id="bundle-docs-platform-translation-bundle-commands"></a>

# CLI Commands (TranslationBundle)

<a id="oro-translation-dump-command"></a>

## oro:translation:dump

The `oro:translation:dump` command dumps the translations used by JavaScript code into the predefined public resource files.

```none
php bin/console oro:translation:dump
```

The `--locale` option can be used to dump translations only for the specified locales:

```none
php bin/console oro:translation:dump --locale=<locale1> --locale=<locale2> --locale=<localeN>
```

<a id="oro-translation-load-command"></a>

## oro:translation:load

The `oro:translation:load` command loads translations to the database.

```none
php bin/console oro:translation:load
```

The `--languages` option can be used to limit the list of the loaded languages:

```none
php bin/console oro:translation:load --languages=<language1> --languages=<language2> --languages=<languageN>
```

The `--rebuild-cache` option will trigger the translation cache rebuild after the translations are loaded:

```none
php bin/console oro:translation:load --rebuild-cache
```

<a id="oro-translation-rebuild-cache-command"></a>

## oro:translation:rebuild-cache

To rebuilds the translation cache, use the following commad:

```none
php bin/console oro:translation:rebuild-cache
```

<a id="oro-translation-update-command"></a>

## oro:translation:update

The `oro:translation:update` command downloads and installs a new version of translations for a specified language:

```none
php bin/console oro:translation:update <language>
```

The `--all` option can be used to download and update translations for all installed languages:

```none
php bin/console oro:translation:update --all
```

The command will print the list of all languages installed in the application if run without any options:

```none
php bin/console oro:translation:update
```

<a id="oro-translation-dump-files-command"></a>

## oro:translation:dump-files

The `oro:translation:dump-files` command dumps translations from the database or Crowdin to files
into the translations directory of the application.

```none
php bin/console oro:translation:dump-files --locale=en_US
```

By default, the translations are dumped from the database. You can load translations to the database
via the [back-office UI](../../../user/back-office/system/localization/languages/index.md#localization-languages) or via the [oro:translation:load]() command.

To dump from the Crowdin use the `--source` option:

```none
php bin/console oro:translation:dump-files --locale=en_US --source=crowdin
```

To determine whether only new translations should be applied to existing dumped files, use the `--new-only` option:

```none
php bin/console oro:translation:dump-files --locale=en_US --new-only
```

The default format of the dumped translations is YAML. To specify another format, use the `--format` option:

```none
php bin/console oro:translation:dump-files --locale=en_US --format=xlf
```
