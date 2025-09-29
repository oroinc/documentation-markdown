<a id="bundle-docs-platform-dam"></a>

# OroDigitalAssetBundle

OroDigitalAssetBundle bundle provides the Digital Asset Management (DAM) functionality and CRUD for digital assets. It can be enabled for fields of type File and Image both in the back-office UI via the entity management, and via the field configuration.

The following example is an illustration of how to enable DAM for the Image field type:

```php
$this->attachmentExtension->addImageRelation(
    $schema,
    'oro_table_name',
    'image',
    [
        'attachment' => [
             'use_dam' => true,
        ]
     ],
     10
);
```

## Related Articles

* [Digital Asset Management](../../../user/back-office/marketing/digital-assets/index.md#digital-assets)
* [Use DAM in Entity Manager for File and Image Field Types](../../../user/back-office/system/entities/entity-fields/entity-field-type-related-properties.md#admin-guide-create-entity-fields-type-related)
