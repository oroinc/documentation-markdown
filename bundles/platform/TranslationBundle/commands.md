# CLI Commands (TranslationBundle)

## oro:translation:dump

The `oro:translation:dump` command dumps the translations used by JavaScript code into the predefined public resource files.

```none
php bin/console oro:translation:dump
```

The `--locale` option can be used to dump translations only for the specified locales:

```none
php bin/console oro:translation:dump --locale=<locale1> --locale=<locale2> --locale=<localeN>
```

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

## oro:translation:rebuild-cache

To rebuilds the translation cache, use the following commad:

```none
php bin/console oro:translation:rebuild-cache
```

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
