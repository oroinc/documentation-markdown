<a id="backend-entities-filters-grid-extension"></a>

# Grid Extension

The FilterBundle provides an extension for datagrid with ORM and Search datasources.
Filters could be added to the datagrid in the datagrids.yml file for a specified datagrid under the filters node.
Definition of any filter requires option data_name that should be referenced to column in the query and type (filter type).

For example:

```none
SOME_DATAGRID:
    source:
        type: orm
        query:
            select:
                - g.id
                - g.label
            from:
                - { table: Oro\Bundle\ContactBundle\Entity\Group, alias: g }

    filters:
        columns:
            SOME_FITLER_NAME: # uses for query param, and for setting default filters
                type: string  # Filter type, list of available types described below
                data_name: g.id
                renderable: true|false #whether filter available or not. If filter is not renderable it will not be displayed in filter list but will be accessible in filter management.
                visible: true|false #If set to "false" - filter will not be displayed anywhere in UI. However, one can still set filter's value in backend or via url in frontend
                disabled: true|false #If filter is disabled it will not be displayed in filter list and will not be available in filter management.
                order: number #The number of filter's position, allows to change order of the filters (by default it is not defined and follows columns order)
                force_like: true|false #Different search engines uses different methods for text search. When `force_like` is set to true, text-based filters will use simple `LIKE %%` OR `NOT LIKE %%`statement which depends on a chosen operator
                min_length: integer #In case of text-based filters this option introduce possibility to ignore filters with less characters then specified. Validation message will also appear
                divisor: number #In case of number-based filters this option will filter values rendered with datagrid divisor option.
                case_insensitive: true|false #When set to 'true' text search filter will be case insensitive [Postgres only].
                value_conversion: string #Callback for text search filter used for converting value passed to a query.
```

## Default Values

### String Filter

```none
filters:
    columns:
        fieldName:
            type:      string
            data_name: priorityLabel
            case_insensitive: true
    default:
        fieldName: { value: 'someText', type: 'Oro\Bundle\FilterBundle\Form\Type\Filter\TextFilterType::TYPE_CONTAINS' }
```

### Choice Filter

```none
filters:
    columns:
        period:
            type: orocrm_period_filter
            data_name: period
            options:
                populate_default: false
                field_options:
                    choices:
                        monthPeriod:    Monthly
                        quarterPeriod:  Quarterly
                        yearPeriod:     Yearly
    default:
        period: { value: monthPeriod }
```

## Additional Params

- filter_condition - use OR or AND operator in expression
- filter_by_having - filter expression should be added to HAVING clause
- options - pass form options directly to filter form type (for additional info, [see Filter Form Types](filter-form-types.md#backend-filters-form-types)).

## Filters

### String Filter

Provides filtering using string comparison.

type: string - Validated by TextFilterType in the backend and rendered by `oro/filter/choice-filter`.  When case_insensitive is set to false, it is possible to convert value by using callback defined in ‘value_conversion’.

### Number and Percent Filter

Provides filtering by numbers comparison.

#### NOTE
Value from frontend will automatically transform to percentage for “percent” filter.

type: number - integer/decimal filter

Validated by [NumberFilterType](filter-form-types.md#backend-filters-form-types-number) in the backend and rendered by `oro/filter/number-filter`.

type: number-range - integer/decimal filter

type: percent - percent filter

type: currency - currency filter

Validated by [NumberRangeFilterType](filter-form-types.md#backend-filters-form-types-oro-type-number-range-filter) in the backend
and rendered by `oro/filter/number-range-filter`.

### Boolean Filter

Provides filtering for boolean values.

type: boolean - Validated by [BooleanFilterType](filter-form-types.md#backend-filters-form-types-oro-type-boolean-filter) in the backend and rendered by `oro/filter/boolean-filter` with a predefined set of options (yes/no).

### Choice Filter

Provides filtering data using a list of predefined choices

type: choice - Validated by [ChoiceFilterType](filter-form-types.md#backend-filters-form-types-oro-type-choice-filter) in the backend
and rendered by `oro/filter/select-filter`.

### Entity Filter

Provides filtering data using list of choices that extracted from database.

type: entity - Validated by [EntityFilterType](filter-form-types.md#backend-filters-form-types-oro-type-entity-filter) in the backend
and rendered by `oro/filter/select-filter`.

### Date Filter

Provides filtering data by date values

type: date - Validated by [DateRangeFilterType](filter-form-types.md#backend-filters-form-types-oro-type-daterange-filter).
Rendered by `oro/filter/date-filter`.

### DateTime Filter

Provides filtering data by datetime values

type: datetime - Validated by [DateTimeRangeFilterType](filter-form-types.md#backend-filters-form-types-oro-type-datetime-filter).
Rendered by `oro/filter/datetime-filter`.

### DateGrouping Filter

Provides grouping dates using list of predefined choices: Day, Month, Quarter, Year

type: datetime - Validated by [DateGroupingFilterType](filter-form-types.md#backend-filters-form-types-grouping) in the backend
and rendered by `oro/filter/datetime-filter``.

### SkipEmptyPeriods Filter

Provides skipping empty data using list of predefined choices: Yes, No

type: choice - Validated by [SkipEmptyPeriodsFilterType](filter-form-types.md#backend-filters-form-types-skip-empty-periods) in the backend
and rendered by `oro/filter/select-filter`.

## Customization

To implement your filter you have to do following:

- Develop class that implements `Oro\Bundle\FilterBundle\Filter\FilterInterface` (also there is basic implementation in AbstractFilter class)
- Register your filter as service with tag { name: oro_filter.extension.orm_filter.filter, type: YOUR_FILTER_TYPE }
- Create and register JavaScript module for the new filter. The *map-filter-module-name.js* defines the JavaScript module name for a filter based on frontend_type by the pattern `'oro/filter/{{type}}-filter'`. Since module name does not represent the real path to the filter file, add the alias and dynamic-imports definitions to your *jsmodules.yml* file. E.g.:
  ```yaml
  aliases:
      oro/filter/subcategory-filter$: orocatalog/js/filter/subcategory-filter
  dynamic-imports:
      orodatagrid:
          - oro/filter/subcategory-filter
  ```

<!-- Frontend -->
