<a id="user-guide-sales-orders-promotions"></a>

# Manage Discounts in Orders

You can view discounts applied to a specific order under the dedicated **Discounts** section on the order page. This section is divided into **All Promotions** and **All Special Discounts**.

Within **All Promotions**, you can view promotions and coupon codes.

#### NOTE
Promotions can be disabled for an order via REST API, in which case the following message is displayed:

*Promotions are disabled for the order.*

Within **All Special Discounts**, you can view special discounts added manually.

![View the information specified in the Promotions and Discounts section](user/img/marketing/promotions/PromotionsInOrdersNew.png)

<a id="user-guide-sales-orders-promotions-apply-multiple-discounts"></a>

## Apply Multiple Discounts to an Order

When items in the order qualify for multiple discounts, several promotions or coupon codes can be added to it.

#### NOTE
Keep in mind that the application of promotions to orders may be subject to the sort number (priority) assigned to the promotions and whether any of them have **Stop Further Rule Processing** enabled.

You cannot use two coupon codes for one order if they are part of the same promotion.

Promotion can be applied to the existing order in two ways:

* **By creating a new promotion** — If there are no available promotions applicable to the items from the order, you need to [create a new promotion](create.md#user-guide-marketing-promotions-create) with the necessary products added to it. Once you open the order edit page, the created promotion will be added to the order automatically and will be displayed in the **Discounts** section under **All Promotions**.
* **By applying an existing promotion** — If the promotion applicable to the order items was created after the order had been placed, it will be added automatically once you open the order edit page. This promotion will be displayed in the **Discounts** section under **All Promotions**.

The following illustration is an example of multiple discounts applied to one order:

![An example of multiple discounts applied to one order](user/img/marketing/promotions/MultiplePromotionsAppliedtoOrder.png)

<a id="user-guide-sales-orders-promotions-add-special-discount"></a>

## Add Special Discounts to an Order

To add one-time personalized discounts for selected customers:

1. On the order page, click **Add Special Discount** from the **More Actions** menu.
   ![More Actions menu options on the order page](user/img/marketing/promotions/more-actions-discount.png)
2. In the form that opens, provide the following information:
   * **Discount** — Provide the desired discount amount (in currency or percents). This field is mandatory.
   * **Description** — Provide the reason for the special discount. This field is optional.

   ![Providing the discount and description in the form](user/img/marketing/promotions/AddSpecialDiscount2.png)
3. Click **Apply**.

> ![View the discount saved in the All Special Discounts section under Promotions and Discounts](user/img/marketing/promotions/AddSpecialDiscount3.png)

This way, you can apply one or more special discounts to selected orders.

## Manage Discounts When Editing the Order

You can manage promotions, coupons and special discounts for the required order by opening its edit page and navigating to the **Discounts** section.

![Highlight the Add Special Discount button under the Promotions and Discounts section](user/img/marketing/promotions/AddSpecialDiscount4.png)

Under **All Promotions**, you can <i class="fa fa-eye fa-lg" aria-hidden="true"></i> view details of the selected promotion or coupon code, <i class="fa fa-times fa-lg" aria-hidden="true"></i> deactivate, or ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) delete them from the system.

Under **All Special Discounts**, you can <i class="fa fa-edit fa-lg" aria-hidden="true"></i> edit, or ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) remove the discount.

![View the actions that you can do to promotions and discounts](user/img/marketing/promotions/ManagePromotionsIcons.png)
<!-- finish_promotions_in_order -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
<!-- A -->
<!-- B -->
<!-- C -->
<!-- D -->
<!-- E -->
<!-- F -->
<!-- G -->
<!-- H -->
<!-- I -->
<!-- L -->
<!-- M -->
<!-- P -->
<!-- R -->
<!-- S -->
<!-- T -->
<!-- U -->
<!-- Z -->
