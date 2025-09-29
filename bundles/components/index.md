<!-- meta: description = OroPlatform Components Documentation -->

<a id="component-docs"></a>

# Components Documentation

Oro Config Component provides additional resource types to the Symfony Config Component infrastructure responsible for loading configurations from different data sources and optionally monitoring these data sources for changes.

* Resource Types provides a way to configure a bundle from other bundles.
* Resource Merge provides a way to merge configurations of some resource both from one or many bundles. Supports two strategies: replace and append.
* System Aware Resolver allows to make your configuration files more dynamic. For example, you can call service’s methods, static methods, constants, context variables etc.

* [Configuration Merger](configuration-merger.md)
* [Cumulative Resources](cumulative-resources.md)
* [System Aware Resolver](system-aware-resolver.md)
