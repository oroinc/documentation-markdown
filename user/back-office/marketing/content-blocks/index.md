<!-- begin -->

# Manage Content Blocks in the Back-Office

#### HINT
This section is part of the [Content Management Concept Guide](../../../concept-guides/content-management/index.md#concept-guide-content-management) topic that provides the general understanding of the tools that help manage the content of your website, such as web catalog, landing page, content blocks, widgets, and WYSIWYG editor.

Content Blocks are the foundation of your site, and they can help create a custom layout. In Oro applications, you can modify the existing content blocks, or create your own.

#### NOTE
Creating a new content block requires developers’ assistance. As a sample, use Home Page Slider content block, <a href="https://github.com/oroinc/orocommerce/tree/4.2/src/Oro/Bundle/CMSBundle/Resources/views/layouts/blank/oro_frontend_root/home_page_slider.yml" target="_blank">configuration</a> in the yaml file that helps embed it into the website homepage.

To edit a defined content block:

1. Navigate to **Marketing > Content Blocks** in the main menu.
2. Click <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> at the end of the content block you wish to edit, and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to open the selected block for editing.
   ![The actions available to a content block from the grid](user/img/marketing/content_blocks/ContentBlocks.png)
3. In the *General* tab, you can amend the following fields:
   * **Owner** — The owner of the content block.
   * **Alias** — The unique identifier that can be used in the layout to render a block.
   * **Titles** — Localized block title.

   #### NOTE
   To enable/disable the content block, select/clear the **Enabled** check box.
4. In the *Restrictions* section, you can specify or edit visibility restrictions for the content block.

   By default, the content block is displayed for any localization, on any website, and for any customer.
   To make OroCommerce apply a content block to the storefront only for the particular combination of these facts, create a restriction by selecting all or some of the following: target localization, website, customer, or customer group.

   #### NOTE
   Only one field must be chosen for customers at a time, either a customer group or a customer.
5. In the *Content Variants* section, you can add (click **Add Content**) or remove (click <i class="fa fa-times fa-lg" aria-hidden="true"></i>) various content variants for the content block. Once you add more than one content variant, you will have to apply restrictions to any non-default variants. These restrictions help you set up the conditions where content should override the default option.

   #### WARNING
   Never leave the restrictions for non-default variant empty. This may cause unexpected priority collision between the default and non-default variant.

   #### NOTE
   Only one field must be chosen for customers at a time, either a customer group and a customer.

For instance, you can set the content block to have a specific text displayed for *Non-authenticated Visitors*. For that:

1. Set visibility restrictions to *Non-authenticated Visitors* in **Restrictions > Customer Groups**.
2. Add a new content variant by clicking **Add Content** in the **Content Variant** section.
3. Enter text.
4. Drag the selected element (a text, an image, a column, or a **<>** source code) from the editor’s manager panel and drop it to the required location.
5. Rearrange the content or modify the style of the elements by navigating from tab to tab of the WYSIWYG editor’s manager panel. For more details on WYSIWYG management, see the [WYSIWYG Editor](../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) topic.
   ![A sample of a content block's restriction setting for non-authenticated visitors](user/img/marketing/content_blocks/ContentBlocksSample.png)

<a id="user-guide-landing-pages-marketing-content-blocks-translation"></a>

To translate the content block (e.g., the homepage slider), restrict it to the required localization(s).

For instance, to translate the homepage slider into German:

1. Set the visibility restriction to *German* in **Restrictions > Localization**.
2. Edit the default variant to include Germany-specific content, or add another content variant by clicking **+Add**.
3. Click **Save and Close**.
4. Once switched to the German localization, the home page slider displays the new content.
   ![Translated home page slider in the storefront](user/img/marketing/content_blocks/translated_slider_front.png)

<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
