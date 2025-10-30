<a id="bundle-docs-commerce-commerce-menu-bundle-menu-updates"></a>

# Menu Updates

OroCommerceMenuBundle reuses and extends the [Menu Updates](../../platform/NavigationBundle/menu-updates.md#bundle-docs-platform-navigation-bundle-menu-updates) mechanism to provide new features:

1. Menu Updates for customer scope backed by `oro_commerce_menu.scope_criteria_provider.customer` service.
2. Menu Update for customer group scope backed by `oro_commerce_menu.scope_criteria_provider.customer_group` service.

While using the same code from <a href="https://github.com/oroinc/platform/tree/5.1/src/Oro/Bundle/NavigationBundle" target="_blank">OroNavigationBundle</a>, OroCommerceMenuBundle declares its own stack of classes and services to work with menu updates:

1. Entity class `Oro\Bundle\CommerceMenuBundle\Entity\MenuUpdate` to store the changes made to menu items.
2. Menu builder `Oro\Bundle\NavigationBundle\Menu\MenuUpdateBuilder`: `oro_commerce_menu.menu.menu_update_builder` that applies menu updates for the current scope.
3. Menu updates provider `\Oro\Bundle\NavigationBundle\Provider\MenuUpdateProvider`: `oro_commerce_menu.provider.menu_update_provider` that provides menu updates for the current scope.
4. Menu update applier `\Oro\Bundle\NavigationBundle\MenuUpdate\Applier\MenuUpdateApplier`: `oro_commerce_menu.menu_update.applier` that applies each menu update.
5. Menu-update-to-menu-item propagator `Oro\Bundle\NavigationBundle\MenuUpdate\Propagator\ToMenuItem\CompositePropagator`: `oro_commerce_menu.menu_update.propagator.to_menu_item` that propagates the data stored in a MenuUpdate into the corresponding menu item.

<!-- Frontend -->
