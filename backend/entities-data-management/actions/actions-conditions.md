<a id="bundle-docs-platform-action-bundle-action-component"></a>

# Actions and Conditions in Operations

ActionBundle provides several actions and conditions, besides those that are in the Action Component.

## Actions

Run Action Group @run_action_group.

**Class:** Oro\\Bundle\\ActionBundle\\Action\\RunActionGroup

**Alias:** run_action_group

**Description:** Runs named [action group](./action-groups.md) with passed parameters.

**Options:**

- result - (optional) property path where the action group execution context value is allocated
- results - (optional) property path where the results from action-group-context are mapped to current context keys
- action_group - action group name
- parameters_mapping - map of parameters which are passed to the action_group context from the current one

**Configuration Example**

```none
- '@run_action_group':
    result: $.result
    results:
        result_entity_id: $.demo_new_attribute
    action_group: acme_demo_action_group
    parameters_mapping:
        entity_class: Acme\Bundle\DemoBundle\Entity\User
        entity_id: $.user.id
```

This configuration executes configured **action group** with the acme_demo_action_group name and parameters displayed under the parameters_mapping section.
After the execution of **action group**, processed ActionData (e.g. context) are returned and assigned to the $.result attribute of the caller context.
And $.result_entity_id acquires the value of $.demo_new_attribute from the Action Group’s context.

Please note that all parameters must pass validation and be accessible under root node of ActionData in the action_group execution body.
E.g., $.entity_class and $.entity_id respectively to their names. See the [Action Groups](action-groups.md#bundle-docs-platform-action-bundle-action-groups) documentation for more details.

### Format Name

**Class:** Oro\\Bundle\\ActionBundle\\ActionFormatName

**Alias:** format_name

**Description:** Format entity name based on locale settings.

**Parameters:**

- attribute - target path where the action results are saved;
- object - entity;

**Configuration Example**

```none
- '@format_name':
    attribute: $.result.formattedCustomerName
    object: $cart.customer
```

### Create Date

**Class:** Oro\\Bundle\\ActionBundle\\Action\\CreateDate

**Alias:** create_date

**Description:** Create DateTime object based on date string

**Parameters:**

- date - (optional) date as a string. The current date by default;
- attribute - target path where the action results are saved.

**Configuration Example**

```none
- '@create_date':
    attribute: $sales_funnel_start_date
```

OR

```none
- '@create_date':
    conditions:
            # optional condition configuration
    parameters:
        attribute: $sales_funnel_start_date
        date: '2014-04-01' # must use quotes because date parameter requires string value
```

### Copy Values

**Class:** Oro\\Component\\Action\\Action\\CopyValues

**Alias:** copy_values

**Description:**  Copies the values from a context or an object to the provided attribute and behaves the same as the array_merge PHP function.

```none
- '@copy_values': [$.to, $.from1, $.from2, {key: 'value'}]
```

### Resolve Destination Page

**Class:** Oro\\Bundle\\ActionBundle\\Action\\ResolveDestinationPage

**Alias:** resolve_destination_page

**Description:** Resolves the URL redirection activity by a route name from the entity configuration using the routeName or routeView parameters.

**Options:**

- destination / 0 - the route name specified in the @Config annotation of an entity
- entity / 1 - (optional) property path of the original entity (by default, equals to entity)
- attribute / 2 - (optional) target property path where the action results are saved (by default, equals to redirectUrl)

**Configuration Example**

```none
 - '@resolve_destination_page': view

OR



- '@resolve_destination_page': ['view', $.entity, $.attribute]

OR



 - '@resolve_destination_page':
     name: index
     entity: $.data.entity

OR



 - '@resolve_destination_page':
     name: index
     entity: $.entity
     attribute: $.attribute
```

Allowed values for the destination parameter:

- for the index page (routeName) value can be name
- for the view page (routeView) value can be view

### Duplicate

**Class:** Oro\\Bundle\\ActionBundle\\Action\\DuplicateEntity

**Alias:** duplicate, duplicate_entity

**Description:** Duplicate entity object

**Options:**

- entity - (optional) a property path of the original entity (by default, the getEntity() method is used from context)
- target - (optional) a property path of the original entity, alias for entity
- settings - (optional) a list of filters and matchers to be applied to
- attribute - a target property path where the action results are saved

**Filters and Matchers:**

Available filters: setNull, keep, collection, emptyCollection, replaceValue, and shallowCopy.
Available matchers: property, propertyName, and propertyType.

For more information, please refer to the <a href="https://packagist.org/packages/myclabs/deep-copy" target="_blank">DeepCopy</a> documentation.

**Configuration Example**

```none
- '@duplicate':
    target: $.entity
    attribute: $.entityCopy
    settings:
      - [[setNull], [propertyName, [id]]]
      - [[collection], [propertyName, [items]]]
      - [[replaceValue, $.currentUser], [propertyName, [user]]]
      - [[keep], [propertyName, [owner]]]
      - [[shallowCopy], [propertyType, ['\DateTime']]]
      - [[keep], [propertyType, ['%oro_user.entity.user%']]]
```

<a id="bundle-docs-platform-action-bundle-conditions"></a>

## Conditions

### Add Custom Condition

The conditions are based on the <a href="https://github.com/oroinc/platform/tree/4.2/src/Oro/Component/ConfigExpression/README.md" target="_blank">ConfigExpression</a> component.

To add custom condition, simply add a service to DIC with the “oro_action.condition” tag, for example:

```none
services:
    Oro\Bundle\ActionBundle\ConfigExpression\Blank:
        tags:
            - { name: oro_action.condition, alias: blank|empty }
```

The “|” symbol in alias can be used to demonstrate several aliases. Note that service class must implement OroComponentConfigExpressionExpressionInterface.

### Configurable Condition

**Alias:** - the option is configurable.

**Description:** - uses Condition Assembler to assemble conditions from passed configuration.
This condition is NOT intended to be used in configuration of Action.
But it can be used to create a condition based on configuration in runtime.

**Options:** - valid configuration of conditions.

**Code Example**

Code Example is a value of the “call_timeout” attribute. It is not blank, and it equals to 20.

```php
$configuration = [
    '@and' => [
        '@not_blank' => ['$call_timeout'],
        '@equal' => ['$call_timeout', 20]
    ]
];
/** @var \Oro\Bundle\ActionBundle\Model\Condition\ConditionFactory $conditionFactory */
$condition = $conditionFactory->create(Configurable::ALIAS, $configuration);

/** @var object $data */
$data->call_timeout = 20;

var_dump($condition->evaluate($data)); // will output TRUE
```

<!-- Frontend -->
