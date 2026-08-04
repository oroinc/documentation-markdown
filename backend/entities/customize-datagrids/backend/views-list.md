<a id="customize-datagrids-views-list"></a>

# Datagrid Views List

Adds a list of grid views, and applies the grid view’s filters and sorters to the parameters’ filters.

To write your own view list, create a class that extends the `Oro\Bundle\DataGridBundle\Extension\GridViews\AbstractViewsList`
class. Here is an example:

*src/Acme/Bundle/DemoBundle/Datagrid/FavoriteViewList.php*
```php
<?php

namespace Acme\Bundle\DemoBundle\Datagrid;

use Oro\Bundle\DataGridBundle\Entity\GridView;
use Oro\Bundle\DataGridBundle\Extension\GridViews\AbstractViewsList;
use Oro\Bundle\FilterBundle\Form\Type\Filter\TextFilterType;

/**
 * Grid views for acme-demo-favorite-grid datagrid.
 */
class FavoriteViewList extends AbstractViewsList
{
    protected $systemViews =  [
        [
            'name'         => 'acme_demo.first_view',
            'label'         => 'acme.demo.favorite.datagrid.views.first_example_view_label',
            'is_default'    => false,
            'grid_name'     => 'acme-demo-favorite-grid',
            'type'          => GridView::TYPE_PUBLIC,
            'filters'       => [
                'name' => [
                    'type'  => TextFilterType::TYPE_EQUAL,
                    'value' => 'First favorite'
                ]
            ],
            'sorters'       => [
                'name' => 'DESC'
            ],
            'columns'       => []
        ], [
            'name'         => 'acme_demo.sample_view',
            'label'         => 'acme.demo.favorite.datagrid.views.second_example_view_label',
            'is_default'    => false,
            'grid_name'     => 'acme-demo-favorite-grid',
            'type'          => GridView::TYPE_PUBLIC,
            'filters'       => [
                'name' => [
                    'type'  => TextFilterType::TYPE_STARTS_WITH,
                    'value' => 'Last'
                ]
            ],
            'sorters'       => [],
            'columns'       => [
                'name'                 => ['renderable' => true, 'order' => 1],
                'viewCount'            => ['renderable' => true, 'order' => 2],
                'value'                => ['renderable' => true, 'order' => 3],
            ]
        ]
    ];

    #[\Override]
    protected function getViewsList()
    {
        return $this->getSystemViewsList();
    }
}
```

Add the service definition to `services.yml`:

*src/Acme/Bundle/DemoBundle/Resources/config/services.yml*
```yaml
services:
    acme_demo.favorite_view_list:
        class: Acme\Bundle\DemoBundle\Datagrid\FavoriteViewList
        public: true
        arguments:
            - '@translator'
```

Add the view list to a datagrid in the datagrids.yml file, under the view-list node.

*src/Acme/Bundle/DemoBundle/Resources/config/oro/datagrids.yml*
```yaml
datagrids:
    acme-demo-favorite-grid:
        views_list: '@acme_demo.favorite_view_list'
```

**Related Articles**

* [Datagrids](../../data-grids/index.md#data-grids)
* [Datagrid Configuration Reference](../../../configuration/yaml/datagrids.md#reference-format-datagrids)
