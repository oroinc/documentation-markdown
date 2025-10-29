# Recurring Events

In most cases, recurring events are saved as a single instance of an event along with the ‘recurrence’  field where the recurring pattern is stored. Based on this pattern, Calendar UI expands the instance of one recurring event into a sequence of occurrences.

## Recurrence Pattern

Each calendar event has a recurrence field. This is a dictionary containing fields related to the event recurrence. Some fields are mandatory for all recurrence patterns, and some fields are required only for some patterns. The fields are described in the following table:

```none
<table>
<tr>
    <th rowspan="2">Field Name</th>
    <th colspan="6">Recurrence Pattern</th>
</tr>
<tr>
    <th>Daily</th>
    <th>Weekly</th>
    <th>Monthly</th>
    <th>MonthNth</th>
    <th>Yearly</th>
    <th>YearNth</th>
</tr>
<tr>
    <td>recurrenceType</td>
    <td>daily</td>
    <td>weekly</td>
    <td>monthly</td>
    <td>monthnth</td>
    <td>yearly</td>
    <td>yearnth</td>
</tr>
<tr>
    <td>interval</td>
    <td>Number of day</td>
    <td>Number of week</td>
    <td colspan="2">Number of month</td>
    <td colspan="2">Number of month (a multiple of 12, i.e. 12, 24, 36, 48 etc.</td>
</tr>
<tr>
    <td>instance</td>
    <td>Not used</td>
    <td>Not used</td>
    <td>Not used</td>
    <td>A value from 1 to 5</td>
    <td>Not used</td>
    <td>A value from 1 to 5</td>
</tr>
<tr>
    <td>dayOfWeek</td>
    <td>Not used</td>
    <td>Array of week days</td>
    <td>Not used</td>
    <td>Array containing one week day</td>
    <td>Not used</td>
    <td>Array containing one week day</td>
</tr>
<tr>
    <td>dayOfMonth</td>
    <td>Not used</td>
    <td>Not used</td>
    <td>Day of month</td>
    <td>Not used</td>
    <td>Day of month</td>
    <td>Not used</td>
</tr>
<tr>
    <td>monthOfYear</td>
    <td>Not used</td>
    <td>Not used</td>
    <td>Not used</td>
    <td>Not used</td>
    <td colspan="2">Month number from 1 to 12</td>
</tr>
<tr>
    <td>startTime</td>
    <td colspan="6">Range of recurrence - Start (mandatory)</td>
</tr>
<tr>
    <td>endTime</td>
    <td colspan="6">Range of recurrence - End (mandatory)</td>
</tr>
<tr>
    <td>occurrences</td>
    <td colspan="6">Range of recurrence - End after X occurrences (optional)</td>
</tr>
<tr>
    <td>timeZone</td>
    <td colspan="6">The time zone in which the time is specified (mandatory)</td>
</tr>
</table>
```

Usually, for recurring events, only one entity of OroBundleCalendarBundleEntityCalendarEvent is created with reference to the entity of OroBundleCalendarBundleEntityRecurrence. When an API request with a date range is sent to the server, it dynamically expands each recurring event into occurrences of this recurring event. Each occurrence event will have the same data as the original recurring event, but with start and end dates dynamically calculated.

## Exceptions

Each occurrence of a recurrent event can be modified, so it differs from other occurrences. Such an event has its own step
and is called an “exception” event. Separate event entities with additional fields represent these exceptions.
The standard event fields (title, description, start, end, etc.) can differ from the parent recurrence event fields.
Here is the list of additional fields which are applicable only for exception events:
- **recurringEventId** – the id of the parent recurring event.
- **originalStart** – the original start date and time of this occurrence. It may differ from the actual start date for the recurrence.
- **isCancelled** – A boolean field indicating whether the occurrence was canceled (removed from the user’s calendar).

## Recurrence Validation

To make sure that the recurrence pattern has all the necessary data, you  can validate it with the recurrence model:

```php
use Oro\Bundle\CalendarBundle\Model\Recurrence as RecurrenceModel;

...

/** @var \Symfony\Component\Validator\Validator\ValidatorInterface $validator */
/** @var \Oro\Bundle\CalendarBundle\Entity\Recurrence $recurrence */
$model = new RecurrenceModel($this->validator);
$model->validateRecurrence($recurrence);
```

## Key Classes

Here is a list of the key classes:

**Entities**

- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Entity/Recurrence.php" target="_blank">Entity/Recurrence</a> - Entity that contains all recurrence pattern data and has ‘one to one’ relation with <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Entity/CalendarEvent.php" target="_blank">CalendarEvent</a>.

**Model**
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence.php" target="_blank">Model/Recurrence</a> - Model represents domain logic related to recurrence. The recurrence entity is passed to the model in most cases to fulfill its responsibilities. The client code can use it in the application.

**Model / Strategies**
Strategies implement different types of recurrence patterns. The model uses strategies to delegate responsibilities related
to different recurrence patterns. Strategies should not be used directly in application client code.

- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/AbstractStrategy.php" target="_blank">Model/Recurrence/AbstractStrategy</a> - The base class for recurrence patterns. It contains all basic methods that can be reused in child classes.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/DailyStrategy.php" target="_blank">Model/Recurrence/DailyStrategy</a> - The daily recurrence pattern strategy implementation.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/DelegateStrategy.php" target="_blank">Model/Recurrence/DelegateStrategy</a> - The class that determines what recurrence pattern strategy must be used according to the recurrence data.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/MonthlyStrategy.php" target="_blank">Model/Recurrence/MonthlyStrategy</a> - The Monthly recurrence pattern strategy implementation.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/MonthNthStrategy.php" target="_blank">Model/Recurrence/MonthNthStrategy</a> - The MonthNth recurrence pattern strategy implementation.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/StrategyInterface.php" target="_blank">Model/Recurrence/StrategyInterface</a> - An interface of recurrence pattern strategies.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/WeeklyStrategy.php" target="_blank">Model/Recurrence/WeeklyStrategy</a> - The Weekly recurrence pattern strategy implementation.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/YearlyStrategy.php" target="_blank">Model/Recurrence/YearlyStrategy</a> - The Yearly recurrence pattern strategy implementation.
- <a href="https://github.com/oroinc/OroCalendarBundle/blob/master/Model/Recurrence/YearNthStrategy.php" target="_blank">Model/Recurrence/YearNthStrategy</a> - The YearNth recurrence pattern strategy implementation.

<!-- Frontend -->
