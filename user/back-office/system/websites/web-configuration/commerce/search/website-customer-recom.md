<a id="website-configuration-commerce-search-customer-recommendation"></a>

# Configure Customer Recommendations Settings per Website

#### NOTE
The feature is only available in the Enterprise edition applications.

#### NOTE
You can also configure customer recommendation search settings [on the global level](../../../../configuration/commerce/search/customer-recommendations.md#system-configuration-commerce-search-customer-recommendation).

You can boost full-text search results based on the history of all registered customers that have interacted with your website. Such boost settings help provide customers with a better user experience, displaying the most relevant products based on customer actions (product views, product placement to a shopping list, product purchases) or total product revenue.

To configure the product full-text search boost settings based on the global purchase history, the total revenue, or the product data only per each specific website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> more actions menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Select **Commerce > Search > Customer Recommendations** in the menu to the left.

#### NOTE
For faster navigation between the configuration menu sections, use [Quick Search](../../../../configuration/quick-search.md#user-guide-system-configuration-quick-search).

![Customer recommendation search settings configured per website](user/img/system/websites/web_configuration/customer-recommendations-website.png)
1. Configure the required boost setting to promote either the most viewed, purchased, or profitable products to your customers.

## Customer Actions Boost

**Customer Actions Boost** considers the three factors when applying the search boost scheme:

* The number of registered customer users who have viewed the product;
* The number of registered customer users who have added the product to a shopping list;
* The number of registered customer users who have purchased the product.

To activate the boost, configure the following options:

* **Enable Customer Actions Boost** - select the option to enable the customer action boost functionality.
* **Product View Ratio** - set a ratio for the number of customer users who have viewed the product.
* **Added To Shopping List Ratio** - set a ratio for the number of customer users who have added the product to a shopping list.
* **Product Purchase Ratio** - set a ratio for the number of customer users who have purchased the product.
* **Score Multiplier Formula** - select the most appropriate formula to calculate the score multiplier that boosts specific products. See each formula’s description and detailed explanation in the [CustomerRecommendation bundle](../../../../../../../bundles/commerce/CustomerRecommendationBundle/index.md#bundles-commerce-customer-recommendation) documentation.

## Product Revenue Boost

Product revenue boost focuses on the most profitable products, boosting the ones that have generated the biggest revenue in total.

To activate the boost, configure the following options:

* **Enable Product Revenue Boost** - select the option to enable the product revenue boost functionality.
* **Product Revenue Multiplier** - set a multiplier for the product’s total revenue.
* **Score Multiplier Formula** - select the most appropriate formula to calculate the score multiplier that boosts specific products.

See each formula’s description and detailed explanation in the [CustomerRecommendation bundle](../../../../../../../bundles/commerce/CustomerRecommendationBundle/index.md#bundles-commerce-customer-recommendation) documentation.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
