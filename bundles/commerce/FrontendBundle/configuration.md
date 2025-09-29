# Frontend Sessions and Debug Routes

## Frontend Session

This bundle provides a possibility to configure different session cookie parameters (such as name, path and lifetime) for the storefront and back-office. Use `session` section for this:

```yaml
oro_frontend:
    session:
        name: OROSFID
        cookie_lifetime: 900
```

The full list of storefront session options is:

* name
* cookie_lifetime
* cookie_path
* gc_maxlifetime
* gc_probability
* gc_divisor

See <a href="https://symfony.com/doc/current/reference/configuration/framework.html#session" target="_blank">Symfony Framework Configuration Reference</a> for detailed information about each option.

## Debug Routes

Debug routes allows to turn off on fly routes generation, it can slightly boost performance on slow hardware configurations and also makes app more stable on Windows. If `kernel.debug` is set to false value of debug routes is ignored. To turn off routes generation set option `debug_routes` to `false` in config.yml file:

```yaml
oro_frontend:
    debug_routes: false
```

If you turned off routes generation, you must do it manually by executing following command:

```php
php bin/console fos:js-routing:dump
```

<!-- Frontend -->
