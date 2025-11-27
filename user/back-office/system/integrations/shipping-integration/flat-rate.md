<a id="doc-integrations-flat-rate"></a>

# Configure Flat Rate Shipping Integration in the Back-Office

#### HINT
This section is part of the [Shipping Configuration](../../../../concept-guides/administration/shipping-configuration/index.md#admin-guide-shipping) topic that provides a general understanding of the shipping concept in OroCommerce.

Flat Rate shipping integration section describes the steps that are necessary to expose [flat rate](../../../../glossary.md#term-Flat-Rate) shipping as a shipping method in OroCommerce orders and quotes.

#### NOTE
See a short demo on <a href="https://academy.oroinc.com/media-library/create-shipping-integrations" target="_blank">how to set up a shipping integration in OroCommerce</a> or keep reading the step-by-step guidance below.

> <iframe width="560" height="315" src="https://www.youtube.com/embed/ileKXVTG6B8" frameborder="0" allowfullscreen></iframe>

To enable flat rate shipping:

1. Navigate to the **Manage Integrations** page by clicking **System > Integrations > Manage Integrations** in the main menu.
2. Click **Create Integration** and select Flat Rate Shipping as integration type:
   ![image](user/img/system/integrations/CreateFlatRate.png)
3. Type in the integration name and label (e.g., Flat Rate). Add label translations, if necessary.
4. Set status to **Active** to enable the integration.
5. Click **Save**.

Next, set up a shipping rule via the [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules) page to enable this shipping method for all or some customer orders.

Once the shipping method is added to the shipping rule, provide the information that configures the shipping fee components and the method to calculate it following the [Configure a Shipping Method in a Shipping Rule](../../shipping-rules/index.md#doc-shipping-rules-shipping-methods-detailed) topic.

**Related Topics**

* [Shipping Configuration Concept Guide](../../../../concept-guides/administration/shipping-configuration/index.md#admin-guide-shipping)
* [System Shipping Configuration](../../configuration/commerce/shipping/index.md#configuration-guide-commerce-configuration-shipping)
* [Shipping Rules Configuration](../../shipping-rules/index.md#sys-shipping-rules)
