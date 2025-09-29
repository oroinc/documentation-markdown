<a id="digital-assets"></a>

# Manage Digital Assets in the Back-Office

[Digital asset](../../../glossary.md#term-Digital-Assets) management (DAM) is a tool for organizing, storing, and managing digital files in one central location. For this purpose, use the Digital Assets section that lists all assets uploaded to the DA database of your application. Here, you can quickly find and edit the assets you need and create your personal database of the shared files.

![The list of all digital assets](user/img/marketing/digital-assets/digital_assets_main.png)

You can enable the DAM functionality for any entity attachment field that is of a [file, image, multiple files, or multiple images](../../system/entities/entity-fields/entity-fields-basic-properties.md#admin-guide-create-entity-fields-basic) type when creating an entity field. For more details, read the [Create Entity Fields](../../system/entities/entity-fields/index.md#doc-entity-fields) topic.

![Enable DAM for the image entity field](user/img/marketing/digital-assets/enable_DAM.png)

If DAM is enabled, it changes the usual uploading behavior of the related type field for the selected entity. Now, your entity attachments are first uploaded to the DA database. Then, you can select the required asset from the list of available DA records. Any other DAM-supported entity can further re-use all attachments that are saved to the DA pool.

If DAM is disabled, the usual uploading behavior is applied, enabling you to select the asset from your local directory and not save it to the DA pool. Such attachments cannot be shared and used by other entities.

![The difference in the image uploading behavior when **Use DAM** is set to yes and no](user/img/system/entity_management/use_dam_difference_file.png)
