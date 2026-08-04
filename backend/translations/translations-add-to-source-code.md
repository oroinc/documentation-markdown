<a id="dev-translation-add-to-source-code"></a>

# Add Translations to Source Code

Out-of-the-box, only base English translations (`en` language code) are loaded from the translation files.
As described in <a href="https://symfony.com/doc/current/translation.html#translation-resource-file-names-and-locations" target="_blank">translation files</a>, these files are located in the Resources/translations directory of any bundle and the translations directory of the application, e.g., Resources/translations/messages.en.yml, Resources/translations/validators.en.yml, etc.

These translations are compiled in the [Symfony translation catalogs](translations.md#dev-translation-symfony-translator), which are sets of PHP files. As a result, these files are cached by <a href="https://www.php.net/manual/en/book.opcache.php" target="_blank">OPcache</a>, so getting these translations is fairly quick.

You can download translations for other languages from [Crowdin](../../community/contribute/code-ui-translations.md#doc-community-ui-translations) or add them manually in the [Back-Office](../../user/back-office/system/localization/translations/index.md#localization-translations-config). These translations load from the database into the application cache, which is slower than reading them from the Symfony translation catalogs.

To minimize performance issues, add them to the source code as described below:

1. Use [oro:translation:dump-files](../../bundles/platform/TranslationBundle/commands.md#oro-translation-dump-files-command) to dump translations to the translations directory of the application.
2. When you have updated the existing translations, use a file comparison tool of your choice to verify the dumped files.
3. Push the files to the version control system (git).

To rebuild Symfony translation catalogs with new translations and remove them from the database, use the `oro:platform:update` command.

Note that languages loaded from the dumped files can no longer be managed via Crowdin in the UI; a developer must manage their data instead.

<!-- Frontend -->
