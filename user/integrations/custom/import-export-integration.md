<a id="custom-integrations-import-export"></a>

# Import and Export

Oro applications have import/export capabilities for their most critical features, specifically designed for daily operations that generate high amounts of data. These capabilities facilitate the seamless transfer of data into and out of the system, enabling users to efficiently manage their data and streamline their workflows. With these functionalities in place, users can easily import data into Oro applications from external sources or export data from Oro applications to other systems for further analysis or manipulation.

![Illustration of how import works in Oro](user/img/integrations/oro_server.png)

Out of the box, import and export is enabled for the following types of data:

| Import   | Translation, FieldConfigModel, Contact, Product, ProductImage, RelatedProduct, Category, Customer, CustomerUser, CustomerAddress, CustomerUserAddress, TrackingData, Account, Synonym, ProductPrice, PriceAttributeProductPrice, Lead, Opportunity, B2bCustomer, TaxRule, Tax, InventoryLevel, Coupon, User   |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Export   | User, Translation, Contact, Product, RelatedProduct, Category, Customer, CustomerUser, CustomerAddress, CustomerUserAddress, Account, Synonym, ProductPrice, PriceAttributeProductPrice, Lead, Opportunity, B2bCustomer, TaxRule, Tax, SearchResultHistory, InventoryLevel, Coupon                            |

[OroImportExportBundle](../../../bundles/platform/ImportExportBundle/index.md#bundle-docs-platform-import-export-bundle) provides a range of built-in readers and writers that support various file formats and data sources. Readers include support for CSV and XLSx file formats, and data retrieval from Doctrine entities. Writers include support for CSV and XLSx file formats, Doctrine entities, and direct writing to the database with the InsertFromSelectWriter. These pre-built components offer a solid foundation for various import and export scenarios, making it easier for users to work with their data.

**Related Topics**

* [OroImportExportBundle](../../../bundles/platform/ImportExportBundle/index.md#bundle-docs-platform-import-export-bundle)
* [Import/Export Developer Guide](../../../backend/integrations/import-export/index.md#dev-integrations-import-export)
* [Data Import Concept Guide](../../concept-guides/administration/data-import/index.md#concept-guide-data-import)
