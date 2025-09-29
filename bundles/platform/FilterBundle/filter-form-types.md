<a id="backend-filters-form-types"></a>

# Filter Form Types

Filter Form Types are PHP classes that represent filters and extend standard Symfony form types.
Each filter form type is a compound and consists of two fields:

* a field for filter value (named “value”)
* a field for filter operator (named “type”)

The following filters form types are available:

| Class                      | Name                               | Short Description                                                      |
|----------------------------|------------------------------------|------------------------------------------------------------------------|
| FilterType                 | oro_type_filter                    | Basic type for all filters, declares two children, value and type      |
| TextFilterType             | oro_type_text_filter               | Represents text filter form                                            |
| NumberFilterType           | oro_type_number_filter             | Represents number filter form                                          |
| NumberRangeFilterType      | oro_type_number_range_filter       | Represents number range filter form                                    |
| ChoiceFilterType           | oro_type_choice_filter             | Represents choice filter form                                          |
| EntityFilterType           | oro_type_entity_filter             | Represents entity filter form                                          |
| BooleanFilterType          | oro_type_boolean_filter            | Represents boolean filter form                                         |
| DateRangeFilterType        | oro_type_date_range_filter         | Represents date filter form                                            |
| DateTimeRangeFilterType    | oro_type_datetime_range_filter     | Represents date and time filter form                                   |
| DateRangeType              | oro_type_date_range                | This form type is used by oro_type_date_range_filter as field type     |
| DateTimeRangeType          | oro_type_datetime_range            | This form type is used by oro_type_datetime_range_filter as field type |
| DateGroupingFilterType     | oro_type_date_grouping_filter      | Represents date grouping filter                                        |
| SkipEmptyPeriodsFilterType | oro_type_skip_empty_periods_filter | Represents skip empty periods filter                                   |

## oro_type_filter Form Type

**Children**

* value
* type

**Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = TextType::class
* operator_type = ChoiceType::class
* show_filter = False

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\FilterType`

**Options Description**

* **field_type** - This option declares the type of the value child element.
* **field_options** - Value of this option will be used as the options array for the value field.
* **operator_choices** - Value of this option will be used as the value of the “choices” option of the type field.
* **operator_type** - This option declares the type of type child element. By default, the velue is “choice”.
* **operator_options** - Value of this option will be used as the options array for the type field.
* **show_filter** - If FALSE, then the filter will be hidden when it is rendered in the filter list.

## oro_type_text_filter Form Type

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = text
* operator_choices
  * TextFilterType::TYPE_CONTAINS
  * TextFilterType::TYPE_NOT_CONTAINS
  * TextFilterType::TYPE_EQUAL

**Parent Type**

oro_type_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\TextFilterType`

<a id="backend-filters-form-types-number"></a>

## oro_type_number_filter Form Type

**Options**

* data_type
* fromatter_options

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = text
* operator_choices
  * NumberFilterType::TYPE_GREATER_EQUAL
  * NumberFilterType::TYPE_GREATER_THAN
  * NumberFilterType::TYPE_EQUAL
  * NumberFilterType::TYPE_LESS_EQUAL
  * NumberFilterType::TYPE_LESS_THAN
* data_type = NumberFilterType::DATA_INTEGER

**Parent Type**

oro_type_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\NumberFilterType`

**Options**

* **data_type** - This option can be used for configuration of value field type. Can be a value of one of constants:
  ::DATA_INTEGER or NumberFilterType::DATA_DECIMAL.

**formatter_options**

In addition to data_type option, this option can contain parameters for number formatter that is used by value field.
Available attributes are:

* decimals - maximum fraction digits
* grouping - use grouping to separate digits
* orderSeparator - symbol of grouping separator
* decimalSeparator - symbol of decimal separator.

<a id="backend-filters-form-types-oro-type-number-range-filter"></a>

## oro_type_number_range_filter Form Type

**Options**

* data_type
* formatter_options

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = text
* operator_choices
  * NumberRangeFilterType::TYPE_BETWEEN
  * NumberRangeFilterType::TYPE_NOT_BETWEEN
  * NumberRangeFilterType::TYPE_GREATER_EQUAL
  * NumberRangeFilterType::TYPE_GREATER_EQUAL
  * NumberRangeFilterType::TYPE_GREATER_THAN
  * NumberRangeFilterType::TYPE_EQUAL
  * NumberRangeFilterType::TYPE_LESS_EQUAL
  * NumberRangeFilterType::TYPE_LESS_THAN
  * FilterUtility::TYPE_EMPTY
  * FilterUtility::TYPE_NOT_EMPTY
* data_type = NumberFilterType::DATA_INTEGER

**Parent Type**

oro_type_number_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\NumberRangeFilterType`

**Options**

* **data_type** - This option can be used for configuration of value field type. Can be a value of one of constants:
  NumberFilterType::DATA_INTEGER or NumberFilterType::DATA_DECIMAL.

**formatter_options**

In addition to data_type option, this option can contain parameters for number formatter that is used by value field.
Available attributes are:

* decimals - maximum fraction digits
* grouping - use grouping to separate digits
* orderSeparator - symbol of grouping separator
* decimalSeparator - symbol of decimal separator.

<a id="backend-filters-form-types-oro-type-choice-filter"></a>

## oro_type_choice_filter Form Type

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = choice
* operator_choices
  * ChoiceFilterType::TYPE_CONTAINS
  * ChoiceFilterType::TYPE_NOT_CONTAINS

**Parent Type**

oro_type_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\ChoiceFilterType`

<a id="backend-filters-form-types-oro-type-entity-filter"></a>

## oro_type_entity_filter Form Type

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = entity

**Parent Type**

oro_type_choice_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\EntityFilterType`

<a id="backend-filters-form-types-oro-type-boolean-filter"></a>

## oro_type_boolean_filter Form Type

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_options = choices
  * BooleanFilterType::TYPE_YES
  * BooleanFilterType::TYPE_NO

**Parent Type**

oro_type_choice_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\BooleanFilterType`

<a id="backend-filters-form-types-oro-type-daterange-filter"></a>

## oro_type_date_range_filter Form Type

**Options**

* widget_options
* type_values

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter

**Default Options**

* field_type = oro_type_date_range
* widget_options = [“dateFormat” => “mm/dd/yy”, “firstDay” => 0]
* operator_choices
  * DateRangeFilterType::TYPE_BETWEEN
  * DateRangeFilterType::TYPE_NOT_BETWEEN
* type_values
  * DateRangeFilterType::TYPE_BETWEEN
  * DateRangeFilterType::TYPE_NOT_BETWEEN

**Parent Type**

oro_type_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\DateRangeFilterType`

**Options Description**

* **widget_options** - Value of this option will be used by javascript widget to correctly display its data. Default value of this option depend from of current application locale options.
* **type_values** - Value of this option will be used by javascript widget to generate valid hint of current filter value (strings like “between %start% and %end%”, “before %start%”, “after %end%”, “not between %start%”, etc)

<a id="backend-filters-form-types-oro-type-datetime-filter"></a>

## oro_type_datetime_range_filter Form Type

**Options**

* widget_options
* type_values

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter
* type_values
* widget_options

**Default Options**

* field_type = oro_type_datetime_range
* widget_options = [“dateFormat” => “mm/dd/yy”, “timeFormat” => “hh:mm tt”, “firstDay” => 0]

**Parent Type**

oro_type_date_range_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\DateRangeFilterType`

## oro_type_date_range Form Type

**Children**

* start
* end

**Options**

* field_type
* field_options
* start_field_options
* end_field_options

**Default Options**

* field_type = “date”

**Class**

`Oro\Bundle\FilterBundle\Form\Type\DateRangeType`

**Options Description**

* **field_type** - This option declares type of start and end child elements.
* **field_options** - Value of this option will be used as options array for start and end fields.
* **start_field_options** - Value of this option will be used as options array for start field.
* **end_field_options** - Value of this option will be used as options array for end field.

## oro_type_datetime_range Form Type

**Default Options**

* field_type = “datetime”

**Parent Type**

oro_type_date_range

**Class**

`Oro\Bundle\FilterBundle\Form\Type\DateTimeRangeType`

<a id="backend-filters-form-types-grouping"></a>

## oro_type_date_grouping_filter Form Type

**Options**

* data_name
* joined_column
* not_nullable_field
* calendar_entity
* target_entity

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter
* field_type
* operator_choices

**Default Options**

* calendar_table = “calendarDate”
* calendar_column = ‘date’
* calendar_table_for_grouping = ‘calendarDate1’
* calendar_column_for_grouping = ‘date’
* joined_table = ‘joinedTableAlias’
* target_column = ‘date’

**Parent Type**

oro_type_choice_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\DateGroupingFilterType`

<a id="backend-filters-form-types-skip-empty-periods"></a>

## oro_type_skip_empty_periods_filter Form Type

**Options**

* not_nullable_field

**Inherit Options**

* field_type
* field_options
* operator_choices
* operator_type
* operator_options
* show_filter
* field_type
* operator_choices

**Parent Type**

oro_type_choice_filter

**Class**

`Oro\Bundle\FilterBundle\Form\Type\Filter\DateGroupingFilterType`

## Example of Usage

You can use filter form types as any other form type in Symfony. For example, consider you have a form
with three filters. In your form type you should add code like this:

```php
class MyFilterFormType extends AbstractType
{
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        // Add some form fields
        // ...
        // Add filters
        $builder->add('name', TextFilterType::class);
        $builder->add('salary', NumberFilterType::class);
        $builder->add('hobby', ChoiceFilterType::class, [
        field_options' => [
                'choices' => [1 => 'Coding', 2 => 'Hiking', 3 => 'Photography'],
                'multiple' => true
            ]
        ]);
    }
}
```

## References

* Symfony 2 Form Types
  * <a href="http://symfony.com/doc/master/cookbook/form/create_custom_field_type.html" target="_blank">Create Custom Field Type</a>
  * <a href="http://symfony.com/doc/master/reference/forms/types.html" target="_blank">Types</a>

<!-- Frontend -->
