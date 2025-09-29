<a id="user-guide-marketing-promotions-coupons"></a>

# Manage Coupons in the Back-Office

#### HINT
This section is part of the [Promotion Management](../../../../concept-guides/promotions/index.md#concept-guides-promotion-management) topic that provides the general understanding of the promotions and coupons concept.

As a promotional tool, coupons can be generated and distributed to customers to be redeemed for a discount when purchasing goods online. In your Oro application, coupons are always linked to promotions, although they can be created separately and linked to a promotion when the need arises.

The following topics will explore how to create, generate, and manage coupons in your Oro application:

#### NOTE
You can check out <a href="https://academy.oroinc.com/media-library/how-to-create-coupons-and-link-them-to-promotions" target="_blank">how to create coupons and link them to promotions</a> in our media library.

<a id="user-guide-marketing-promotions-coupons-begin"></a>

## Before You Begin

As coupons are linked to promotions, make sure that [promotions](../promotions/index.md#user-guide-marketing-promotions) are enabled in your system. For more information on configuration of promotions, see the relevant [Configure Promotions](../../../system/configuration/commerce/sales/promotions-settings.md#sys-config-commerce-sales-promotions) topic, or refer to your administrator.

Enabling promotions allows you to perform the following actions with coupons:

1. See **Coupons** under **Marketing > Promotions > Coupons** in the main menu of the back-office.
2. View and add coupons to [orders](../../../sales/orders/index.md#user-guide-sales-orders) in the back-office.
3. Apply coupons in [shopping lists](../../../../storefront/account/shopping-lists/index.md#frontstore-guide-shopping-lists) and [checkout](../../../../storefront/orders/index.md#frontstore-guide-orders) in the storefront.

Coupons can be created manually or generated. Usually, you *create* coupons manually when you need a small number of them (e.g., 2), or *generate* coupons when you need many (e.g., 1000).

<a id="user-guide-marketing-promotions-coupons-create"></a>

## Create Coupons

To create a new coupon:

1. Navigate to **Marketing > Promotions > Coupons** in the main menu.
2. Click **Coupons Actions > Create Coupon** on the top right.
   ![The steps you need to perform to get to the coupon creation page](user/img/marketing/coupons/FindCoupon.png)
3. In the  **General** section, complete the following fields:
   ![Create a new coupon](user/img/marketing/coupons/CreateCoupon.png)
   * **Owner** — Select the business unit responsible for the coupon.
   * **Coupon Code** — Enter the coupon code. Code value should be numeric, alphabetic or both, and have no spaces. This field is mandatory.
   * **Promotion** — Select the promotion that the coupon should relate to, or click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to load the list of promotions to choose from. Please note that only promotions with the **Triggered by** option set to *Coupons and Conditions* will be displayed on the list of available promotions. If there are no promotions to link the coupon to, they can be created and added to the coupon later.
   * **Enabled** — Enable the check box to activate the coupon. To deactivate it, clear the check box.
   * **Uses Per Coupon** — Enter the number of times that the coupon may be used.
   * **Uses Per Person** — Enter the number of times a specific customer can use the coupon.
   * **Valid From/Until** — Provide the expiration date and time for the coupon.
4. Click **Save**.

<a id="user-guide-marketing-promotions-coupons-generate"></a>

## Generate Coupons

To generate new coupons:

1. Navigate to  **Marketing > Promotions > Coupons** in the main menu.
2. Click **Coupons Actions > Generate Multiple Coupons** on the top right.
   ![Multiple coupons generation page](user/img/marketing/coupons/GenerateCoupons.png)
3. In the form, complete the following fields:
   * **Promotion** — Select the promotion that the coupon should relate to, or click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to load the list of promotions to choose from. Please note that only promotions with the *Triggered by* [option](../promotions/create.md#user-guide-marketing-promotions-create) set to *Coupons and Conditions* will be displayed on the list of available promotions.
   * **Enabled** — Enable the check box to activate the coupons.
   * **Uses Per Coupon** — Enter the number of times that the coupon may be used.
   * **Uses Per Person** — Enter the number of times a specific customer can use the coupon.
   * **Valid From/Until** — Provide the expiration date and time for the coupon.
   * **Owner** — Select the business unit responsible for the coupon.
   * **Coupon Quantity** — Specify the quantity of coupons to be automatically generated.
   * **Code Length** — Enter the number that represents the desired length of the coupon code.
   * **Code Type** — Select the coupon code type from the list (numeric, alphanumeric or alphabetic).
   * **Code Prefix** — Enter the prefix for the coupon code. If provided, each code will start from this prefix.
   * **Code Suffix** — Enter the suffix for the coupon code. If provided, each code will finish with this suffix.
   * **Add Dashes Every…Symbols** — Provide the number to indicate where a dash should be placed in the coupon code (e.g., after every 2 symbols: xx-xx-xx).
   * **Code Preview** — Preview the sample of the code to be generated for the coupon.

   #### NOTE
   Please note that coupon codes must not be longer than 255 symbols, including prefix, suffix, and dashes.
4. Click **Generate**.

   The coupons list should now have the coupon codes you have just generated.

<a id="user-guide-marketing-promotions-coupons-view"></a>

## Manage a Coupons List

Navigate to **Marketing > Promotions > Coupons** in the main menu.

The page contains the list of all available coupons in your Oro application. From here, you can perform the following actions:

![The page of all coupons available in the system](user/img/marketing/coupons/ActionsCoupons.png)
1. Create a new coupon: Click **Coupons Actions > Create Promotion** on the top right.
2. Generate coupons: Click **Coupons Actions > Generate Multiple Coupons** on the top right.
3. Export coupons: Click  **Export** on the top right.
4. Import coupons: Click  **Import** on the top right.
5. View coupon details: Click on the item from the list to open its details page.
6. Hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary coupon and select either to <i class="fa fa-eye fa-lg" aria-hidden="true"></i> **View**, <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit**, or <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** the existing coupons from the system.
7. Mass edit or mass delete coupons: Select the check boxes on the left of the corresponding rows. Click <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> on the far right of the table header. Click <i class="fa fa-edit fa-lg" aria-hidden="true"></i> **Edit** to edit, or <i class="fas fa-trash-alt" aria-hidden="true"></i> **Delete** to delete the selected coupons.
   ![The illustration of a mass action](user/img/marketing/coupons/MassActionsCoupons.png)
8. Filter a coupons grid to find the required records quicker: Click <i class="fa fa-filter fa-lg" aria-hidden="true"></i> above the table on the far right to display the filters. To apply a filter, click on its button in the bar, and specify your query in the control that appears.

   #### NOTE
   Filter controls might look different depending on the type of data you are going to filter, e.g., textual, numeric, a date or an option set.

   ![Coupon filters in the grid](user/img/marketing/coupons/coupon_filters.png)
9. Organize a coupons list to define which columns to show in the grid: Click <i class="fa fa-cog fa-lg" aria-hidden="true"></i> above the table on the far right.
   * To choose the columns to be displayed in the table, select the check box next to the required column under **Show**. Clear the check box to make the column disappear from the table.
   * To change the order of the columns, click <i class="fas fa-arrows-alt-v" aria-hidden="true"></i> next to the name of the column you wish to move, hold the mouse button and drag the column to the required position.
   * To refresh the coupon list, click <i class="fas fa-redo-alt" aria-hidden="true"></i>.
   * To reset the coupon list, click <i class="fas fa-sync-alt" aria-hidden="true"></i> to clear list customization and return to default settings. Reset applies to all filters, records per page and sorting changes that you have made.

   ![Coupon grid settings](user/img/marketing/coupons/coupon_grid_settings.png)

<a id="user-guide-marketing-promotions-coupons-edit"></a>

<a id="user-guide-marketing-promotions-coupons-edit-view"></a>

<a id="user-guide-marketing-promotions-coupons-edit-on-order-page"></a>

<a id="user-guide-marketing-promotions-coupons-edit-manage-when-editing-an-order"></a>

## Manage Coupons in Orders

In your Oro application, you can manage coupons from the page of the selected [order](../../../sales/orders/index.md#user-guide-sales-orders). Specifically, you can:

1. View the coupon applied to the order under **Promotions and Discounts** of the order page.
2. Add a coupon to the order manually.

### View Coupon Codes

To view the coupon codes that apply to the selected order:

1. Navigate to **Sales > Orders** in the main menu.
2. Click once to open the required order to open it.
3. Click **Promotions and Discounts** to open the section.
4. Under **All Promotions** on the left of the section, click <i class="fa fa-eye fa-lg" aria-hidden="true"></i> at the end of the coupon code row.
   ![View the coupon applied to the order in the back-office](user/img/marketing/coupons/ViewCouponsIcon.png)
5. In the popup that opens, you can view the details of the selected coupon, as illustrated below.
   ![View the details of the coupon applied to the order in the back-office](user/img/marketing/coupons/ViewCoupon.png)

### Add Coupons Through the Order Page

To add a coupon code to the required order from its page:

1. Navigate to **Sales > Orders** in the main menu.
2. Click once to open the required order to open it.
3. On the order page, click **Add Coupon Code** on the top right.
   ![Highlight the Add Coupon Code button on the Order's page](user/img/marketing/coupons/AddCouponToOrder.png)
4. In the popup that opens, choose a coupon code from the list:
   ![Selecting the coupon code from the list in the popup dialog](user/img/marketing/coupons/CouponCodesListOrder.png)

   Alternatively, click <i class="fa fa-bars fa-lg" aria-hidden="true"></i> to load the list of all available coupons:
5. Click **Add** to add the selected coupon code.
6. Click **Apply** to apply the coupon code.

   #### NOTE
   Please keep in mind that you cannot apply two coupon codes to one order if they are related to the same promotion.
7. The applied coupon code will be displayed under **All Promotions** in the **Promotions and Discounts** section.

This way you can apply as many coupons to the order as necessary as long as they belong to different promotions.

### Manage Coupons When Editing the Order

When editing the selected order, you can perform the following actions with the coupons under **All Promotions** in the **Promotions and Discounts** section:

![The actions you can perform with the coupons under All Promotions](user/img/marketing/coupons/AllPromotionsSectioninEditOrderForm.png)
1. **Add Coupon Code** and follow the steps described in the [Add Coupons Through the Order Page](#user-guide-marketing-promotions-coupons-edit-on-order-page) page.
2. <i class="fa fa-eye fa-lg" aria-hidden="true"></i> View a coupon code.
3. <i class="fa fa-times fa-lg" aria-hidden="true"></i> Deactivate/<i class="fa fa-check fa-lg" aria-hidden="true"></i> activate a coupon code.

   #### NOTE
   When you deactivate the coupon code, its status is changed from active to inactive. It is not removed, and you can reactivate it when necessary.
4. <i class="fas fa-trash-alt" aria-hidden="true"></i> Delete a coupon code.

#### NOTE
When you add, deactivate, or delete coupons when editing orders, the price totals and the shipping cost may change. Please, review the order totals to make sure that the cost is acceptable.

## Create a Sample Coupon

As an illustration, let us create a sample promotion and generate 100 coupons for it. These coupons will be redeemed for orders placed by first-time customers. The promotion will offer a 50% discount for all orders between 18 and 22 May 2019.

### Create a Promotion

As coupons should always be linked to promotions, the first step is to create a new promotion:

1. Navigate to **Marketing > Promotions > Promotions** in the main menu.
2. Click **Coupons Actions > Create Promotion** on the top right.
3. In the form that opens, specify the discount details and items, making sure that the **Triggered by** field is set to *Coupons and Conditions*.

   The sample promotion is called **Summer Sale**, and the discount options are 50% off all orders
4. Click **Save and Close**.

### Generate Coupons

Next, generate coupons for this promotion:

1. Navigate to **Marketing > Promotions > Coupons** in the main menu.
2. Click **Coupons Actions > Generate Multiple Coupons**.
3. In the pop up that opens, specify the details of the coupons, making sure that the **Coupon Quantity** is set to *100* and the coupons are linked to the newly created *Summer Sale* promotion.
   ![The popup dialog with the fields you need to fill to generate multiple coupons](user/img/marketing/coupons/SampleCoupons4.png)
4. Click **Generate** once all the details are provided.

### Add Coupons to an Order

Now that the promotion has been created and coupons generated, we can add a coupon to the order that fits the conditions of the discount.

1. Navigate to **Sales > Orders** in the main menu.
2. Select the relevant order and click on it once to open.
3. Click **Add Coupon Code** on the top right of the order page.
4. Select the coupon from the list, click **Add** and then  **Apply**.
5. The coupon for 50% off is now applied to the order.
   ![The illustration of applying the coupon for 50% off to the order](user/img/marketing/coupons/SampleCoupons8.png)
6. In their storefront account, the customer will be able to see the discount applied to their order in the **Order History** menu.
   ![The illustration of applying the coupon for 50% off to the order in the storefront](user/img/marketing/coupons/SampleCoupons9.png)

## Export Coupons

To export the coupons in a .csv format:

1. In the main menu, navigate to **Marketing > Promotions > Coupons**.
2. To export information on all coupons, click **Export** on the top right.
3. Once export is complete, you will receive an email to download the .csv file.

## Import Coupons

**Import File** option helps import large bulk of coupon information into the coupons list using the .csv file.

**Example of coupon bulk import template**

|   Coupon Code |   Enabled |   Uses per Coupon |   Uses per Person | Valid From   | Promotion Name   | Owner Name   |
|---------------|-----------|-------------------|-------------------|--------------|------------------|--------------|
|           123 |         1 |                 1 |                 1 | 01-12-2018   | Discounts        | Owner Name   |

To import a bulk of coupons:

1. In the main menu, navigate to **Marketing > Promotions > Coupons**. The coupons list opens.
2. Click **Import File** on the top right.
3. **Prepare data for import**: Create your bulk information in the .csv format. Once your file is ready, click **Choose File**, select the prepared comma-separated values (.csv) file, and click **Import File**.
   ![The steps that are necessary to perform to import the coupons successfully](user/img/marketing/coupons/import_coupons.png)
4. **Validate import results**: Click **Validate** to check your import results. If there are any *Records with errors*, fix them in the .csv file before starting the import.
5. **Launch import:** After successful validation, click **Import File**.
6. Click **Cancel** to decline the import.

#### IMPORTANT
Interactive status messages inform about the import progress, and once the import is complete, the changes are reflected in the list upon refresh. Additionally, an email message with the import status is delivered to your mailbox.

#### BUSINESS TIP
## Business Tip

Want to dip your toe into the emerging digital commerce trend? Learn more about a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">wholesale B2B marketplace</a>, its unique characteristics, and successful case studies.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
