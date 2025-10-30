<a id="layouts-layout-cache"></a>

# Layout Cache

Layout cache is based on layout context.

It uses the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/ContextInterface.php#L94" target="_blank">Context::getHash</a> method to generate the cache key.

Layout cache uses `OroCacheBundle`. For more information, see <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockViewCache.php" target="_blank">BlockViewCache</a>.

## Last Modification Date

The layout context contains the last modification date of the files with layout updates. It is registered with the `layout.context_configurator` - <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/LayoutBundle/Layout/Extension/LastModifiedDateContextConfigurator.php" target="_blank">LastModifiedDateContextConfigurator</a>.

## BlockView Tree

The layout cache contains the `root` <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockView.php" target="_blank">BlockView</a> with children and variables.

The BlockView tree is serialized with `oro_layout.block_view_serializer`.

The following is the list of normalizers used in the `oro_layout.block_view_serializer`:

* `oro_layout.block_view_serializer.block_view_normalizer` - <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/LayoutBundle/Layout/Serializer/BlockViewNormalizer.php" target="_blank">BlockViewNormalizer</a>
* `oro_layout.block_view_serializer.expression_normalizer` - <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/LayoutBundle/Layout/Serializer/ExpressionNormalizer.php" target="_blank">ExpressionNormalizer</a>
* `oro_layout.option_value_bag_normaizer` - <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Bundle/LayoutBundle/Layout/Serializer/OptionValueBagNormalizer.php" target="_blank">OptionValueBagNormalizer</a>

All normalizers are registered as a service in the DI container with the `layout.block_view_serializer.normalizer` tag.

## Expressions / Evaluate and Evaluate Deferred

There are two groups of expressions in the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockView.php" target="_blank">BlockView</a> options:

* Context key `expressions_evaluate` - expressions that do not work with `data`. It evaluates before <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockTypeInterface.php#L19" target="_blank">BlockTypeInterface::buildBlock</a>
* Context key `expressions_evaluate_deferred` - expressions that work with `data`. It evaluates after <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockTypeInterface.php#L51" target="_blank">BlockTypeInterface::finishView</a>

For example:

```yaml
actions:
    ...
    - '@add':
        id: blockId
        parentId: parentId
        blockType: typeName
        options:
            optionName: '=context["valueKey"]'
```

It will be evaluated before the <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockTypeInterface.php#L19" target="_blank">BlockTypeInterface::buildBlock</a> and the result will be cached.

```yaml
actions:
    ...
    - '@add':
        id: blockId
        parentId: parentId
        blockType: typeName
        options:
            optionName: '=data["valueKey"]'
```

It will be evaluated after <a href="https://github.com/oroinc/platform/tree/6.1/src/Oro/Component/Layout/BlockTypeInterface.php#L51" target="_blank">BlockTypeInterface::finishView</a> and the result will not be cached.

<!-- Frontend -->
