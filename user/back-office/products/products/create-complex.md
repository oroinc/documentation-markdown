<a id="products-products-create-config-product"></a>

# Create a Configurable Product

#### HINT
This section is part of the [Product Management](../../../concept-guides/product-management/index.md#concept-guides-product-management) topic that provides the general understanding of the product concept in OroCommerce.

See a short demo on <a href="https://academy.oroinc.com/media-library/create-configurable-products" target="_blank">how to create a configurable product</a>, or keep reading the step-by-step guidance below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/V3yhUw-Tc_U" frameborder="0" allowfullscreen></iframe>

## Checklist

Prior to creating a [configurable product](../../../glossary.md#term-Configurable-Product), ensure that you have performed the following steps:

1. Created [attributes](../product-attributes/index.md#products-product-attributes-create).

   A configurable attribute is one of the product attributes that are used to distinguish [product variants](index.md#doc-products-actions-create) of the same configurable product. There should be at least one configurable attribute specified for the configurable product in order to enable a customer to select product variants.
2. Created a [product family](../product-families/create.md#product-product-families-create).

   As a configurable product and all of its variants share the same set of attributes, they should share the product family as well.
3. Created [product variants (simple products)](create-simple.md#products-products-create-simple-product).

   A configurable product may group several simple products or configurable product variants whose information mostly overlaps except for several product attributes. It means that you have to create a simple product for each variant that you need to add to the configurable product.

   #### NOTE
   Make sure the configurable product you are creating has the same product unit as its product variants.

   #### NOTE
   Product variants for configurable products in the storefront are displayed only when either customer users are logged in or [guest shopping lists](../../../concept-guides/guests/index.md#sys-conf-commerce-guest) are enabled in the system configuration.

## Flow

To add a new configurable product and make it available in the master catalog (for internal product management) and for purchase in the storefront:

1. Navigate to **Products > Products** using the main menu.
2. Click **Create Product**.
3. From the **Type** list, select *Configurable* to enable product variants.
4. Select the [product family](../product-families/index.md#products-product-families) to define the product options and details that will be filled in the following steps.

   #### NOTE
   Ensure that the product attributes that store product variant options are created and included in the product’s product family.
5. Place the product under the necessary category in the master catalog by clicking on the category. Use the search to filter the list of categories.
6. Click **Continue**. The product details page appears.
7. In the **General** section, provide the following information:

   | Field                       | Description                                                                                                                                                                                                                                                                                                                                                                                          |
   |-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Owner**                   | Limits the list of users who can manage the product.                                                                                                                                                                                                                                                                                                                                                 |
   | **SKU**                     | Enter the product SKU number. The field is mandatory.                                                                                                                                                                                                                                                                                                                                                |
   | **Name**                    | Enter the name of the product. The field is mandatory.                                                                                                                                                                                                                                                                                                                                               |
   | **Configurable Attributes** | Define the configurable attributes that distinguish product variants by selecting the check boxes next to them.<br/><br/>#### NOTE<br/>A configurable product should contain at least one configurable attribute of select or boolean type.<br/><br/>![A sample of a configurable product that has one configurable attribute of a select type](user/img/products/products/ConfigProducVariants.png) |
   | **Status**                  | Select the product status (e.g., *Enabled*/*Disabled*). When disabled, the product is not included in the catalog and is considered to be a draft. The field is mandatory.                                                                                                                                                                                                                           |
   | **URL Slug**                | Enter a URL slug that is used to build a human-readable URL for the product page in the storefront. If left blank, the slug will be autogenerated.                                                                                                                                                                                                                                                   |
   | **Is Featured**             | Select whether the product is featured. The field is mandatory.                                                                                                                                                                                                                                                                                                                                      |
   | **New Arrival**             | Select whether the product is a new arrival. When set to *Yes*, the product is highlighted in the storefront. The field is mandatory.                                                                                                                                                                                                                                                                |
   | **Brand**                   | Choose [the product brand](../product-brands/index.md#user-guide-product-brands), if available. Click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to select the brand from the full list.                                                                                                                                                                                                    |

   Also, specify the value of your configurable attributes and define any other custom attributes if required.
8. In the **Short Description** section, provide a short but meaningful default description that best positions the product for your target audience and will appear in the catalog listing. Move from tab to tab to localize the description by setting the required fallback option. From the dropdown, you can select whether to fall back to the default value, parent localization, or a custom value. When selecting the custom value, provide the localized version of the short description in the text field.
   > ![Localization fallback option for the short description of the configurable product](user/img/products/products/localize_short_descr_config_product.png)
9. In the **Description** section, provide a long default description of the product that will appear on the product view page. Move from tab to tab to localize the description by setting the required fallback option. From the dropdown, you can select whether to fall back to the default value, parent localization, or a custom value. When selecting the custom value, provide the localized version of the long description in the WYSIWYG field. For more details on WYSIWYG management, see the [WYSIWYG Editor](../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) topic.
10. In the **Image** section, add a new image to the product by clicking **+Add Image** and then **Choose Image**. You can either upload a new image or select the required one from the list of available [digital assets](../../marketing/digital-assets/index.md#digital-assets) records.

> Then, select whether to show the image as *main* (the image is used in the product details view), *listing* (the image is shown in the catalog listing), or *additional* (additional product pictures). All three categories can be selected at the same time. To remove an image, click <i class="fas fa-times" aria-hidden="true"></i> next to it.
1. In the **SEO** section, specify the required attributes:

> | Field                | Description                                                                                                                                                                                              |
> |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | **Meta Keywords**    | Enter meta keywords for the product. A meta keyword is a specific type of a meta tag that appears in the HTML code of a web page and helps search engines to understand what the topic of the page is.   |
> | **Meta Title**       | Enter a meta title for the product. A meta title is what is seen by search engine users and helps a search engine to index the page.                                                                     |
> | **Meta Description** | Enter a meta description for the product. A meta description summarizes the page content. Search engines show a meta description in search results when the searched phrase is found in the description. |

> And any other custom attributes if defined.
1. In the **Design** section, select the [page template](page-templates.md#user-guide-page-templates) from the list.

> ![The list of available page templates in the dropdown of the Page Template field](user/img/products/products/SimpleProductDesign.png)
1. In the **Product Variants** section, select the configurable product variants by ticking the **Is Variant** check box next to the product.

> ![Selecting the configurable product variants](user/img/products/products/SampleProductVariantsForConfigProduct.png)

> #### NOTE
> Make sure the configurable product has the same product unit as its product variants.
1. Review translation rules for a product name, URL slug, description, and short description.

> To enter a translation manually, click <i class="fas fa-language" aria-hidden="true"></i>, clear the **Use <parent translation>** check box next to the required language, and provide your version of the translation.

> ![Provide the relevant translation](user/img/products/products/ProductsCreateTranslation.png)
1. Click **Save** to save your configurable product.

Once the core product information is saved, you may add related products and up-sell products to display them in the **Related Items** section in the product details in the back-office, and in the **Related Products** and **Up-sell Products** blocks next to the product details in the storefront. See the [Add Related Items](create-simple.md#products-related-items) for more details.

## Create a Sample Configurable Product

The sample flow below shows all the steps required for the creation of a configurable product.

*Product: Red and green hats, sizes S and M.*

**Step 1. Create Attributes.**

1. Navigate to **Products > Product Attributes** in the main menu.
2. Click **Create Attribute** on the top right.

   We will create two attributes, one after another: ‘hatcolor’ and ‘hatsize’.
3. Select the type of an attribute.

   Currently, *Select* and *Boolean* types are available for configurable attributes. We will use *Select* for both attributes.
4. Fill in the required information and add the necessary options for the attributes by clicking **+Add**.

   For ‘hatcolor’, attribute options will be ‘Red’ and ‘Green’.
   ![Create the HatColor product attribute with the red and green options](user/img/products/products/SampleHatColor.png)

   For ‘hatsize’, attribute options will be ‘S’ and ‘M’.
   ![Create the HatSize product attribute with the s and m options](user/img/products/products/SampleHatSize.png)
5. Click **Save** to save the attributes.

![Newly created attributes are displayed in the list of all product attributes](user/img/products/products/SampleHatColorSizeGrid.png)

**Step 2. Create a Product Family.**

1. Navigate to **Products > Product Families** in the main menu.
2. Click **Create Product Family** in the top right corner.
3. Fill in the required information and add attributes ‘HatColor’ and ‘HatSize’ to the attribute group by clicking **+Add**.

   Each attribute must have a separate group in our case.
   ![Add new product attributes to separate groups when creating a product family](user/img/products/products/SampleProductFamily.png)
4. Click **Save** to save the product family.

**Step 3. Create Configurable Product Variants.**

We now need to create one configurable product variant (simple product) per each variant that we would like to have available in the configurable product. Since we have two attributes, ‘HatSize’ and ‘HatColor’, and each attribute has two options (‘S’/’M’ for the first and ‘Red’/’Green’ for the second), we need to create four simple products.

1. Navigate to **Products > Products** in the main menu.
2. Click **Create Product** in the top right corner.
3. Set the product type to *Simple*, select the ‘HATS’ product family.
4. Fill in the required information and add the attributes required for this particular product.
   ![Illustrate a simple product creation based on the provided parameters](user/img/products/products/SampleSimpleProduct1.png)
5. Click **Save**.

Perform step 3 for all four simple products.

#### NOTE
Make sure that all your simple products are *enabled*.

![Display all created simple products in the products' grid](user/img/products/products/SampleSimpleProductsGrid.png)

**Step 4. Create a Configurable Product.**

1. Navigate to **Products > Products** in the main menu.
2. Click **Create Product**.
3. Set the product type to *Configurable*.
4. Select the category.

   #### NOTE
   Choosing category is mandatory at this stage, as it determines whether the product is available on the website.
5. Choose the ‘Hats’ product family.
   ![Illustrate a configurable product creation based on the provided parameters](user/img/products/products/SampleCreateConfigProduct.png)
6. Add ‘HatSize’ and ‘HatColor’ attributes to the product.
7. Fill in the required information and add the created product variants for this configurable product.

   #### NOTE
   You might want to save the product at this point to make sure that product variants are available in the **Product Variants** section of the product you are creating.

   ![Display the product variants available for the configurable product in the Product Variants section](user/img/products/products/SampleProductVariantsForConfigProduct.png)
8. Click **Save**.
   ![Display all created simple and configurable products in the products' grid](user/img/products/products/SampleConfigSimpleGrid1.png)

The product should now be available on the website in the category we have previously assigned it to.

<!-- stop_product_create_configurable -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
