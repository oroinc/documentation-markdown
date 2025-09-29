<a id="sys-integrations-manage-integrations-ups-flat-rate"></a>

<a id="user-guide-shipping-configuration-common-details"></a>

# Configure Shipping Method Integration in the Back-Office

#### HINT
This section is part of the [Shipping Configuration](../../../../concept-guides/shipping-configuration/index.md#admin-guide-shipping) topic that provides a general understanding of the shipping concept in OroCommerce.

## Create an Integration with a Shipping Service Provider

Out-of-the-box, you can create an integration with the following third-party providers (click the links for detailed guidance) to offer their shipping services for the quotes and orders placed using OroCommerce.

* [Flat Rate](flat-rate.md#doc-integrations-flat-rate)
* [Fixed Product Shipping Cost](fixed-shipping.md#doc-integration-fixed-shipping-cost)
* [UPS](ups.md#doc-integrations-ups)
* [FedEx](fedex.md#doc-integrations-fedex)
* [DPD](dpd.md#doc-integrations-dpd)

#### HINT
Check out <a href="https://extensions.oroinc.com/orocommerce/" target="_blank">OroCommerce's Extensions Store</a> to download other shipping services that you can pair with your OroCommerce applications.

## Delete a Shipping Integration

This section describes the steps that are necessary to delete integration with the shipping provider and disable shipping methods they offer in OroCommerce orders and quotes.

To delete an integration and related shipping methods:

1. Navigate to the **Manage Integrations** page by clicking **System > Integrations > Manage Integrations** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu on the right side of the line with the necessary integration and click <i class="fas fa-trash-alt" aria-hidden="true"></i>.

   The confirmation box is shown.

   If any shipping rule depends on the integration that is being deleted, the affected shipping methods in those shipping rules will be disabled. The shipping rule might also be disabled if none of its shipping methods remain enabled.
3. If necessary, review the shipping rules using the link in the confirmation box.

   #### NOTE
   The shipping rules open in a new tab in your browser.
4. Once you are ready to delete the integration, click **Delete**.

The shipping methods created due to this integration are no longer usable in OroCommerce and cannot be enabled in the shipping rule.

**Related Topics**

* [Shipping Configuration Concept Guide](../../../../concept-guides/shipping-configuration/index.md#admin-guide-shipping)
* [System Shipping Configuration](../../configuration/commerce/shipping/index.md#configuration-guide-commerce-configuration-shipping)
* [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
