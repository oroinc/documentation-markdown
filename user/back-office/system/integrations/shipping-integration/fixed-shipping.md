<a id="doc-integration-fixed-shipping-cost"></a>

# Configure Fixed Product Shipping Cost Integration in the Back-Office

#### HINT
This section is part of the [Shipping Configuration](../../../../concept-guides/shipping-configuration/index.md#admin-guide-shipping) topic that provides a general understanding of the shipping concept in OroCommerce.

#### HINT
Fixed Product Shipping Cost is available starting from v4.2.11. To check which application version you are running, see the [system information](../../system-information/index.md#system-information).

In OroCommerce, you can set a fixed shipping cost to a product or a group of products and configure the required rules and surcharges for them. To enable this shipping method, first, create a Fixed Product Cost shipping integration to expose it as a shipping method for the storefront.

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-shipping-integrations" target="_blank">how to set up a shipping integration in OroCommerce</a> or keep reading the step-by-step guidance below.

> <iframe width="560" height="315" src="https://www.youtube.com/embed/ileKXVTG6B8" frameborder="0" allowfullscreen></iframe>

To enable fixed product shipping cost integration:

1. Navigate to the **Manage Integrations** page by clicking **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** and select Flat Rate Shipping as integration type:
   ![image](user/img/system/integrations/fixed-product-cost/fixed-product-cost-integration.png)
3. Type in the integration name and label (e.g., Fixed Product Shipping). Add label translations, if necessary.
4. Set status to **Active** to enable the integration.
5. Click **Save**.

Next, set up a shipping rule via the [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules) page to enable and configure this shipping method.

#### HINT
Fixed Product Shipping Cost Method and its configuration through [a shipping rule](../../shipping-rules/index.md#shipping-rule-fixed-product-shipping-cost) can work in conjunction with the values defined in the [Shipping Cost price attribute](../../../products/products/manage/view.md#products-shipping-options-price-attribute). For example, if the shipping cost for a product is set to $2.70 and the surcharge configured for the Fixed Shipping Cost shipping method is $3, then the shipping charge at checkout will equate to $5.70.

![Illustration of how shipping cost set for the price attribute works on combination with the surcharge defined in the fixed product shipping cost integration](user/img/products/price_attributes/shipping-cost-price-attribute-with-integration.png)

**Related Topics**

* [Shipping Configuration Concept Guide](../../../../concept-guides/shipping-configuration/index.md#admin-guide-shipping)
* [System Shipping Configuration](../../configuration/commerce/shipping/index.md#configuration-guide-commerce-configuration-shipping)
* [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules)
* [Shipping Cost Price Attribute](../../../products/products/manage/view.md#products-shipping-options-price-attribute)
