<a id="user-guide-landing-pages-marketing-content-widgets"></a>

<a id="content-widgets-user-guide"></a>

# Manage Content Widgets in the Back-Office

#### HINT
This section is part of the [Content Management Concept Guide](../../../concept-guides/content-management/index.md#concept-guide-content-management) topic that provides a general understanding of the tools that help manage the content of your website, such as web catalog, landing page, content blocks, widgets, and WYSIWYG editor.

Content widgets are snippets of structured information that you can insert into any WYSIWYG field in your application. [WYSIWYG fields](../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) are available throughout OroCommerce; for example, in category descriptions, on edit pages of products, content blocks, and landing pages.

There are four content widget types:

* An Image Slider
* A Contact Us form
* A Product Mini Block
* A Product Segment
* Tabbed Content

Each of these widget types has a different set of options.

Please keep in mind that:

| You can:<br/><br/>* Edit content widgets from the grid and view page.<br/><br/>You cannot:<br/><br/>* Delete a widget if it is used in a content block or a landing page.<br/>* Change widget type for an already existing widget.   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

#### NOTE
Whenever you modify a content widget, changes are applied everywhere the widget is used.

## Create a Content Widget

To create a new content widget:

1. Navigate to **Marketing > Content Widgets** in the main menu.
2. Click **Create Content Widget** on the top right.

   #### NOTE
   If you have more than one organization in your OroCommerce application, first select the organization to which you want to add a new content widget.
3. Depending on the widget type, form fields are different:
   * **Contact Us Form** - Enables you to add a standard Contact Us form.

   > ![Contact us content widget form](user/img/marketing/content_widgets/contact_us.png)
   * **Image Slider** - Enables you to configure and add an image slider.

   > ![Image slider content widget form](user/img/marketing/content_widgets/image_slider_1.png)
   > <br/>

   > #### NOTE
   > You can add as many slides as necessary by clicking **Add** at the bottom of the *Slides* section.
   > ![Image slider content widget form](user/img/marketing/content_widgets/image_slider_2.png)

   > <br/>
   * **Product Mini Block** - Enables you to add a block with product information with or without prices and/or the **Add to Shopping List** button.
     ![A product mini block form](user/img/marketing/content_widgets/mini-block.png)

   > <br/>
   * **Product Segment** - Enables you to add a product segment content widget, configure how many max and min items to show, whether to use slider on mobile, and show the **Add to Shopping List** button in the storefront. Only segments with type *Product* are listed in the **Segment** field dropdown. You can modify an existing [segment](../../reports-segments/segments.md#user-guide-business-intelligence-filters-segments) or create a new one under **Reports&Segments > Manage Segments**.
     ![A product mini block form](user/img/marketing/content_widgets/product-segment.png)

   > <br/>
   * **Tabbed Content** - Enables you to add content to your storefront website in a form of tabs or an accordion.
     ![Tabbed vs Accordion view of tabbed content widget](user/img/marketing/content_widgets/tabs-vs-accordion.png)

   > <br/>
   > > Tabbed content widget uses the [WYSIWYG editor](../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) which enables you to inject other content widget(s), such as a contact us form, into your current tabbed content widget.
   > > ![Contact us widget embedded in tabbed content widget](user/img/marketing/content_widgets/injected-widget.png)
4. Once you have provided all widget-specific details, click **Save and Close**.
   <!-- .. image:: /user/img/marketing/content_widgets/widget-view.png
   :alt: Content widget view page -->
   <br/>

   #### HINT
   Each content widget may have various representations in the form of layouts. Developers define layouts using the existing [layout update functionality](../../../../frontend/storefront/layouts/index.md#dev-doc-frontend-layouts-layout), which enables you to alternate between the pre-configured designs for each widget in the back-office.
   ![Select Layouts in the back-office](user/img/marketing/content_widgets/layout-dropdown.png)

   Please be aware that layouts are theme-specific. For more information, please refer to the [CMS bundle documentation](../../../../bundles/commerce/CMSBundle/content-widgets/index.md#how-to-create-content-widget-type).
