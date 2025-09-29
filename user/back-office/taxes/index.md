<!-- meta: description = Tax rules configuration and management guides for the OroCommerce back-office users -->

<a id="user-guide-taxes"></a>

# Manage Taxes in the Back-Office

#### HINT
This section is part of the [Tax Management](../../concept-guides/taxes/index.md#concept-guide-taxes) concept guide that provides a general understanding of the tax configuration and management in OroCommerce.

Tax rules help OroCommerce find the correct tax rate that should be used for the products listed in the purchase order by matching the product tax code that indicates:

* Tax status of the product
* Customer tax code that indicates the tax status of the buying company
* Tax jurisdiction where the tax is due

OroCommerce supports a tax exemption mechanism: you can set a zero tax rate for some customers and/or products.

A [tax rule](tax-rules/index.md#tax-rules) binds the following items:

* [Customer tax code](customer-tax-codes/index.md#user-guide-taxes-customer-tax-codes) - a label for a customer or customer group that follows similar taxation rules in at least one tax jurisdiction.
* [Product tax code](product-tax-codes/index.md#taxes-product-tax-code) - a label for a group of products that have similar taxation rules in at least one tax jurisdiction.
* [Tax jurisdiction](tax-jurisdictions/index.md#taxes-tax-jurisdiction) - an address, usually a state in a country that has defined taxation policies that determine when and how the company should pay its sales or VAT tax, and what rates should be used, depending on the tax status of the products you sell and the parties you sell to.
* [Tax rate](taxes/index.md#user-guide-taxes-tax-rates) - the percentage of the sales income that should be paid as a tax in the particular tax jurisdiction for a certain type of products sold to a group of customers with the same tax status.

![The general page of all tax rates](user/img/taxes/all_tax_rules.png)

## Taxation Configuration

OroCommerce groups taxation configuration options into the following categories that should be customized in the [global system configuration](../system/configuration/commerce/taxation/index.md#configuration-guide-commerce-configuration-taxation) or [per organization](../system/user-management/organizations/org-configuration/commerce/taxation/tax-calculation.md#user-guide-taxes-org-promotions):

* [Tax Calculation](../system/configuration/commerce/taxation/tax-calculation.md#user-guide-taxes-tax-configuration)
* [US Sales Tax for Digital Products](../system/configuration/commerce/taxation/us-sales-tax.md#user-guide-taxes-us)
* [EU VAT Tax for Digital Products](../system/configuration/commerce/taxation/eu-vat-tax.md#user-guide-taxes-eu)

<a id="tax-rule-prerequisites"></a>

## Tax Rules Creation Prerequisites

Before setting up a tax rule, make sure to complete the following actions:

1. [Create a customer tax code](customer-tax-codes/create.md#user-guide-taxes-customer-tax-codes-create)

Create a customer tax code and apply it to a certain customer or a customer group who has fixed tax rates.

1. [Create a product tax code](product-tax-codes/create.md#taxes-product-tax-code-create)

Create a product tax code and apply it to the required products with fixed tax rates so that only the products that are subject to be taxed are taxed during a checkout.

1. [Create a tax jurisdiction](tax-jurisdictions/create.md#taxes-tax-jurisdiction-create)

Once you have created both customer and product tax codes and assigned them to the required customers and products, you need to create a tax jurisdiction (country, state, and a range of zip codes) with defined taxation policies to determine where and how the company should pay their sales or VAT tax. A tax jurisdiction specifies what rates should be used depending on the tax status of the products you sell and the customers you sell to.

1. [Create a tax rate](taxes/create.md#user-guide-taxes-tax-rates-create)

Create a tax rate(%) defined by the tax jurisdiction for the customers you are serving and the products you are selling. A tax rate determines the percentage of a sale or order that is required to be paid as a tax in a certain tax area (country or state).

1. [Create a tax rule](tax-rules/create.md#tax-rules-create)

Finally, create a tax rule that associates the customer tax code, the product tax code, and the tax jurisdiction with the tax rate or the tax exemption (zero rate).

#### NOTE
See the two short demos for the guidance on how to create tax rules.

<a href="https://academy.oroinc.com/media-library/create-tax-code-and-jurisdictions" target="_blank">Creating tax codes and jurisdictions in OroCommerce</a>

> <iframe width="560" height="315" src="https://www.youtube.com/embed/3Bra02GiKZE" frameborder="0" allowfullscreen></iframe>

<a href="https://academy.oroinc.com/media-library/create-tax-rules" target="_blank">Creating tax rules</a>

> <iframe width="560" height="315" src="https://www.youtube.com/embed/Ma0JOwn9VVs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Related Articles**

* [Customer Tax Codes](customer-tax-codes/index.md#user-guide-taxes-customer-tax-codes)
* [Product Tax Codes](product-tax-codes/index.md#taxes-product-tax-code)
* [Tax Jurisdictions](tax-jurisdictions/index.md#taxes-tax-jurisdiction)
* [Tax Rates](taxes/index.md#user-guide-taxes-tax-rates)
* [Tax Rules](tax-rules/index.md#tax-rules)

<!-- finish -->
