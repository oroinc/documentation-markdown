<a id="backend-security-bundle-role-access-control"></a>

# Access Control

Symfony has a built-in security capability to easily filter URL patterns by user roles, defining an access_control list in the security configuration context. See <a href="https://symfony.com/doc/6.3/security/access_control.html" target="_blank">Role Based Access Control In Symfony</a> for details.

The order of this list really matters, as Symfony will return the first entry for which the current request URL, method, ip, etc., matches.

As this list can be extended by bundles, it’s important to be aware of the final order the list is going to have.

Because of this, in Oro, you cannot put the access_control rules in the `security` configuration extension, but you must put them in the `oro_security` context (in the same format).

Example:

```yaml
# config/config.yaml
oro_security:
    access_control:
        - { path: ^%web_backend_prefix%/contact$, roles: ANY_ROLE }
```

By default, the final rule list is sorted in the following order:

1. Application level configuration (config.yml, security.yml, etc.)

```yaml
# config/config.yaml
oro_security:
    access_control:
        - { path: ^%web_backend_prefix%/contact$, roles: security_yml_ROLE }
```

1. The list merged from vendor bundles in the bundle loading order

```yaml
# AclBundle/Resources/config/app.yml (5th. loaded bundle in kernel)
oro_security:
    access_control:
        - { path: ^%web_backend_prefix%/contact$, roles: acl_bundle_ROLE }

# OroActivityContactBundle/Resources/config/app.yml (61st. loaded bundle in kernel)
oro_security:
    access_control:
        - { path: ^%web_backend_prefix%/contact$, roles: activity_contact_bundle_ROLE }
```

1. The list merged from the src folder

```yaml
# src/Resources/config/app.yml
oro_security:
    access_control:
        - { path: ^%web_backend_prefix%/contact$, roles: src_folder_ROLE, priority: 20 }
```

If you want to override a rule and move to the top of the rule list which is going to be checked, you can use the `priority` flag.

By default, if there is no value set for a rule, it will default to 0, so if you want to move a rule up in order, put a value higher than that.

In the example above, the final list will look like the following.

```yaml
- { path: ^%web_backend_prefix%/contact$, roles: src_folder_ROLE }
- { path: ^%web_backend_prefix%/contact$, roles: security_yml_ROLE }
- { path: ^%web_backend_prefix%/contact$, roles: acl_bundle_ROLE }
- { path: ^%web_backend_prefix%/contact$, roles: activity_contact_bundle_ROLE }
```

The request coming for URL `^%web_backend_prefix%/contact` will be checked for role `src_folder_ROLE` because it was moved up for its priority of 20.

<!-- Frontend -->
