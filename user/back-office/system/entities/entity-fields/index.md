<a id="doc-entity-fields"></a>

<a id="admin-guide-create-entity-fields"></a>

<a id="doc-entity-fields-create"></a>

# Create Entity Fields

Fields are used to store details of entity records. For example, a ‘street name’, a ‘zip code’, and a ‘building number’ may be fields of an ‘address.’ You can add new fields to any extendable [system entity](../../../../glossary.md#term-System-Entity).

This topic describes how you can create custom entity fields, explains what basic and advanced entity field properties are available for them, and illustrates [examples](create-entity-field-example.md#admin-guide-create-entity-fields-example) of adding new fields to existing entities.

To create a custom entity field:

1. Navigate to **System > Entities > Entities Management** in the main menu.
2. On the **All Entities** page, click the required entity to open its page.
3. On the entity page, click **Create Field**  on the top right.

![Highlighting the Create field button](user/img/system/entity_management/create-field.png)

#### HINT
You may receive the following warning message which notifies you about the limits for the number of fields that can be created, which can effect the future export of entities.

| The number of fields stored as columns in the X table (the fields that are relations or that have ever been marked<br/>as “A”, “B”, “C”) is approaching the limit after which it will no longer be possible to export Y with the standard X export.<br/>Remaining number of attributes - approximately Z.   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

Once 90% of the limit is reached, you will receive a flash message with the related warning.

Reaching 100% of the limit triggers a warning message on a potential inactive export when clicking the Export button.

1. Provide the [basic entity field properties](entity-fields-basic-properties.md#admin-guide-create-entity-fields-basic), such as the name, the field and field storage types.
2. Click **Continue**.
3. Provide [advanced field properties](entity-fields-advanced-properties.md#admin-guide-create-entity-fields-advanced), some of which can be field-type-related.
4. Click **Save and Close** when you finish creating the new entity field.
5. Once the field is saved, [update the schema](../manage-entity-fields.md#admin-guide-update-schema), if the storage type for the field is set to **Table Column**.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->

**Related Topics**

* [Basic Entity Field Properties](entity-fields-basic-properties.md)
* [Advanced Entity Field Properties](entity-fields-advanced-properties.md)
* [Type-Related Entity Field Properties](entity-field-type-related-properties.md)
* [Examples of Creating Custom Entity Fields](create-entity-field-example.md)
