<a id="wysiwyg-field-dev-guide"></a>

# WYSIWYG Field

<a href="https://en.wikipedia.org/wiki/WYSIWYG" target="_blank">WYSIWYG</a> field type utilizes an editor that provides advanced editing capabilities. Any such editor can be integrated with WYSIWYG fields, and the <a href="https://grapesjs.com/docs/" target="_blank">GrapesJS</a> editor is integrated out of the box.
An administrator can add a new WYSIWYG field to any entity available in Entity Management. Landing Page and [Content Blocks](../content-blocks.md#bundle-docs-commerce-cms-bundle-content-blocks) entities use WYSIWYG for their content fields by default.

## Structure

Each WYSIWYG field stores data in three separate pieces:

> * `content` - a field (database column) to save the HTML markup of the content;
> * `styles` - a field (database column) to save the CSS styles applied by the editor to the content;
> * `properties` - a field (database column) to save additional JSON metadata stored by the editor to properly initialize its UI.

When using Entity Management UI, the system takes care of managing the additional fields in the background. For example, if you add a WYSIWYG field called `description` to some entity, the system will automatically create fields called `description_styles` and `description_properties`. When adding a WYSIWYG field programatically, developers should create and name all three fields and databases columns themselves.

## Related Documentation

* <a href="https://en.wikipedia.org/wiki/WYSIWYG" target="_blank">WYSIWYG</a>
* <a href="https://grapesjs.com/docs/" target="_blank">GrapesJS</a>

<!-- Frontend -->
