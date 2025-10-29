<a id="admin-embedded-forms"></a>

# Configure Embedded Forms in the Back-Office

In Oro application, embedded forms help create the code that may be added to a third-party website to enable communication between the third-party website users and the Oro application.

Embedded forms may be used to collect requests of marketing, technical, commercial or any other nature.

Additional embedded form types may be created in the course of integration with the Oro application, subject to your specific business needs.

## Create an Embedded Form

In order to create a new embedded form:

1. Navigate to **System > Integrations > Embedded Forms** in the main menu.
2. Click **Create Embedded Form**.
3. Provide the following details:
   * **Title** — The title used to refer to the form in the system. The field must be defined.
   * **Form Type** — Choose one of the available form types.
   * **CSS** — Editable CSS. The default CSS corresponds to the initial form design, subject to its type. You can edit the CSS to change such settings as the border width, color, fonts etc.
   * **Success Message** — The message to be displayed on the website following the successful form submission. By default is set to *Form has been submitted successfully*.
   * **Allowed Domains** — Allowed cross origin domains where the form can be embedded. Supports wildcard, e.g., X.example.com.
     > ![A sample of the Thanks for question form configuration](user/img/system/integrations/emb_form/embedded_form_contact_us.png)
4. Click **Save and Close**.
   ![The Thanks for question form preview](user/img/system/integrations/emb_form/emb_form_create_ex_02.png)

Once saved, the form is displayed on the page of all embedded forms under **System > Integrations > Embedded Forms**.

![A list of all embedded forms](user/img/system/integrations/emb_form/emb_form_create_ex_01.png)

You can view <i class="fa fa-eye fa-lg" aria-hidden="true"></i>, edit <i class="fa fa-edit fa-lg" aria-hidden="true"></i>, and delete ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) contact requests using the corresponding action icons.

<a id="admin-embedded-forms-code"></a>

## Add Embedded Forms to Your Site

To add the necessary embedded form to your website:

1. Navigate to **System > Integrations > Embedded Forms** in the main menu.
2. Click on the form to open its details page.
3. In the **Get Code** section, copy the provided code and paste it to the required section of your website.

![A sample iframe code for the Thanks for question form](user/img/system/integrations/emb_form/emb_form_code.png)
<!-- stop -->
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
