<a id="user-guide-master-catalog"></a>

<a id="user-guide-products-master-catalog"></a>

# Manage Master Catalog in the Back-Office

#### HINT
This section is part of the [Master Catalog](../../../concept-guides/master-catalog/index.md#concept-guide-master-catalog) concept guide topic that provides a general understanding of the master catalog concept in OroCommerce.

[Master Catalog](../../../glossary.md#term-Master-Catalog) is a tree structure that organizes all the products of your store under corresponding categories. A category combines the products of the same type into groups and helps enforce the unified selling strategy by configuring a special set of product options, visibility, and SEO settings that best fit the resulting product family.

Once the categories are in place, you can:

* Add a category description and visuals.
* Link a corresponding product or a set of products to the selected category.
* Configure the default product options.
* Set up an activity type and a date for its implementation.
* Manage the category visibility.
* Configure SEO options.

To view the master catalog, navigate to **Products > Master Catalog** in the main menu.
The page displays all the categories created under this catalog.

<a id="user-guide-master-catalog-category-creation"></a>

## Create a Master Catalog Category

By default, there is only one master catalog in the OroCommerce application. To customize this catalog, you can add or delete a category, creating a group of products and linking it to the corresponding [web catalog](../../marketing/web-catalogs/index.md#user-guide-web-catalog).

To create a master catalog category:

1. Navigate to **Products > Master Catalog**.
2. Click **Create Category**.
3. In the **General** section, provide the following information:
   * **Title** — A meaningful name for the category. Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. Click the same icon again to return to the single-language view.
   * **URL Slug** — A web address generated automatically once the title of the category is defined. It is used to build a human-readable URL for the product page in the storefront. Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. Click the same icon again to return to the single-language view.
   * **Small Image** — An image used to represent the category in the storefront.

   ![Representation of a small image in the storefront](user/img/products/master_catalog/master_catalog_3.png)
   * **Large Image** — An image reserved for customization purposes.
4. In the **Short Description** section, provide a short but meaningful description of the category you are creating as a default value. Move from tab to tab to localize the description by setting the required fallback option. You can select whether to fall back to the default value, parent localization, or a custom value from the dropdown. When selecting the custom value, provide the localized version of the short description in the text field.
   > ![Localization fallback option for the short description of the master catalog](user/img/products/master_catalog/localize_short_descriptions_category.png)
5. In the **Long Description** section, provide a long default description of the category. Move from tab to tab to localize the description by setting the required fallback option. You can select whether to fall back to the default value, parent localization, or a custom value from the dropdown. When selecting the custom value, provide the localized version of the long description in the WYSIWYG field. For more details on WYSIWYG management, see the [WYSIWYG Editor](../../../concept-guides/content-management/wysiwyg.md#getting-started-wysiwyg-editor-field) topic.
6. In the **Products** section, select the items for the category you are creating. Use available filters to narrow your search and speed up the selection of the necessary product items. Each product you select can have a sort order associated with it that will define the default order in which the product will appear in the storefront. Be aware that for the sort order, 0 is the highest priority, and you can input any positive decimal number. Empty values will be sorted last.

   #### HINT
   The feature is available starting from OroCommerce v5.0.7. To check which application version you are running, see the [system information](../../system/system-information/index.md#system-information).

<a id="master-catalog-inventory"></a>
1. In the **Default Product Options** section, configure the following settings:
   ![The default product options details page](user/img/products/master_catalog/catalog_product_options.png)

   | Field                | Description                                                                                                                                                                                                                                                                                   |
   |----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Unit Of Quantity** | A product unit that is shown by default in the product details page in the storefront. Available options are *each*, *hour*, *item*, *kilogram*, *piece*, *set*, and *Parent Category*. The latter refers to the same product quantity unit configured for the corresponding parent category. |
   | **Precision**        | An acceptable value (number of digits after the decimal point) for the quantity that a user may order or add to the shopping list. Items and sets are usually whole numbers, and units like kilograms may get precision of 2 to allow buying a custom volume (e.g., 0.5 kg).                  |

> | Field                         | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
> |-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | **Inventory Status**          | This setting enables you to define and modify status information for the stock of the product.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
> | **Managed Inventory**         | This setting defines the method for [inventory](../../inventory/index.md#user-guide-inventory) management. With *Use category defaults*, the product’s **Manage Inventory** inherits the setting selected for the product’s parent category. With *Use system config*, the product uses the system configuration setting. Selecting *Yes* enables interactive updates based on the product inventory information from the **Inventory > Warehouses** section. Selecting *No* disables connection to the inventory, and uses the static **Inventory Status** value. |
> | **Highlight Low Inventory**   | This option defines if low inventory for products is displayed in the storefront.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
> | **Inventory Threshold**       | A minimum quantity of the product treated as In stock. When a product quantity drops below this value, the product inventory status becomes Out Of Stock.                                                                                                                                                                                                                                                                                                                                                                                                          |
> | **Low Inventory Threshold**   | The minimum stock level defined for the product. Reaching the defined level will trigger a warning message to the buyer in the storefront.                                                                                                                                                                                                                                                                                                                                                                                                                         |
> | **Backorders**                | A flag that indicates whether OroCommerce accepts backorders (EE feature). When set to *Yes*, buyers and salespeople can order products in quantities not currently available in the warehouses. The remaining portion of the order will be sustained until the product is back in stock.                                                                                                                                                                                                                                                                          |
> | **Decrement Inventory**       | A flag that indicates whether OroCommerce decrements inventory upon order. A product quantity can become negative when both **Decrement Inventory** and **Backorders** are enabled.                                                                                                                                                                                                                                                                                                                                                                                |
> | **Minimum Quantity to Order** | A minimum quantity that a buyer or salesperson can claim in the RFQ, customer order, quote, or a shopping list.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
> | **Maximum Quantity to Order** | A maximum quantity that a buyer or salesperson can claim in the RFQ, customer order, [quote](../../sales/quotes/index.md#user-guide-sales-quotes), or a shopping list.                                                                                                                                                                                                                                                                                                                                                                                             |
> | **Is Upcoming**               | This option informs a customer that the product of the selected category is not in stock currently but will be available later. When set to *Yes*, an additional **Availability Date** is displayed. To remove the upcoming products label, set the option to *No* or customize the required behavior in the [system configuration](../../system/configuration/commerce/inventory/product-options.md#upcoming-products-config).                                                                                                                                    |
> | **Availability Date**         | The date which indicates the exact date and time since the selected product will be available in stock.                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
1. The **Activity** section displays all the [activities](../../activities/index.md#user-guide-productivity-tools) available for the selected category, such as *call*, *task*, *email*, *note*, or *calendar event*. You can use filters to select any activity type and the date of its implementation.
2. In the **SEO** section, fill in the following details to help search engines show your master catalog content to the relevant audience.
   * **Meta Keywords** — Enter the meta keywords for the product. A meta keyword is a specific type of meta tag that appears in the HTML code of a web page and helps tell search engines what the topic of the page is.
   * **Meta Title** — Enter the meta title for the product. A meta title is what is seen by the search engine users and helps a search engine to index the page.
   * **Meta Description** — Enter the meta description for the product. A meta description summarizes a page’s content. Search engines show a meta description in search results if they see the searched phrase in the description.

   Click the <i class="fas fa-language" aria-hidden="true"></i> **Translations** icon to provide spelling for different languages. Click the <i class="fas fa-language" aria-hidden="true"></i> **Default Language** icon to return to the single-language view.
3. Click **Save** on the top right.

#### NOTE
You can drag the created category to a different position within the content tree on the left of the page, as illustrated below:

![Show what happens when you drag a category to a different position](user/img/products/master_catalog/master_catalog_8.png)

<a id="master-catalog-visibility"></a>

## Manage Category Visibility

In the **Visibility** section, you can set a visibility restriction for the master catalog category and the products assigned to this category. However, visibility per individual product is controlled by the [product visibility settings](../products/managing-product-visibility.md#products-product-visibility).

![View the global visibility settings for products and categories under the system configuration page](user/img/products/master_catalog/category-visibility.png)

Click the necessary tab to configure the visibility of the selected category.

#### IMPORTANT
You can define system-wide category visibility for existing customers. This setting applies only whenever a category visibility configuration is set to **Config**. These settings apply [globally](../../system/configuration/commerce/customer/visibility.md#user-guide-customers-configuration-visibility) and can be toggled under **System > Configuration > Commerce > Customer > Visibility**.

![View the global visibility settings for products and categories under the system configuration page](user/img/products/master_catalog/ConfigVisibilityOptions.png)

### Category Visibility to All

This setting controls the default visibility for the selected category and applies to all customers and customer groups unless otherwise configured. The available options include:

* *Parent Category* – Inherits configuration from the parent master catalog category. It means that the current category visibility settings equal the value defined in the **Category Visibility to All** field of the parent master catalog category. This option is available only for non-root categories.
* *Config* – Inherits settings from the [global system configuration](../../system/configuration/commerce/customer/visibility.md#user-guide-customers-configuration-visibility).
* *Hidden* – The category is hidden from the storefront for all customers.
* *Visible* – The category is visible to all customers in the storefront.

![View the category visibility settings applied to all customers](user/img/products/master_catalog/category-visibility-to-all.png)

### Category Visibility to Customer Groups

The setting controls if the category is shown to the customers who are members of a particular customer group (wholesalers, retailers, VIP customers, or guests, etc). You can configure specific settings for these groups based on their relationship with your business. Use one of the following options:

* *Visibility to All* – Inherits the default category visibility configuration, meaning it matches the settings defined under the **Category Visibility to All** section for this category. By default, this setting is pre-populated for any new customer group.
* *Parent Category* – Inherits configuration from the parent master catalog category. It means that the current category visibility settings equal the value defined in the **Category Visibility to Customer Groups** field of the parent master catalog category. This option is available only for non-root categories.
* *Hidden* – The category is hidden from the storefront for the selected customer group.
* *Visible* – The category is visible to the selected customer group in the storefront.

![View the category visibility settings applied to customers groups](user/img/products/master_catalog/category-visibility-to-customer-groups.png)

### Category Visibility to Customers

The setting controls if the category is shown to individual customers or businesses (Customer A, Customer B, etc). For instance, if a category is only available to selected customers, you can hide it from others. Use one of the following options:

* *Customer Group* – Inherits the category visibility configuration from the customer group to which the selected customer is assigned, meaning it matches the settings defined under the **Category Visibility to Customer Groups** section for this category. By default, this setting is pre-populated for any new customer.
* *Visibility to All* – Inherits the default category visibility configuration, meaning it matches the settings defined under the **Category Visibility to All** section for this category.
* *Parent Category* – Inherits configuration from the parent master catalog category. It means that the current category visibility settings equal the value defined in the **Category Visibility to Customers** field of the parent master catalog category. This option is available only for non-root categories.
* *Hidden* – The category is hidden from the storefront for the selected customer.
* *Visible* – The category is visible to the selected customer in the storefront.

![View the category visibility settings applied to customers](user/img/products/master_catalog/category-visibility-to-customers.png)

### Category Visibility Priorities

* **System-wide Category Visibility**: This is the global category visibility setting that applies across the entire system whenever the category visibility configuration is set to **Config**.
* **Parent Category Visibility**: Inherits settings from the parent category unless specifically overridden by a subcategory or product visibility.
* **Category Visibility to All**: Controls the visibility of the product’s category and overrides the parent category visibility.
* **Customer Group Visibility**: Overrides the default category visibility. If a category is visible to a customer group, it applies to all customers in that group.
* **Customer Visibility**: Overrides visibility for a customer group. If a category is set to be visible per individual customers, it remains visible to these customers even if visibility for a customer group to which the customer is assigned is set to be hidden.

## Create a Master Catalog Subcategory

Once you have created the main master catalog category, proceed to its subcategory creation.

To distribute the product items into more specific and detailed product families, create a master catalog subcategory:

1. Select a category to link a new subcategory to.
2. Click **Create Subcategory**.
   ![Click create subcategory](user/img/products/master_catalog/master_catalog_9.png)
3. Provide the information following the guide in the [Create a Master Catalog Category](#user-guide-master-catalog-category-creation) section.

#### NOTE
Please note that you cannot link one product item to both a category and a subcategory.

## Link the Master Catalog Category to a Web Catalog

When the master catalog category is created, you need to link it to a [web catalog](../../marketing/web-catalogs/index.md#user-guide-web-catalog) for the customer to view it from the storefront.

Proceed with the following steps:

1. Create a web catalog as described in the [Create a Web Catalog](../../marketing/web-catalogs/create.md#user-guide-web-catalog-create) section.
2. Add the master catalog category following the guide illustrated in the [Add a Category (Web Catalog Content)](../../marketing/web-catalogs/edit-content-tree/content-variants.md#user-guide-marketing-web-catalog-content-variant-category) section.

#### IMPORTANT
As a follow-up, see the [Configure Product and Category Visibility to Customers](../../system/configuration/commerce/customer/visibility.md#user-guide-customers-configuration-visibility) topic for the details on how to control the default visibility settings for master catalog categories and subcategories through the back-office.

**Related Articles**

* [Configure Product Visibility to Customers](../../system/configuration/commerce/customer/visibility.md#user-guide-customers-configuration-visibility)
* [Web Catalog](../../marketing/web-catalogs/index.md#user-guide-web-catalog)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
