<a id="wysiwyg-field-dev-guide"></a>

# WYSIWYG Field

<a href="https://en.wikipedia.org/wiki/WYSIWYG" target="_blank">WYSIWYG</a> field type utilizes an editor that provides advanced editing capabilities. Any editor can be integrated with WYSIWYG fields, and the <a href="https://grapesjs.com/docs/" target="_blank">GrapesJS</a> editor is integrated out of the box.
An administrator can add a new WYSIWYG field to any entity available in Entity Management. Landing Page and [Content Blocks](../content-blocks.md#bundle-docs-commerce-cms-bundle-content-blocks) entities use WYSIWYG for their content fields by default.

## Structure

Each WYSIWYG field data is divided and stored in three separate pieces: HTML markup, CSS styles, JSON properties.
In practice, the field with the `content` name is stored in three fields:

> * `content` - the main field (database column) to save the HTML markup of the content;
> * `content_style` - an additional field (database column) to save the CSS styles applied by the editor to the content;
> * `content_properties` - an additional field (database column) to save additional JSON metadata stored by the editor to properly initialize its UI.

## Related Documentation

* <a href="https://en.wikipedia.org/wiki/WYSIWYG" target="_blank">WYSIWYG</a>
* <a href="https://grapesjs.com/docs/" target="_blank">GrapesJS</a>

<!-- Frontend -->
