<a id="user-guide-email-template"></a>

<a id="user-guide-email-templates-create"></a>

<a id="user-guide-using-emails-create-template"></a>

# Configure Email Templates in the Back-Office

With the Oro applications, you can easily send numerous personalized emails using one template. For example, you can make a single template that welcomes {username}, assign it to an [email campaign](../../marketing/email-campaigns/index.md#user-guide-email-campaigns), and each of your subscribers will get a mail sent specifically to them.

## Create a New Email Template

1. Navigate to **System > Emails > Templates**.
2. Click **Create Template**.
   ![A template creation page](user/img/system/emails/templates/email_template_create.png)
3. Define the general settings for the template.

   The following fields are mandatory and must be defined:
   * **Template Name** — Name used to refer to the template in the system.
   * **Type** — Use html or plain text.
   * **Owner** — Limits the list of users that can manage the template, subject to the [access and permission settings](../user-management/roles/index.md#user-guide-user-management-permissions).

   Optional field **Entity Name** is used to define an [entity](../../../glossary.md#term-Entity), variables whereof can be used in the template. If no entity name is defined, only system variables are available.

   #### IMPORTANT
   If you want to use the template for [autoresponses](../configuration/system/general-setup/global-email.md#admin-configuration-system-mailboxes-autoresponse), the **Entity Name** field value should be **Email**.
4. Define the email template. Click on the necessary variable to add it to the text box.
   ![A sample of an email template](user/img/system/emails/templates/email_template_ex.png)

   #### NOTE
   In the example below, the template contains a link to the website page composed with a piece of [tracking code](../../marketing/tracking-websites/index.md#user-guide-how-to-track). Every time a user follows the link, visit event will be tracked for the campaign.
5. Click **Preview** to check your template.
   ![Preview of an email template](user/img/system/emails/templates/email_template_preview.png)
6. Click **Save** if you are satisfied with the preview.

<a id="user-guide-email-templates-actions"></a>

#### NOTE
You can delete <i class="fas fa-trash-alt" aria-hidden="true"></i>, edit <i class="fa fa-edit fa-lg" aria-hidden="true"></i>, and clone <i class="far fa-copy" aria-hidden="true"></i> email templates on the page of all templates.

![View a list of templates with three options available: edit, clone, delete](user/img/system/emails/templates/email_template_actions.png)

#### IMPORTANT
Keep in mind that the ability to view, edit, clone, or delete email templates depends on specific roles and permissions defined in the system configuration. For more information about available access levels and permissions, see the [Understand Roles and Permissions](../user-management/roles/index.md#user-guide-user-management-permissions-roles) guide.

#### HINT
If you want to track the user-activity related to the emails sent within the email campaign, add a piece of [tracking website](../../marketing/tracking-websites/index.md#user-guide-marketing-tracking) code to the email template.

<a id="user-guide-view-emails-template-variables"></a>

## View Available Template Variables and Functions

For the security reasons, the only available variables are currently the ones listed on the Email Templates edit page in the back-office. However, there are a few exceptions. These are several Twig functions enabled in email templates that can be used to obtain some specific data in email templates.

The full list of these functions is the following:

#### IMPORTANT
Keep in mind that when editing HTML email templates, you pass them to the WYSIWYG editor. WYSIWYG automatically tries to modify the given HTML template against the HTML specifications. Therefore, the text and tags that violate the HTML specifications should be wrapped up in the HTML comment. For example, there should not be any other tags or text between the **<table></table>** tags except **thead**, **tbody**, **tfoot**, **th**, **tr**, **td**.

Examples:

**Invalid template**:

```twig
<table>
    <thead>
        <tr>
            <th><strong>Acme</strong></th>
        </tr>
    </thead>
    {% for item in collection %}
    <tbody>
        {% for subItem in item %}
        <tr>
            {% if loop.first %}
            <td>{{ subItem.key }}</td>
            <td>{{ subItem.value }}</td>
            {% endif %}
        </tr>
        {% endfor %}
    </tbody>
    {% endfor %}
</table>
```

**Valid template**:

```twig
<table>
    <thead>
        <tr>
            <th><strong>Acme</strong></th>
        </tr>
    </thead>
    <!--{% for item in collection %}-->
    <tbody>
        <!--{% for subItem in item %}-->
        <tr>
            <!--{% if loop.first %}-->
            <td>{{ subItem.key }}</td>
            <td>{{ subItem.value }}</td>
            <!--{% endif %}-->
        </tr>
        <!--{% endfor %}-->
    </tbody>
    <!--{% endfor %}-->
</table>
```

### Functions

#### date

```php
date()
```

**Description:** Converts an argument into a date to allow date comparison.

**Example:** See <a href="https://twig.symfony.com/doc/2.x/functions/date.html" target="_blank">the Twig doc</a>

#### oro_config_value

```php
oro_config_value(string $configSettingName)
```

**Description:** Returns the Oro config setting value.

**Returns:** string

**Example:** [Accessing Configuration Values in Templates](../../../../backend/system-configuration/index.md#app-config-templates)

#### calendar_date_range

```php
calendar_date_range(
    \DateTime $startDate = null,
    \DateTime $endDate = null,
    $skipTime = false,
    $dateType = null, \\IntlDateFormatter constant or it's string name
    $timeType = null, \\IntlDateFormatter constant or it's string name
    $locale = null,
    $timeZone = null
)
```

**Description:** Returns a string that represents a range between $startDate and $endDate, formatted according the given parameters.

**Returns:** string

> * $endDate is not specified
>   : * Thu Oct 17, 2013 - when $skipTime = true
>     * Thu Oct 17, 2013 5:30pm - when $skipTime = false
> * $startDate equals to $endDate
>   : * Thu Oct 17, 2013 - when $skipTime = true
>     * Thu Oct 17, 2013 5:30pm - when $skipTime = false
> * $startDate and $endDate are the same day
>   : * Thu Oct 17, 2013 - when $skipTime = true
>     * Thu Oct 17, 2013 5:00pm – 5:30pm - when $skipTime = false
> * $startDate and $endDate are different days
>   : * Thu Oct 17, 2013 5:00pm – Thu Oct 18, 2013 5:00pm - when $skipTime = false
>     * Thu Oct 17, 2013 – Thu Oct 18, 2013 - when $skipTime = true

**Example:**

```php
calendar_date_range(entity.start, entity.end, entity.allDay, 'F j, Y', 1)
```

#### calendar_date_range_organization

```php
calendar_date_range_organization(
    \DateTime $startDate = null,
    \DateTime $endDate = null,
    $skipTime = false,
    $dateType = null, \\IntlDateFormatter constant or it's string name
    $timeType = null, \\IntlDateFormatter constant or it's string name
    $locale = null,
    $timeZone = null,
    OrganizationInterface $organization = null
)
```

**Description:** The same as ‘calendar_date_range’ but for a specific organization.

**Returns:** string

#### get_event_recurrence_pattern

```php
get_event_recurrence_pattern(Entity\CalendarEvent $event)
```

**Description:** This method is aimed at showing text description of a recurring event in email invitations.

**Returns:** string

**Example:**

```php
<!--{% if get_event_recurrence_pattern(entity) %}-->
    <tr>
        <td style="width: 65pt; padding: 0 5pt 0 9pt; line-height: 1.3em; font-family: Arial, Helvetica, sans-serif; font-size: 10pt; vertical-align: top"><strong>Repeats:</strong></td>
        <td style="padding: 0 9pt 0 0; line-height: 1.3em; font-family: Arial, Helvetica, sans-serif; font-size: 10pt; vertical-align: top">{{ get_event_recurrence_pattern(entity) }}</td>
    </tr>
<!--{% endif %}-->
```

#### website_path

```php
website_path(string $route, array $routeParams, Website|null $website = null)
```

**Description:** Returns the absolute path for a specific route and parameters.

**Returns:** string

**Example:**

```php
<p>Please follow this link to confirm your email address: <a href="{{ website_path('oro_customer_frontend_customer_user_confirmation', {'username': entity.username, 'token': token}, entity.website) }}">Confirm</a></p>
```

#### website_secure_path

```php
website_secure_path()
```

**Description:** The same as ‘website_path’ but returns Secure (HTTPS) URL.

#### url

```php
url()
```

**Description:** Returns the absolute URL (with scheme and host) for the given route.

**Example:** See <a href="https://symfony.com/doc/5.4/reference/twig_reference.html#url" target="_blank">the Symfony Twig Extensions (URL)</a>

#### path

```php
path()
```

**Description:** Returns the relative URL (without the scheme and host) for the given route.

**Example:** See <a href="https://symfony.com/doc/5.4/reference/twig_reference.html#path" target="_blank">the Symfony Twig Extensions (Path)</a>

#### get_payment_methods (OroCommerce Only)

```php
get_payment_methods(Order $entity)
```

**Description:** Returns the allowed payment methods for orders.

**Returns:** array of Oro\\Bundle\\PaymentBundle\\Twig\\DTO\\PaymentMethodObject objests with payment method label and options
(can be used as array of strings thanks to PaymentMethodObject::_\_toString method)

**Example:**

```twig
{% set payment_methods = get_payment_methods(entity) %}

<!--{% if  payment_methods|length == 1 %}-->
    <h4>Payment Method:</h4>
    <!--{{ payment_methods[0] }}-->
<!--{% elseif payment_methods|length > 1 %}-->
    <h4>Payment Methods:</h4>
    <!--{{ payment_methods|join(', ') }}-->
<!--{% endif %}-->
```

**Alternative example:**

```twig
{% set payment_methods = get_payment_methods(entity) %}
{% if  payment_methods|length == 1 %}
    <strong>Payment Method: </strong>
{% elseif payment_methods|length > 1 %}
    <strong>Payment Methods: </strong>
{% endif %}
{% for payment_method in payment_methods %}
    {{ payment_method.label }}
    {% if payment_method.options|length > 0 %}
        {{- ' (' ~ payment_method.options|join(', ') ~ ')' -}}
    {% endif %}
    <br/>
{% endfor %}
```

#### get_payment_status_label (OroCommerce only)

```php
get_payment_status_label(Order $entity)
```

**Description:** Returns the translated label for the payment status.
See the `\Oro\Bundle\PaymentBundle\Formatter\PaymentStatusLabelFormatter::formatPaymentStatusLabel` method for details.

**Returns:** string

**Example:** See an example for the [get_payment_status (OroCommerce only)]() method.

#### get_payment_status (OroCommerce only)

```php
get_payment_status(Order $entity)
```

**Description:** Returns the payment status for requested order.

**Returns:** string, one of Oro\\Bundle\\PaymentBundle\\Provider\\PaymentStatusProvider class statuses
(‘full’, ‘partially’, ‘invoiced’, ‘authorized’, ‘declined’, ‘pending’)

**Example:**

```twig
<strong>Payment Status: </strong>{{ get_payment_status_label(get_payment_status(entity)) }}
```

#### oro_order_shipping_method_label (OroCommerce only)

```php
oro_order_shipping_method_label(string $shippingMethod, string $shippingMethodType)
```

**Description:** Returns the translated label of the order\`s shipping method.

**Returns:** string

**Example:**

```twig
{% set shipping_method = oro_order_shipping_method_label(entity.shippingMethod, entity.shippingMethodType) %}
<strong>Shipping Method: </strong>{{ shipping_method }}<br/>
```

#### rfp_products (OroCommerce Only)

```php
rfp_products(Oro\Bundle\RFPBundle\Entity\Request $entity)
```

**Description:** Returns a list of products requested by a buyer in this request for quote.

**Returns:**

```php
array: [
    345 => [ \\Product ID
        'name' => 'Yarn', \\ string, Product name
        'sku' => 'YRN345erer', \\ string, Product SKU
        'comment' => 'Most interesting product for us', \\ string, Comment in RFP for this product
        'items' => [ \\array, Requested product items
            38473 => [ \\Product Item ID
                'quantity' => 49.86, \\ float, Product Item quantity
                'price' => $price, \\ \Oro\Bundle\CurrencyBundle\Entity\Price object, Product Item price
                'unit' => 'ft', \\ string, Product Item unit
            ],
            139473 => [ \\Product Item ID
                'quantity' => 21.98, \\ float, Product Item quantity
                'price' => $price, \\ \Oro\Bundle\CurrencyBundle\Entity\Price object, Product Item price
                'unit' => 'item', \\ string, Product Item unit
            ],
            ...
        ],
    ],
    ...
]
```

**Example:**

```php
{% set products = rfp_products(entity) %}
{% if products|length %}
    <table style="border: 1px solid black;margin-top: 10px">
        <thead>
            <tr>
                <th><strong>SKU</strong></th>
                <th><strong>Product</strong></th>
                <th><strong>Quantity</strong></th>
                <th><strong>Target Price</strong></th>
                <th><strong>Comment</strong></th>
            </tr>
        </thead>
        <!--{% for product in products %}-->
            <!--{% set numItems = product.items|length %}-->
            <tbody>
                <!--{% for item in product.items %}-->
                    <tr>
                        <!--{% if loop.first %}-->
                            <td rowspan="{{ numItems }}">{{ product.sku }}</td>
                            <td rowspan="{{ numItems }}">{{ product.name }}</td>
                        <!--{% endif %}-->

                        <td>{{ item.quantity }} {{ item.unit }}</td>
                        <td>{{ item.price ? item.price|oro_format_price : '' }}</td>

                        <!--{% if loop.first %}-->
                            <td rowspan="{{ numItems }}">{{ product.comment }}</td>
                        <!--{% endif %}-->
                    </tr>
                <!--{% endfor %}-->
            </tbody>
        <!--{% endfor %}-->
    </table>
{% endif %}
```

#### line_items_discounts (OroCommerce only)

```php
line_items_discounts(Order $entity)
```

**Description:** Returns array of discount total sum for every order line item.

**Returns:** array

```php
array: [
    '123123' => [ // Line Item ID
        'value' => 15.065, \\ float, total sum of discount for the line item
        'currency' => 'USD', \\ string, Currency of discount
    ],
    ...
]
```

**Example:** See an example for [order_line_items (OroCommerce only)]() method.

#### order_line_items (OroCommerce only)

```php
order_line_items(\Oro\Bundle\OrderBundle\Entity\Order $entity)
```

**Description:** Returns order line items.

**Returns:**

```php
array: [
    'lineItems' => [
        [
            'product_name' => 'Boat', \\ string, Product name
            'product_sku' => 'BO1BIG', \\ string, Product SKU
            'quantity' => 1.00, \\ float, Product quantity
            'unit' => 'item', \\ string, Product unit
            'price' => $price, \\ \Oro\Bundle\CurrencyBundle\Entity\Price object, Product price
            'comment' => 'Comment for this line Item', string
            'ship_by' => $price, \\ \DateTime, Line item ship by field
            'id' => $id, \\ int|string, Line item identifier value
            'subtotal' => $price, \\\Oro\Bundle\CurrencyBundle\Entity\Price object, Line Item subtotal
        ],
        ...
    ],
    'subtotals' => [
        [
            'label' => 'Shipping', \\ string, Subtotal name
            'totalPrice' => $price, \\\Oro\Bundle\CurrencyBundle\Entity\Price object, Subtotal Price
        ],
        ...
    ],
    'total' => [
        'label' => 'Total', \\ string, label for Total
        'totalPrice' => $price, \\\Oro\Bundle\CurrencyBundle\Entity\Price object, Total sum Price for all order line items
    ],
]
```

**Example:**

```twig
<table style="border: 1px solid black;margin-top: 10px">
    <thead>
    <tr>
        <th><strong>Item</strong></th>
        <th><strong>Quantity</strong></th>
        <th><strong>Price</strong></th>
        <th><strong>Subtotal</strong></th>
        <th><strong>Ship By</strong></th>
        <th><strong>Notes</strong></th>
    </tr>
    </thead>
    <tbody>
    <!--{% set data = order_line_items(entity) %}-->
    <!--{% set lineItemDiscounts = line_items_discounts(entity) %}-->
    <!--{% for item in data.lineItems %}-->
        <tr>
            <td>
                {{ item.product_name }}
                <br>
                SKU #: {{ item.product_sku }}
                <br>
            </td>
            <td>{{ item.quantity|oro_format_short_product_unit_value(item.unit) }}</td>
            <td>{{ item.price|oro_format_price }}</td>
            <td>
                {{ item.subtotal|oro_format_price }}
                {% set matchedDiscount = lineItemDiscounts[item.id] %}
                {% if matchedDiscount is not null and matchedDiscount.value > 0 %}
                    <br/>{{ (-matchedDiscount.value)|oro_format_currency({'currency': matchedDiscount.currency}) }}
                {% endif %}
            </td>
            <td>{{ item.ship_by }}</td>
            <td>{{ item.comment }}</td>
        </tr>
    <!--{% endfor %}-->
    </tbody>
</table>
```

#### NOTE
If none of these Twig functions cover your cases, you can **create a custom Twig function** that returns the desired data that you can use in email templates.
Please, see [OroEmailBundle documentation](../../../../bundles/platform/EmailBundle/email-templates.md#bundle-docs-platform-email-bundle-template) for details.

### Filters

On top of functions, you can use filters in email templates. The full set of these filters is the following:

* <a href="https://twig.symfony.com/doc/2.x/filters/default.html" target="_blank">default</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/date.html" target="_blank">date</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/escape.html" target="_blank">escape</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/format.html" target="_blank">format</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/length.html" target="_blank">length</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/lower.html" target="_blank">lower</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/nl2br.html" target="_blank">nl2br</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/number_format.html" target="_blank">number_format</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/title.html" target="_blank">title</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/trim.html" target="_blank">trim</a>
* <a href="https://twig.symfony.com/doc/2.x/filters/upper.html" target="_blank">upper</a>
* [oro_html_sanitize](../../../../bundles/platform/UIBundle/twig-filters.md#bundle-docs-platform-ui-bundle-twig-filters)
* <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/UIBundle/Twig/FormatExtension.php#L76" target="_blank">oro_format</a>
* [oro_format_address](../../../../bundles/platform/LocaleBundle/address-formatting.md#bundle-docs-platform-locale-bundle-oro-format-address)
* <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/LocaleBundle/Twig/DateTimeExtension.php#L122" target="_blank">oro_format_date</a>
* <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/LocaleBundle/Twig/DateTimeExtension.php#L174" target="_blank">oro_format_time</a>
* <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/LocaleBundle/Twig/DateTimeExtension.php#L92" target="_blank">oro_format_datetime</a>
* oro_format_datetime_organization
* [oro_format_name](../../../../bundles/platform/LocaleBundle/name-formatting.md#bundle-docs-platform-locale-bundle-format-name)
* <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/CurrencyBundle/Twig/CurrencyExtension.php#L111" target="_blank">oro_format_price</a>
* <a href="https://github.com/oroinc/platform/blob/5.1/src/Oro/Bundle/LocaleBundle/Twig/NumberExtension.php#L212" target="_blank">oro_format_currency</a>
* [oro_format_short_product_unit_value](../../../../bundles/commerce/ProductBundle/product-unit-formatting.md#product-bundle-short-formatting)
* <a href="https://twig.symfony.com/doc/2.x/filters/join.html" target="_blank">join</a>

### Tags

The full set of allowed tags to use in email templates is the following:

* app
* <a href="https://twig.symfony.com/doc/2.x/tags/for.html" target="_blank">for</a>
* <a href="https://twig.symfony.com/doc/2.x/tags/if.html" target="_blank">if</a>
* <a href="https://twig.symfony.com/doc/2.x/tags/spaceless.html" target="_blank">spaceless</a>
* <a href="https://twig.symfony.com/doc/2.x/tags/set.html" target="_blank">set</a>

<a id="localize-email-templates"></a>

## Localize Email Templates

To create email templates for different localizations, even the inactive ones, move from tab to tab and create the desired content for required localizations.

![Navigating from one language tab to another](user/img/system/emails/templates/email_template_localization.png)

To enable the email template fallback to the parent localization, select the **Use <localization> (Parent Localization)** checkbox. If the localization does not have a parent, you can enable fallback to the default template value.

#### BUSINESS TIP
## Business Tip

Interested in learning more about <a href="https://oroinc.com/b2b-ecommerce/what-is-b2b-ecommerce/" target="_blank">B2B eCommerce</a> and how it differs from B2C? Read our in-depth information on the subject.

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
