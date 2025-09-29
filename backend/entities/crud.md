<a id="dev-cookbook-framework-create-simple-crud"></a>

# CRUD Operations

To let the users create new tasks and edit existing ones, follow these steps:

1. [Create a form type for the Task entity](#cookbook-entity-form-type).
2. [Create a controller](#cookbook-entity-controller).
3. [Render the form in a template](#cookbook-entity-template).
4. [Link data grid entries to the controller](#controller-entity-grid-create-edit-link).

<a id="cookbook-entity-form-type"></a>

## The Form Type

First, you need to create a form type that makes it possible to let the user enter all the data
needed to describe a task:

*src/AppBundle/Form/TaskType.php*
```php
 namespace AppBundle\Form;

 use Symfony\Component\Form\AbstractType;
 use Symfony\Component\Form\FormBuilderInterface;
 use Symfony\Component\OptionsResolver\OptionsResolver;

 class TaskType extends AbstractType
 {
     public function buildForm(FormBuilderInterface $builder)
     {
         $builder
             ->add('subject')
             ->add('description')
             ->add('dueDate')
             ->add('priority')
         ;
     }

     public function configureOptions(OptionsResolver $resolver)
     {
         $resolver->setDefaults([
             'data_class' => 'AppBundle\Entity\Task',
         ]);
     }
 }
```

#### SEE ALSO
Learn more about <a href="https://symfony.com/doc/5.4/book/forms.html" target="_blank">form types in the Symfony documentation</a>.

<a id="cookbook-entity-controller"></a>

## The Controllers

You then need to create a controller class that comes with two actions: one that is called when a new task should be created and one that can fetch an existing task to let the user modify its data:

*src/AppBundle/Controller/TaskController.php*
```php
 namespace AppBundle\Controller;

 use AppBundle\Entity\Task;
 use Sensio\Bundle\FrameworkExtraBundle\Configuration\Template;
 use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
 use Symfony\Component\Routing\Annotation\Route;
 use Symfony\Component\HttpFoundation\Request;

 /**
  * @Route("/task")
  */
 class TaskController extends AbstractController
 {
     /**
      * @Route("/create", name="app_task_create")
      * @Template("@App/Task/update.html.twig")
      */
     public function createAction(Request $request)
     {
         return $this->update(new Task(), $request);
     }

     /**
      * @Route("/edit/{id}", name="app_task_update", requirements={"id"="\d+"})
      * @Template("@App/Task/update.html.twig")
      */
     public function editAction(Task $task, Request $request)
     {
         return $this->update($task, $request);
     }

     private function update(Task $task, Request $request)
     {
         $form = $this->createForm(new TaskType(), $task);

         return [
             'entity' => $task,
             'form' => $form->createView(),
         ];
     }
 }
```

Then, make sure that the controller is loaded in your routing configuration so that Symfony knows
which controller needs to be called for particular routes:

*src/AppBundle/Resources/config/routing.yml*
```yaml
 app_task:
     resource: '@AppBundle/Controller/TaskController.php'
     type: annotation
```

<a id="cookbook-entity-template"></a>

## The Template

The template that is responsible for displaying the form fields should extend the base template `@OroUI/actions/update.html.twig` from the OroUIBundle. This template defines some basic blocks that you can use. This way, your own forms will provide the same look and feel as the ones coming with OroPlatform:

*src/AppBundle/Resources/views/Task/update.html.twig*
```none
 {# extend the base template from the OroUIBundle #}
 {% extends '@OroUI/actions/update.html.twig' %}

 {# reuse the form theme provided with OroPlatform #}
 {% form_theme form with '@OroForm/Form/fields.html.twig' %}

 {# make the current task accessible with the task variable #}
 {% set task = form.vars.value %}

 {# choose the appropriate action depending on whether a task is created or modified #}
 {# this variable needs to be named formAction as this is what the base template expects #}
 {% if task.id %}
     {% set formAction = path('app_task_update', { 'id': task.id }) %}
 {% else %}
     {% set formAction = path('app_task_create') %}
 {% endif %}

 {% block navButtons %}
     {# the cancelButton() macro creates a button that discards the
        entered data and leads the user to the linked controller #}
     {{ UI.cancelButton(path('app_task_index')) }}

     {# the dropdownSaveButton() macro offers a way to let the user select
        between different options when saving an entity, the selected option
        will be passed to the controller handling the request as an additonal
        parameter #}
     {{ UI.dropdownSaveButton({
         'html': UI.saveAndCloseButton() ~ UI.saveAndStayButton()
     }) }}
 {% endblock navButtons %}

 {% block pageHeader %}
     {% if task.id %}
         {% set breadcrumbs = {
             'entity': task,
             'indexPath': path('app_task_index'),
             'indexLabel': 'Tasks',
             'entityTitle': task.subject
         } %}
         {{ parent() }}
     {% else %}
         {% set title = 'oro.ui.create_entity'|trans({ '%entityName%': 'Task' }) %}
         {{ include('@OroUI/page_title_block.html.twig', { title: title }) %}
     {% endif %}
 {% endblock pageHeader %}

 {% block content_data %}
     {% set id = 'task-edit' %}
     {% set dataBlocks = [{
             'title': 'General'|trans,
             'class': 'active',
             'subblocks': [{
                 'title': '',
                 'data': [
                     form_row(form.subject),
                     form_row(form.description),
                     form_row(form.dueDate),
                     form_row(form.priority),
                 ]
             }]
         }]
     %}

     {# the data variable is a special variable that is used in the
        parent content_data block to render the visual content "blocks"
        of a page #}
     {% set data = {
         'formErrors': form_errors(form) ? form_errors(form) : null,
         'dataBlocks': dataBlocks,
     } %}

     {{ parent() }}
 {% endblock content_data %}
```

<a id="controller-entity-grid-create-edit-link"></a>

## Linking the Data Grid

Finally, link both actions on the page that displays the list of tasks:

**1. Add a link to create new tasks**

The base `@OroUI/actions/index.html.twig` template from the OroUIBundle that you [already used](data-grids/index.md#cookbook-entities-grid-controller) to embed the data grid comes with a pre-defined `navButtons` block, which you can use to add a button that links to the *create a task action*:

*src/AppBundle/Resources/views/Task/index.html.twig*
```html+jinja
 {% extends '@OroUI/actions/index.html.twig' %}

 {% set gridName = 'app-tasks-grid' %}
 {% set pageTitle = 'Task' %}

 {% block navButtons %}
     <div class="btn-group">
         {{ UI.addButton({
             'path': path('app_task_create'),
             'entity_label': 'Create a task',
         }) }}
     </div>
 {% endblock %}
```

**2. Link task rows to the related update action**

To make it possible to modify each task, you need to define a property that describes how the URL of the update action is built, and then add this URL to the list of available actions in your data grid configuration:

*src/AppBundle/Resources/config/oro/datagrids.yml*
```yaml
 datagrids:
     app-tasks-grid:
         # ...
         properties:
             id: ~
             update_link:
                 type: url
                 route: app_task_update
                 params:
                     - id
             # ...
         actions:
             # ...
             edit:
                 type: navigate
                 label: Edit
                 link: update_link
                 icon: edit
```

<a id="book-crud-delete"></a>

## Deleting Entities

You can delete a task through the `DELETE` operation available for all entities by default or through the customized one. When running `DELETE`, ensure that your entity has a route from the `routeName` option of the entity configuration.

You can delete an entity through the [DELETE operation](../entities-data-management/actions/index.md#bundle-docs-platform-action-bundle-default-operations) which is enabled by default for all entities. To run the operation, you need to ensure that your entity has the `routeName` option of the entity configuration, which will be used as a route name to redirect a user after the `DELETE` operation (as in the example below).

```php
@Config(
     routeName="oro_task_index",
     routeView="oro_task_view",
     defaultValues={
         "entity"={
             "icon"="fa-tasks"
         },
```

See the sample configuration of the default `DELETE` operation in the <a href="https://github.com/oroinc/platform/blob/5.0/src/Oro/Bundle/ActionBundle/Resources/config/oro/actions.yml" target="_blank">Actions</a> topic.

If the default configuration is not valid for your particular case, create your own operation that would inherit from the default one, following the example:

```php
DELETE:
    exclude_entities:
        - Oro\Bundle\CatalogBundle\Entity\Category

oro_catalog_category_delete:
    extends: DELETE
    replace:
        - exclude_entities
        - entities
        - for_all_datagrids
        - for_all_entities
    for_all_datagrids: false
    for_all_entities: false
    entities:
        - Oro\Bundle\CatalogBundle\Entity\Category
    preconditions:
        '@and':
            - '@not_equal': [$.data.parentCategory, null]
```

#### NOTE
When creating your own operation, make sure to exclude the entity from the default operation. See more details on [available operations and their configuration](../entities-data-management/actions/index.md#bundle-docs-platform-action-bundle-operations) in the related article.

<!-- Frontend -->
