<a id="bundle-docs-extensions-dpd"></a>

# OroDPDBundle

<a href="https://github.com/oroinc/OroDpdBundle" target="_blank">OroDPDBundle</a> adds the <a href="https://www.dpd.com/" target="_blank">DPD</a> shipping service <a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/IntegrationBundle" target="_blank">integration</a> to Oro applications and helps admin users to enable and configure DPD <a href="https://github.com/oroinc/orocommerce/tree/master/src/Oro/Bundle/ShippingBundle" target="_blank">shipping methods</a> for invoices, quotes, and customer orders. The bundle also adds the <a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/ActionBundle" target="_blank">operation button</a> for admin users to the order view pages to provide order shipping data and send the package pick-up request to the DPD service.

The DPD shipping provides functionality to:

* Implement the *DPD Classic* shipping method type.
* Use *flat-rate* or *table-rate* shipping cost calculation.
* CSV import/export for *table-rates*.
* API based parcel pick-up day/time calculation and validation.
* API based shipping address validation.
* API based PDF label retrieval for orders.

Configuration data of *Shipping Origin* is used in the DPDBundle as the parcel pick-up address. This address is used to calculate the locale specific available pick-up days and is configured under **System > Configuration > Commerce > Shipping > Shipping Origin** in the back-office.

For more information, see the [Configure DPD Shipping Integration in the Back-Office](../../../user/back-office/system/integrations/shipping-integration/dpd.md#doc-integrations-dpd) topic in the user guide.

#### BUSINESS TIP
# Business Tip

Manufacturing companies are gradually embracing digital technologies. Discover how eCommerce can help you achieve <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a>.

<!-- Frontend -->
