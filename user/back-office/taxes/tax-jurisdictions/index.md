<a id="taxes-tax-jurisdiction"></a>

# Manage Tax Jurisdictions in the Back-Office

<!-- begin -->

#### HINT
This section is part of the [Tax Management](../../../concept-guides/taxes/index.md#concept-guide-taxes) concept guide that provides the general understanding of the tax configuration and management in OroCommerce.

[Tax Jurisdiction](../../../glossary.md#term-Tax-Jurisdiction) is a geographical address of the area that is governed by the same tax laws and regulations, and that requires a dedicated set of tax calculation rules in OroCommerce: the tax rates for taxable/tax-exempt types of customers and products.

The sections below provide guidance on managing tax jurisdictions and assigning dedicated tax rules for these tax jurisdictions.

## Create a Tax Jurisdiction

To create a new tax jurisdiction:

1. Navigate to **Taxes > Tax Jurisdictions** in the main menu.
2. Click **Create Tax Jurisdiction**.
3. Fill in **Code**, **Description**.
4. Select the country from the list.
5. Select the state from the list.
6. Type in the Zip code ranges that should be covered by this tax jurisdiction (click **+Add** to capture additional range).
   ![Fill the data for a new tax jurisdiction](user/img/taxes/tax_jurisdiction_fill.png)
7. Click **Save and Close**.

## Manage Tax Jurisdictions

To view all tax jurisdictions, navigate to **Taxes > Tax Jurisdictions** in the main menu.

![The page of all tax available tax jurisdictions](user/img/taxes/tax_jurisdiction_all.png)

#### NOTE
To handle a big volume of data, use the page switcher, increase *View Per Page* or use filters to narrow down the list to just the codes you need.

In the tax jurisdictions list, you will find the information about the code (unique identifier), detailed description, and the dates when the tax jurisdiction was created and updated.

Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> to open its details page, <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to edit, or  <i class="fas fa-trash-alt" aria-hidden="true"></i> to remove the tax jurisdiction.

### View Tax Jurisdiction Details

To view tax jurisdiction details:

1. Navigate to **Taxes > Tax Jurisdictions** in the main menu.
2. Find the line with the necessary tax jurisdiction and click on it to open its details page.
   ![View the tax jurisdiction details](user/img/taxes/tax_jurisdiction_details.png)

You can <i class="fa fa-edit fa-lg" aria-hidden="true"></i> edit or <i class="fas fa-trash-alt" aria-hidden="true"></i>  delete the tax jurisdiction by clicking the required button on the top right.

### Edit a Tax Jurisdiction

To edit the Tax Jurisdiction details:

1. Navigate to **Taxes > Tax Jurisdictions** in the main menu.
2. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the item and click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> to start editing its details.
3. Update the **Code**, **Description**, and the covered addresses including zip codes.
4. Click **Save and Close**.

## Link a Tax Jurisdiction to the Tax Rule

You can edit the association of the tax jurisdiction with other tax components when [editing the tax rule details](../tax-rules/index.md#tax-rules-edit) (see the respective topic for more information).

**Related Articles**

* [Taxes](../index.md#user-guide-taxes)
* [Tax Rates](../taxes/index.md#user-guide-taxes-tax-rates)
* [Tax Rules](../tax-rules/index.md#tax-rules)
* [Customer Tax Codes](../customer-tax-codes/index.md#user-guide-taxes-customer-tax-codes)
* [Product Tax Codes](../product-tax-codes/index.md#taxes-product-tax-code)

<!-- finish -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
