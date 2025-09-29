<a id="user-guide-marketing-web-catalog-sample"></a>

# Build a Custom Web Catalog From Scratch (Example)

For illustration purposes, a sample web catalog set up is provided below.

## Create First Level Menu

A website that distributes beauty and skincare products to shops worldwide is to have the following sections in its main menu:

1. Health and Pharmacy
2. Beauty and Skincare
3. Fragrance
4. Baby and Child
5. Toiletries

These sections will serve as the first level of the storefront main menu. In the back-office, they will be called the root nodes.

To set up root content nodes in the back-office, we:

1. Navigate to **Marketing > Web Catalogs**.
2. Click **Create Web Catalog**
3. Name the catalog *Web Catalog 2017* and save it.
4. Click **Edit Content Tree**.
5. Name the first node *Web Catalog 2017*. Root nodes will be linked to it.
6. Fill in the SEO section.
7. Set the necessary restrictions.
8. Add a landing page in the content variants section that would be linked to the menu.
9. From this node, create the first level menu by clicking **Create Content Node**.
10. Name it *Health and Pharmacy*.
11. Fill in the SEO section.
12. Set the necessary restrictions (or inherit parent restrictions).
13. Add a landing page linked to Health and Pharmacy.
14. Click **Save**.

This way, we create all the required first level menus.

#### NOTE
Make sure that you create first level nodes from Web Catalog 2017 in the nodes section on the left of the page.

![The details of the Web Catalog 2017](user/img/marketing/web_catalogs/use_case/Create1RootNode.png)

## Create Sub-level Menu

Once all first level nodes have been created, we can create the sub-menu nodes (second level menus) that would populate root nodes.

Each of the main menu sections will have the following second level menus:

1. Health and Pharmacy: Vitamins and Supplements, Lifestyle and Wellbeing, Women’s Health, Men’s Health, Baby and Child Health.
2. Beauty and Skincare: Makeup, Nails, Facial Skincare, Body Skincare, Hair, Fashion Accessories.
3. Fragrance: Perfume, Aftershave.
4. Baby and Child: Pregnancy and Maternity, Feeding, Bathing, and Changing.
5. Toiletries: Hair, Dental, Washing and Bathing.

To set up content nodes in the back-office:

1. Select the root node you are creating the sub-node for. In our case, it is *Health and Pharmacy*.
2. Click **Create Content Node**.
3. Name the second level menu *Vitamins and Supplements*. This will be linked to the root node.
4. Fill in the SEO section.
5. Set the necessary restrictions (or inherit parent restrictions).
6. Add a product collection to *Vitamins and Supplements*.

![View the Web Catalog 2017 content tree with the first and second level menus](user/img/marketing/web_catalogs/use_case/Create1SubMenuNode.png)

This way, we create all the required second level menus.

Each of such levels can be populated with more levels, or nodes, if necessary, and each node can have a page ([system](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-system-page), [landing](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-landing-page), [product](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-product-page)), a [product collection](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-product-collection), or a [category](edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-category) mapped into it.

#### NOTE
You can drag the existing content nodes to a different position within the content tree on the left of the page, as illustrated below:

![Dragging the existing content nodes to a different position within the content tree](user/img/marketing/web_catalogs/DragDropNode.png)

Once the catalog is enabled ([globally](../../system/configuration/system/websites/global-routing.md#user-guide-marketing-web-catalog-enable-globally) or [per website](../../system/websites/web-configuration/general-sys-config/websites/website-routing.md#user-guide-marketing-web-catalog-enable-per-website)), you will be able to see it in the storefront.

![Illustrating all content nodes created under the Web Catalog 2017 in the storefront](user/img/marketing/web_catalogs/use_case/NodesFrontStore.gif)

**Related Articles**

* [Web Catalogs](index.md#user-guide-web-catalog)
* [Create a Web Catalog](create.md#user-guide-web-catalog-create)
* [Edit a Web Catalog Content Tree](edit-content-tree/index.md#user-guide-web-catalog-edit-content-tree)
* [Enable a Web Catalog  Globally](../../system/configuration/system/websites/global-routing.md#user-guide-marketing-web-catalog-enable-globally) and [per Website](../../system/websites/web-configuration/general-sys-config/websites/website-routing.md#user-guide-marketing-web-catalog-enable-per-website).
* [Customize Web Catalog Contents for Localization, Customer or Customer Group](edit-content-tree/visibility.md#user-guide-marketing-web-catalog-customize)
* [Use Web Catalog Nodes as Root Nodes (Example)](web-catalog-nav-tool-usecase.md#user-guide-web-catalog-navigation-tool)

<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
