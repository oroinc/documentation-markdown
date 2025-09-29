<a id="bundle-docs-platform-navigation-bundle-commands"></a>

# CLI Commands (NavigationBundle)

## oro:navigation:history:clear

The oro:navigation:history:clear command clears old navigation history.

```none
php bin/console oro:navigation:history:clear
```

The –interval option can be used to override the default time interval (1 day) past which a navigation history item is considered old. It accepts any relative date/time format recognized by PHP (see <a href="https://php.net/manual/datetime.formats.php" target="_blank">Supported Date and Time Formats</a>):

```none
php bin/console oro:navigation:history:clear --interval=<relative-date>
```

```none
php bin/console oro:navigation:history:clear --interval="15 minutes"
```

```none
php bin/console oro:navigation:history:clear --interval="3 days"
```

## oro:navigation:menu:reset

The oro:navigation:menu:reset command resets all menu updates.

```none
php bin/console oro:navigation:menu:reset
```

The –user option can be used to reset menu updates for a specific user:

```none
php bin/console oro:navigation:menu:reset --user=<user-email>
```

The –menu option can be used to reset only a specific menu:

```none
php bin/console oro:navigation:menu:reset --menu=<menu-name>
```

Both options can be combined to further limit the scope being reset.

```none
php bin/console oro:navigation:menu:reset --user=<user-email> --menu=<menu-name>
```

<!-- Frontend -->
