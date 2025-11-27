<a id="bundle-docs-platform-scimbundle"></a>

# OroScimBundle

#### NOTE
This bundle is available as of OroCommerce Enterprise version 6.1.7.

OroScimBundle adds support for the **System for Cross-domain Identity Management (SCIM)** protocol in the Oro application. It enables automatic user management between Oro and external identity systems, such as <a href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/user-provisioning" target="_blank">Microsoft Entra ID</a> (formerly Azure Active Directory), via SCIM API by SCIM extension. This integration allows imported users to sign in to Oro via [Microsoft 365 Single Sign-On](../../../user/back-office/system/configuration/system/integrations/microsoft-settings/microsoft-single-sign-on.md#user-guide-integrations-microsoft-single-sign-on).

SCIM 2.0 (<a href="https://datatracker.ietf.org/doc/html/rfc7642" target="_blank">RFC 7642</a>, <a href="https://datatracker.ietf.org/doc/html/rfc7643" target="_blank">RFC 7643</a>, <a href="https://datatracker.ietf.org/doc/html/rfc7644" target="_blank">RFC 7644</a>) is a standard protocol designed to simplify account management - creating, updating, and deleting user accounts across multiple applications from one centralized identity management system. This means that users can be automatically *provisioned* (created), updated, or *deprovisioned* (deleted) in Oro whenever changes are made in your connected identity provider.

**Supported Operations**

* **User synchronization** – Oro currently supports syncing user information between systems.
* **Group synchronization** – Not supported at this time.

**API Endpoints:**

* For standard installations, you can access the SCIM API at the `https://yourapplication/scim/Users` URL.
* For OroCommerce installations, the API is available at the `https://yourapplication/{backend_prefix}/scim/Users` URL, where {backend_prefix} is your current back-office prefix (by default, it is `admin`).

**API Sandbox:**

* For standard installations, you can access the SCIM API sandbox at the `https://yourapplication/api/doc/scim_rest` URL.
* For OroCommerce installations, the API sandbox is available at the `https://yourapplication/{backend_prefix}/api/doc/scim_rest` URL, where {backend_prefix} is your current back-office prefix (by default, it is `admin`).

**SCIM Synchronization Configuration**

For more details on how to configure the SCIM synchronization in the back-office, follow the steps described in the [related documentation](../../../user/back-office/system/configuration/system/general-setup/user.md#admin-configuration-user-settings-scim).

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
