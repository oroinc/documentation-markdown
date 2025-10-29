# CLI Commands (PlatformBundle)

## oro:platform:optional-listeners

The oro:platform:optional-listeners command lists optional Doctrine listeners that can be disabled when running console commands by using the –disabled-listeners option.

```none
php bin/console oro:platform:optional-listeners
```

<a id="oro-cron-platform-delete-old-number-sequences-command"></a>

## oro:cron:platform:delete-old-number-sequences

The oro:cron:platform:delete-old-number-sequences command schedules deletion of old number sequences that are no longer needed. This is a cron command that runs daily at midnight and uses message queue for asynchronous processing.

```none
php bin/console oro:cron:platform:delete-old-number-sequences
```

The command only executes when number sequences exist in the database and processes deletion by grouping sequences by type and discriminator for efficient batch processing.
