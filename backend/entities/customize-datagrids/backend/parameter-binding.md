<a id="datagrids-customize-parameter-binding"></a>

# Parameter Binding

Parameter binding is used to fill datasource with parameters from datagrid. For example,
[ORM datasource](datasources/orm.md#customize-datagrids-datasource-orm) is working on top of Doctrine ORM and using QueryBuilder to build query to database. Using parameter binding option in orm datasource you can configure mapping between parameters of datagrid and parameters of query.

## Configuration Syntax

```yaml
datagrids:
    acme-demo-datagrid:
        source:
            type: orm
            query:
                select:
                    - u
                from:
                    { table: ACME\Bundle\DemoBundle\Entity\User, alias:u }
                where:
                    and:
                        - u.group = :group_id
            bind_parameters:
                # Get parameter "group_id" from datagrid
                # and set it's value to "group_id" parameter in datasource query
                - group_id
```

If the name of parameters in the grid and the query do not match, you can pass an associative array of parameters, where the key is the name of the parameter in the query, and the value is the name of the parameter of the grid:

```yaml
datagrids:
    acme-demo-grid:
        source:
            type: orm
            query:
                select:
                    - u
                from:
                    { table: ACME\Bundle\DemoBundle\Entity\User, alias:u }
                where:
                    and:
                        - u.group = :group_id
            bind_parameters:
                # Get parameter "groupId" from datagrid
                # and set it's value to "group_id" parameter in datasource query
                group_id: groupId
```

To pass parameter `groupId` to the grid, use the following format when rendering the grid in the template:

```twig
{{ dataGrid.renderGrid('acme-demo-datagrid', {'groupId': entityId}) }}
```

Or pass them directly to <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/DataGridBundle/Datagrid/Manager.php" target="_blank">DatagridManager</a>.

```php
$datagridManager->getDatagrid('acme-demo-datagrid', ['groupId' => $entityId]);
```

The full format for declaring parameters binding is also available:

```yaml
bind_parameters:
    data_in: # option string key will be interpreted as name of parameter in query
        path: _parameters.groupId # it will reference to parameter groupId in key _parameters of parameter bag.
        default: [0] # some default value, will be used if parameter is not passed
        type: array # type applicable with Doctrine: Doctrine\DBAL\Types\Type::getType()
```

```yaml
bind_parameters:
    -
        name: # name of parameter in query
        path: _parameters.groupId # it will reference to parameter groupId in key _parameters of parameter bag.
        default: [0] # some default value, will be used if parameter is not passed
        type: array # type applicable with Doctrine: Doctrine\DBAL\Types\Type::getType()
```

## Support of Parameter Binding by Datasource

Datasource must implement <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/DataGridBundle/Datasource/ParameterBinderAwareInterface.php" target="_blank">ParameterBinderAwareInterface</a> to support the `bind_parameters` option.

## Parameter Binder Class

Parameter binder class must implements <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/DataGridBundle/Datasource/ParameterBinderInterface.php" target="_blank">ParameterBinderInterface</a> and depends on datasources implementation.

Example of usage:

```php
// get parameter "name" from datagrid parameter bag and add it to datasource
$queryParameterBinder->bindParameters($datagrid, ['name']);

// get parameter "id" from datagrid parameter bag and add it to datasource as parameter "client_id"
$queryParameterBinder->bindParameters($datagrid, ['client_id' => 'id']);

// get parameter "email" from datagrid parameter bag and add it to datasource, all other existing
// parameters will be cleared
$queryParameterBinder->bindParameters($datagrid, ['email'], false);
```

## Parameter Binding Listener

<a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/DataGridBundle/EventListener/DatasourceBindParametersListener.php" target="_blank">DatasourceBindParametersListener</a> is responsible for running the binding of the datasource parameters. It checks whether the datasource implements <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Bundle/DataGridBundle/Datasource/ParameterBinderInterface.php" target="_blank">ParameterBinderInterface</a> and whether it has the `bind_parameters` option.

If the grid configuration is applicable, then parameters configuration specified in the `bind_parameters` is passed to the datasource method `bindParameters`.

<!-- Frontend -->
