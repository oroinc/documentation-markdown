<a id="user-guide-marketing-web-catalog-content-variant"></a>

# Configure Content Variants for the Content Node

This section provides an overview of the content node types and guidance on their setup.

#### NOTE
The first content variant added to the node is marked as the default variant. Specify the restrictions next to the content variant details when adding more content variants. These restrictions will limit the use of this content variant only to specific cases.

![Specify the restrictions for the default content node](user/img/marketing/web_catalogs/ContentVariantSection.png)

<a id="user-guide-marketing-web-catalog-content-variant-system-page"></a>

## Add a System Page

The system page is one of the standard pre-designed pages of the OroCommerce storefront (e.g., Homepage, Requests for Quotes, Open Orders).

To add a system page to the menu in the OroCommerce storefront:

1. Select the **Add System Page** in the Content Variants list.
   ![Add system page and specify restrictions](user/img/marketing/web_catalogs/WebCatalogCreateContentVariantsSystemPage.png)
2. Select the system page from the list.
3. This step applies only to the content nodes with more than one content variant.

   When your system page is not selected as a default variant for the content node,  you can define the condition when the system page overrides the default content variant. See the [Configure Content Visibility](visibility.md#user-guide-marketing-web-catalog-content-visibility) section for more information.
4. Click **Save** when you have filled in the web catalog content node or keep adding the content variants.

<a id="user-guide-marketing-web-catalog-content-variant-product-page"></a>

## Add a Product Page

The product page node is a direct link to the product details in the OroCommerce storefront.

To add a product page node to the menu in the OroCommerce storefront:

1. Select the **Add Product Page** in the Content Variants list.
   ![Add product page and spec there is a *Restrictions* section beneath the selected system page.ify the restrictions](user/img/marketing/web_catalogs/WebCatalogCreateContentVariantsProductPage.png)
2. Select the product from the list. To use search, start typing the product name or SKU in the box. To use filtering, click on the **bars**, and select the filtering conditions in the *Manage filters* section.
3. This step applies only to the content nodes with more than one content variant.

   When your product page is not selected as a default variant for the content node, you can define the condition when the product details override the default content variant in the *Restrictions* section beneath the selected product. See [Configure Content Visibility](visibility.md#user-guide-marketing-web-catalog-content-visibility) section for more information.
4. Click **Save** when you have filled in the web catalog content node or continue to add the content variants.

<a id="user-guide-marketing-web-catalog"></a>

## Add All Products Page to Web Catalog

<!-- begin_all_products -->

Once the All Products page has been enabled in the system configuration [globally](../../../system/configuration/commerce/catalog/global-all-products.md#sys-conf-commerce-catalog-special-pages-global) or [per website](../../../system/websites/web-configuration/commerce/catalog/website-all-products.md#sys-conf-commerce-catalog-special-pages-website), you can add it as part of your web catalog.

#### NOTE
We recommend enabling the All Products page exclusively for *small catalogs* with no more than a few hundred products, otherwise browser performance might be affected.

1. Navigate to **Marketing > Web Catalogs** in the main menu.
2. For the necessary web catalog, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> more actions menu to the right and click <i class="fa fa-sitemap fa-lg" aria-hidden="true"></i> to start editing the catalog content tree.

> ![Click the content tree icon in the more options menu of the Default Web Catalog](user/img/marketing/web_catalogs/AllProductsEditContentTree.png)
1. In the **Content Nodes** menu on the left, click on the node to select the one you want to add the All Products page to.
2. Click **Create Content Node** on the top right of the page.
3. Complete the required fields to [configure the web catalog node](first-level-menu.md#user-guide-marketing-web-catalog-content-node).
4. In the **Content Variants** section, make sure to add the All Products as the system page. To do this:
   1. Click **Add System Page**.
   2. From a **System Page Route** list, select the *Oro Catalog Frontend Product Allproducts (All Products page)*.

   ![Selecting the All products page for the System Page Route for the Default Web Catalog](user/img/marketing/web_catalogs/AllProductsContentVariants.png)

   #### NOTE
   See [Content Variants](#user-guide-marketing-web-catalog-content-variant) topic for more information on using content variants. See [System Page](#user-guide-marketing-web-catalog-content-variant-system-page) topic for more information on this content variant type.
5. Once all the details have been provided, click **Save** on the top right of the page.

<!-- finish_all_products -->

<a id="user-guide-marketing-web-catalog-content-variant-category"></a>

## Add a Category

A category node is a direct link to the product category with the list of products in the OroCommerce storefront.

To add a category node to the menu in the OroCommerce storefront:

1. Select **Add Category** in the Content Variants list.
   ![Select a category from the content tree](user/img/marketing/web_catalogs/WebCatalogCreateContentVariantsCategory.png)
2. Click <i class="fa fa-caret-down fa-lg" aria-hidden="true"></i> next to **Sub-Categories** to select the required option from the list.

   The available options are:
   * **Include, show as filter** - Used to include all the products assigned to the subcategories of the selected category and the products already assigned directly. The subcategories of the first level with at least one product will be displayed as a category filter in the OroCommerce storefront.
     ![Illustration of the Include, show as filter option](user/img/marketing/web_catalogs/subcategory_filter_1.png)
   * **Do not include** - Used to include the products assigned only to the selected category. If the category has a subcategory, its product items will not be displayed.
3. Select the category from the product catalog tree. To use search, start typing the category name in the box. Use **>** and **v** to expand/collapse the tree node.
   ![Start typing the category name in the search bar](user/img/marketing/web_catalogs/subcategory_filter_3.png)
4. This step applies only to the content nodes with more than one content variant.

   When your category is not selected as a default variant for the content node, you can define the condition when the selected category overrides the default content variant in the *Restrictions* section beneath the categories tree. See [Configure Content Visibility](visibility.md#user-guide-marketing-web-catalog-content-visibility) section for more information.
5. Click **Save** when you have filled in the web catalog content node or keep adding the content variants.

<a id="user-guide-marketing-web-catalog-content-variant-landing-page"></a>

## Add a Landing Page

Landing Page node is a link to the [custom content page](../../landing-pages/index.md#user-guide-landing-pages) created in the **Marketing > Landing Pages** section.

To add a landing page node to the menu in the OroCommerce storefront:

1. Select the **Add Landing Page** in the Content Variants list.
   ![Add a landing page and specify the restrictions](user/img/marketing/web_catalogs/WebCatalogCreateContentVariantsLandingPage.png)
2. Select the existing landing page from the list. To use search, start typing the keywords in the box to search for the necessary page. To use filtering, click on the **bars**, and select the filtering conditions in the *Manage filters* section. Alternatively, you can create a new landing page:
   1. To create a new landing page, click **+** to the right from the Landing page list.
   2. Fill in the landing page details and contents as described [here](../../landing-pages/index.md#user-guide-landing-pages-create).

   Enable the **Do Not Render Title** option if you do not want the title of the landing page to be displayed in the storefront.
3. This step applies only to the content nodes with more than one content variant.

   When your landing page is not selected as a default variant for the content node, you can define the condition when the landing page overrides the default content variant in the *Restrictions* section beneath the selected landing page. See [Configure Content Visibility](visibility.md#user-guide-marketing-web-catalog-content-visibility) section for more information.
4. Click **Save** when you are done filling in the web catalog content node or keep adding the content variants.

<a id="user-guide-marketing-web-catalog-content-variant-product-collection"></a>

## Add a Product Collection

Product Collection is a filter-based segment that helps you display a custom and dynamic set of products in the web catalog similarly to the category contents.

#### NOTE
You can control the frequency of the product collections indexation. By default, product collections are indexed every hour. See the [Product Collections Configuration](../../../system/configuration/commerce/product/product-collections.md#configuration-guide-commerce-configuration-product-collections) guide for the details on how to change the default indexation frequency.

1. To add a product collection node to the menu in the OroCommerce storefront:

   Select the **Add Product Collection** in the Content Variants list.
   ![Add a product collection and specify the restrictions](user/img/marketing/web_catalogs/ProductCollection.png)
2. To name a segment of the product collection:

   Enter the segment name for the product collection in the provided field.
   ![Enter the segment name for the product collection in the provided field](user/img/marketing/web_catalogs/SegmentName.png)
3. To add a product to the collection via filter:

   In the All Added tab, click <i class="fa fa-filter fa-lg" aria-hidden="true"></i> **Advanced Filter** to set up a [filter](../../../reports-segments/filters.md#user-guide-getting-started-filters) that will limit the products list and include only the necessary products.
   ![Set up a filter to limit the products list](user/img/marketing/web_catalogs/AdvancedFilter.png)

   #### NOTE
   <i class="fa fa-filter fa-lg" aria-hidden="true"></i> **Advanced Filter** is hidden by default.

   Click **Preview Results** to check whether the products found via the filter match your criteria or to exclude unnecessary items from the list.
   ![Click Preview Results](user/img/marketing/web_catalogs/PreviewResultsExclude.png)

   #### NOTE
   To manage the columns displayed Within the products grid, click <i class="fa fa-cog fa-lg" aria-hidden="true"></i>.
4. To add a product to the collection manually:

   Click **Add** next to <i class="fa fa-filter fa-lg" aria-hidden="true"></i> **Advanced Filter** to add the selected products manually. This can be used when you have a few products to be added, and there is no need to set up a complicated filter, or when you need to add specific products that may be out of the filter’s scope.
   ![Click Add and select the products manually](user/img/marketing/web_catalogs/AddProductsManually.png)

> Manually added items will appear both in the **Manually Added** and **All Added** tabs.
1. To exclude items from the collection:

   To ensure that specific items are excluded from the list of the product collection and will not be included automatically or manually, click **Add** in the **Excluded** tab:
   ![Click Add in the Excluded tab](user/img/marketing/web_catalogs/AddToExluded.png)

   Tick the Selected box to the left of the necessary products, and click **Add**.

   #### NOTE
   You can use the filter on the top of the dialog to limit the scope of the products and make them fit into the visible area.

   ![Select the necessary products manually](user/img/marketing/web_catalogs/ExcludeItemsFromProductCollection.png)
2. To reset products:

   To clear all filters and reset the product collection to the default state, click **Reset Products** next to the tabs.
   ![Click Reset Products next to the tabs](user/img/marketing/web_catalogs/ResetProducts.png)
3. To define a sort order for products:

   Each product selected in the All Added grid can have a sort order associated with it that will define the default order in which the product will appear in the storefront. 0 is the highest priority, and you can input any positive decimal number. Empty values will be sorted last. You can also click on the **Manage Sort Order** button to be able to manage the sort order of products in the product collection in a separate pop-up window. Products with grey background have sorting number assigned. Product with white background have no sorting order. You can drag and drop the horizontal background separator up and down to apply or clear the sorting order. All changes made to the sorting order in this dialog window will be applied immediately.
   ![Clicking the Manage Sort Order button opens a new pop-up window to bulk sort the products added to the product collection.](user/img/marketing/web_catalogs/manage-sort-order.png)
4. This step applies only to the content nodes with more than one content variant.

   When your collection is not selected as a default variant for the content node, you can define the condition when the product collection overrides the default content variant in the *Restrictions* section beneath the product collection preview. See [Configure Content Visibility](visibility.md#user-guide-marketing-web-catalog-content-visibility) section for more information.
5. Click **Save** when you have filled in the web catalog content node or keep adding the content variants.

<a id="user-guide-marketing-web-catalog-default-content-variant"></a>

## Set a Default Content Variant

The first content variant added to the node is marked as the default variant.

When adding more content variants, they have a dedicated restrictions section next to the content variant details. These restrictions will limit the use of this content variant only to specific cases; the default option is used in any other case.

Select the radio on the top left of its type to set up a newly added content variant as default.

![Select the content variant to make it the default one](user/img/marketing/web_catalogs/change_default_variant.png)
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
