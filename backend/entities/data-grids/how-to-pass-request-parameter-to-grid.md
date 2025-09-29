<a id="index-0"></a>

<a id="how-to-pass-request-parameter-to-the-grid"></a>

# Pass Request Parameters to the Grid

Sometimes, you must pass parameters from the request to the grid.
For this, use grid event listeners or an existing listener implementation.

## Grid Configuration

Suppose you have a grid configuration and a named parameter inside the where clause of its source query:

*src/Acme/Bundle/TaskBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     # ...
     acme-tasks-grid:
         # ...
         source:
             query:
                 where:
                     and:
                     - task.relatedContact = :contactId
         # ...
     # ...
```

The goal is to set the :contactId parameter with the value from the request.

## Solution 1: Grid Parameter Binding

The easiest way (sufficient for most situations) is to use the parameter binding option of the datasource to configure the mapping between the datagrid and query parameters.

You can do this by adding the `bind_parameters` option to your `datagrids.yml` using the following syntax:

*src/Acme/Bundle/TaskBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     # ...
     acme-tasks-grid:
         # ...
         source:
             query:
                 where:
                     and:
                     - task.relatedContact = :contactId
             bind_parameters:
                 # Get the "contactId" parameter from the datagrid
                 # and set its value to the "contactId" parameter in the datasource query
                 - contactId
         # ...
     # ...
```

In case if names of the parameter in the grid and the query do not match, you can pass an associative array of parameters, where the key will be the name of the query parameter, and the value will match the name of the parameter in the grid:

*src/Acme/Bundle/TaskBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     # ...
     acme-tasks-grid:
         # ...
         source:
             query:
                 where:
                     and:
                     - task.relatedContact = :contactId
             bind_parameters:
                 # Get the "relatedContactId" parameter from the datagrid
                 # and set its value to the "contactId" parameter in the datasource query
                 contactId: relatedContactId
         # ...
     # ...
```

#### CAUTION
A datasource must implement the `Oro\Bundle\DataGridBundle\Datasource\ParameterBinderAwareInterface`
to support the `bind_parameters` option.

Next, pass the “relatedContactId “ parameter to the grid. The controller receives a contact entity and passes it to the view:

*src/Acme/Bundle/TaskBundle/Controller/TaskController.php*
```php
     namespace Acme\Bundle\TaskBundle\Controller;

     use Oro\Bundle\ContactBundle\Entity\Contact;
     use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;
     use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
     use Symfony\Component\Routing\Annotation\Route;

     class TaskController extends AbstractController
     {
         // ...

         /**
          * @Route("/contact/{id}/tasks", name="acme_task_contact_tasks", requirements={"id"="\d+"})
          * @Template
          */
         public function contactTasksAction(Contact $contact)
         {
             return ['contact' => $contact];
         }

         // ...
     }
```

The view passes the “relatedContactId” parameter to the grid:

*src/Acme/Bundle/TaskBundle/Resources/views/Task/contactTasks.html.twig*
```html+jinja
 {% import '@OroDataGrid/macros.html.twig' as dataGrid %}

 <div class="widget-content">
     {{ dataGrid.renderGrid('acme-tasks-grid', {relatedContactId: contact.id}) }}
 </div>
```

## Solution 2. Create Custom Event Listener

If the first example does not work for you ( for example, datasource does not support parameters binding, or  you need to implement additional logic before binding parameters), you can create a listener for the
`oro_datagrid.datagrid.build.after` event and set the parameter for the source query in this listener:

*src/Acme/Bundle/TaskBundle/EventListener/ParameterListener.php*
```php
 namespace Acme\Bundle\TaskBundle\EventListener;

 use Doctrine\ORM\QueryBuilder;

 use Oro\Bundle\DataGridBundle\Datasource\Orm\OrmDatasource;
 use Oro\Bundle\DataGridBundle\Event\BuildAfter;

 class ParameterListener
 {
     protected $parameterName;
     protected $requestParameterName;

     public function __construct($parameterName, $requestParameterName = null)
     {
         $this->parameterName = $parameterName;
         $this->requestParameterName = $requestParameterName ? $requestParameterName : $this->parameterName;
     }

     public function onBuildAfter(BuildAfter $event)
     {
         $datagrid   = $event->getDatagrid();
         $datasource = $datagrid->getDatasource();
         $parameters = $datagrid->getParameters();

         if ($datasource instanceof OrmDatasource) {
             /** @var QueryBuilder $queryBuilder */
             $queryBuilder = $datasource->getQueryBuilder();

             $queryBuilder->setParameter($this->parameterName, $parameters->get($this->requestParameterName));
         }
     }
 }
```

Register this listener in the container:

*src/Acme/Bundle/TaskBundle/Resources/config/services.yml*
```yaml
 services:
     acme_task.event_listener.acme_tasks_grid_parameter_listener:
         class: Acme\Bundle\TaskBundle\EventListener\ParameterListener
         arguments:
             - contactId
         tags:
             - { name: kernel.event_listener, event: oro_datagrid.datagrid.build.after.acme-tasks-grid, method: onBuildAfter }
```

Remember that you still need to pass the `relatedContactId` parameter to the grid from a Twig template (see the example in the previous solution).

## References

* <a href="https://symfony.com/doc/5.4/cookbook/doctrine/event_listeners_subscribers.html" target="_blank">Symfony Cookbook How to Register Event Listeners and Subscribers</a>

<!-- Frontend -->
