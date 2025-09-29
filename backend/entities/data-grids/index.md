<a id="data-grids"></a>

# Datagrids

Creating a basic datagrid to display the data of all tasks involves three steps:

1. [Configure the datagrid](#cookbook-entities-grid-config)
2. [Create a controller and template](#cookbook-entities-grid-controller)
3. [Add a link to the grid to the application menu](#cookbook-entities-grid-navigation)

<a id="cookbook-entities-grid-config"></a>

## Configure the Grid

The datagrid configuration happens in the `datagrids.yml` file in the configuration directory of your bundle and is divided into sections below.

### Datasource

The `source` option is used to configure a Doctrine query builder that is used to fetch the data to be displayed in the grid:

*src/AppBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     app-tasks-grid:
         source:
             type: orm
             query:
                 select:
                     - task.id
                     - task.subject
                     - task.description
                     - task.dueDate
                     - priority.label AS taskPriority
                 from:
                     - { table: Acme\Bundle\AppBundle\Entity\Task, alias: task }
                 join:
                     left:
                         - { join: task.priority, alias: priority }
```

### Displayed Columns

Then, the `columns` option needs to be used to configure how which data will be displayed:

*src/AppBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     app-tasks-grid:
         # ...
         columns:
             id:
                 label: ID
                 frontend_type: integer
             subject:
                 label: Subject
             description:
                 label: Description
             dueDate:
                 label: Due Date
                 frontend_type: datetime
             taskPriority:
                 label: Priority
```

For each column, you can use the `frontend_type` option to customize how data will be displayed (by default, the data will be shown as is).

### Column Sorters

Use the `sorters` option to define on which columns’ header the user can click to order by the data:

*src/AppBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     app-tasks-grid:
         # ...
         sorters:
             columns:
                 id:
                     data_name: task.id
                 subject:
                     data_name: task.subject
                 description:
                     data_name: task.description
                 dueDate:
                     data_name: task.dueDate
                 taskPriority:
                     data_name: priority.label
             default:
                 dueDate: DESC
```

Each key under `sorters.columns` refers to one displayed column. The `data_name` option is the term that will be used as the `order by` term in the Doctrine query.

### Data Filters

Data filters are UI elements that allow the user to filter the data being displayed in the data grid. List all the attributes for which a filter should be shown under the `filters.columns` key. To configure the filter for a certain property, two options are needed:

* The `type` configures the UI type of the filter. The type of filter should be chosen based on the data type of the underlying attribute.
* The `data_name` denotes the name of the property to filter and will be used as is to modify the datagrid’s query builder.

*src/AppBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     app-tasks-grid:
         # ...
         filters:
             columns:
                 id:
                     type: number
                     data_name: task.id
                 subject:
                     type: string
                     data_name: task.subject
                 description:
                     type: string
                     data_name: task.description
                 dueDate:
                     type: datetime
                     data_name: task.dueDate
                 taskPriority:
                     type: string
                     data_name: priority.label
```

### Complete Datagrid Configuration

The final datagrid configuration now looks like this:

*src/AppBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     app-tasks-grid:
         source:
             type: orm
             query:
                 select:
                     - task.id
                     - task.subject
                     - task.description
                     - task.dueDate
                     - priority.label AS taskPriority
                 from:
                     - { table: Acme\Bundle\AppBundle\Entity\Task, alias: task }
                 join:
                     left:
                         - { join: task.priority, alias: priority }
         columns:
             id:
                 label: ID
                 frontend_type: integer
             subject:
                 label: Subject
             description:
                 label: Description
             dueDate:
                 label: Due Date
                 frontend_type: datetime
             taskPriority:
                 label: Priority
         sorters:
             columns:
                 id:
                     data_name: task.id
                 subject:
                     data_name: task.subject
                 description:
                     data_name: task.description
                 dueDate:
                     data_name: task.dueDate
                 taskPriority:
                     data_name: priority.label
             default:
                 dueDate: DESC
         filters:
             columns:
                 id:
                     type: number
                     data_name: task.id
                 subject:
                     type: string
                     data_name: task.subject
                 description:
                     type: string
                     data_name: task.description
                 dueDate:
                     type: datetime
                     data_name: task.dueDate
                 taskPriority:
                     type: string
                     data_name: priority.label
```

<a id="cookbook-entities-grid-controller"></a>

## Create the Controller and View

To make your datagrid accessible, create a controller that the user can visit, which will serve as a view that renders the configured datagrid:

*src/AppBundle/Controller/TaskController.php*
```php
 namespace AppBundle\Controller;

 use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;
 use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
 use Symfony\Component\Routing\Annotation\Route;

 /**
  * @Route("/task")
  */
 class TaskController extends AbstractController
 {
     /**
      * @Route("/", name="app_task_index")
      * @Template()
      */
     public function indexAction()
     {
         return [];
     }
 }
```

The view can be straightforward if you extend the `@OroUI/actions/index.html.twig` template:

*src/AppBundle/Resources/views/Task/index.html.twig*
```html+jinja
 {% extends '@OroUI/actions/index.html.twig' %}

 {% set gridName = 'app-tasks-grid' %}
 {% set pageTitle = 'Task' %}
```

Configure the name of your datagrid and the title you wish to be displayed. The base template from the OroUIBundle handles everything else.

<a id="cookbook-entities-grid-navigation"></a>

## Link to the Action

At last, you need to make the action accessible by creating a menu item:

*src/AppBundle/Resources/config/oro/navigation.yml*
```yaml
 menu_config:
     items:
         task_list:
             label: Tasks
             route: app_task_index
     tree:
         application_menu:
             children:
                 task_list: ~
```

#### NOTE
`application_menu` is the name of the menu you want to hook your item into. In this case, `application_menu` is an existing menu that is part of OroPlatform.

## Key Classes

- `Datagrid\Manager` - responsible for preparing the grid and its configuration.
- `Datagrid\Builder` - responsible for creating and configuring the datagrid object and its datasource. It contains registered datasource types and extensions, and it also performs a check for datasource availability according to ACL.
- `Datagrid\Datagrid` - the main grid object, has only knowledge about the datasource object and its interaction; all further modifications of the results and metadata come from the extensions. Extension\\Acceptor - is a visitable mediator, contains all applied extensions, and provokes visits at different points of the interactions.
- `Extension\ExtensionVisitorInterface` - visitor interface.
- `Extension\AbstractExtension` - basic empty implementation.
- `Datasource\DatasourceInterface` - link object between data and grid. Should provide results as an array of ResultRecordInterface compatible objects.
- `Provider\SystemAwareResolver` - resolves specific grid YAML syntax expressions. For more information, see the [references in configuration](../customize-datagrids/backend/references-in-configuration.md#datagrid-references-configuration) topic.

<a id="datagrids-customize-mixin"></a>

## Mixin

Mixin is a datagrid that contains additional (common) information for use by other datagrids.

**Configuration Syntax**

```yaml
datagrids:

    # configuration mixin with column, sorter and filter for an entity identifier
    acme-demo-common-identifier-datagrid-mixin:
        source:
            type: orm
            query:
                select:
                    # alias that will be replaced by an alias of the root entity
                    - __root_entity__.id as identifier
        columns:
            identifier:
                frontend_type: integer
        sorters:
            data_name: identifier
        filters:
            columns:
                identifier:
                    type: number
                    data_name: identifier

    acme-demo-user-datagrid:
        # one or several mixins
        mixins:
            - acme-demo-datagrid-mixin
            - ...
            - ...
        source:
            type: orm
            query:
                from:
                    { table: ACME\Bundle\DemoBundle\Entity\User, alias:u }
```

**Related Articles**

* [Customizing Datagrid](../customize-datagrids/index.md#customizing-data-grid-in-orocommerce)
* [Datagrid Configuration Reference](../../configuration/yaml/datagrids.md#reference-format-datagrids)
