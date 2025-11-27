<a id="admin-openapi-specifications"></a>

# OpenAPI Specifications Management

#### NOTE
This feature is available as of OroCommerce version 6.0.2.

This section describes how to create and manage OpenAPI specifications for different types of REST APIs provided by Oro applications.

## Create an OpenAPI Specification

In order to create a new OpenAPI specification:

1. Navigate to **System > Integrations > OpenAPI Specifications** in the main menu.
2. Click **Request Specification**.
3. Provide the following details:
   * **Name** — The name of the OpenAPI specification.
   * **Public Slug** — The URL slug for downloading the OpenAPI specification without authorization. When the slug is not specified the unauthorized access is not permitted.
   * **Requested By** — A user who requested the OpenAPI specification.
   * **Format** — The format in which the OpenAPI specification should be created, e.g. JSON or YAML.
   * **API Type (View)** — The API type for which the OpenAPI specification should be created, e.g. “Back-Office API” or “Storefront API”.
   * **Entities** — The list of entities for which the OpenAPI specification should be created. When no entity is specified, the specification is created for all entities.
   * **Server URLs** — The list of server URLs that should be added to the OpenAPI specification.
     > ![A sample of an OpenAPI specification request](user/img/system/integrations/openapi/create.png)
4. Click **Save and Close**.

Once saved, a request to create the specification is sent and the specification is displayed on the page of all OpenAPI specifications under **System > Integrations > OpenAPI Specifications**.

![A list of all OpenAPI specifications](user/img/system/integrations/openapi/grid.png)

You can download <i class="fa fa-download fa-lg" aria-hidden="true"></i>, renew ![Reset-SVG](_themes/sphinx_rtd_theme/static/svg-icons/reset.svg), view <i class="fa fa-eye fa-lg" aria-hidden="true"></i>, edit <i class="fa fa-edit fa-lg" aria-hidden="true"></i>, clone <i class="far fa-copy" aria-hidden="true"></i>, and delete ![Trash-SVG](_themes/sphinx_rtd_theme/static/svg-icons/trash.svg) specifications using the corresponding action icons.

Once you have finished the configuration of a specification and want to make it read-only, click Publish <i class="fas fa-share-square" aria-hidden="true"></i>. Also, when the public slug is provided, a published specification will be available for unauthorized users to download.

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
