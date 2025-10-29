<a id="system-websites-create"></a>

# Create a Website in the Back-Office

#### IMPORTANT
Multi-website management is only available in the Enterprise edition.

To create a new website in OroCommerce:

1. Navigate to **System > Websites** using the main menu.
2. Click **Create Website**.
   ![The create website page](user/img/system/websites/create_website_page.png)
3. In the **General** section, provide the following information:
   * **Owner** — the field is prepopulated with the organization to which the user who creating a website belongs. You can change this value, if necessary.
   * **Name** — the website name.
   * **Configure For B2C** — if set to *Yes*, some website configuration settings are modified to match the standard B2C setup. The changes affect the following options:
     ![The list of options that are modified for the B2C website](user/img/system/websites/B2C_settings.png)

     You can always modify any of these options manually in the system configuration.

     If set to *No*, the settings that you have configured for your website remain intact.
4. In the **Price Lists** section, configure the following options:
   * **Fallback** — specify whether the website prices should reuse the global price list defined in the system configuration whenever the product price is not available in the price list specified for the website.
   * **Price Lists** — select the price list to use for this website. You may add multiple price lists using the **+ Add Price List** option and specify the priority that controls the way the price is looked up.

   Priority defines the order in which OroCommerce walks through the price lists to find a product price. Whenever the price is not found in the higher priority price list, OroCommerce switches to the next one.

<!-- To configure flexible price options, set **Merge** flags for the price lists you would like to combine to cover the most product units. The unit price from the lower priority price list is used when it is missing in the higher priority price list. This mechanism applies only to the price lists where the *merge* is enabled.

.. note:: Price list configuration on the customer or customer group level may override the website configuration. -->
1. In the **Additional** section, define the default customer user roles to be assigned to both guests and authenticated users.
   * **Guest Role** - select the [customer user role](../../customers/customer-user-roles/index.md#user-guide-customers-customer-user-roles) that will be applied to all guest visitors of the current website by default. A set of [permissions and access levels](../user-management/roles/index.md#user-guide-user-management-permissions-roles) defined for the selected role affects the way guest users manage their data in the storefront.
   * **Default Self-Registration Role** - select the default [customer user role](../../customers/customer-user-roles/index.md#user-guide-customers-customer-user-roles) that will be applied to the users once they register an account on the website automatically. To enable this option, set the corresponding registration permission in the [website configuration](web-configuration/commerce/customers/website-customer-users.md#system-website-configuration-commerce-customers-customer-users) under **Commerce > Customer > Customer Users**.
2. Click **Save and Close**.

**Next steps**

* After creating the website in OroCommerce, ensure that the customer users will navigate to the website in your planned scenarios. Perform the necessary configuration on the web server or cookie preparation in order to make the website identifiable. For more details on the necessary configuration outside OroCommerce, please refer to the *src/Oro/Bundle/MultiWebsiteBundle/Resources/doc/website_matchers.md* document in the OroCommerce Enterprise GitHub repository.
* Make the necessary [adjustments](../../../../backend/setup/installation-in-sub-folder.md#system-websites-prepare-to-host-a-website-in-the-domain-sub-folder) if you plan to host several websites on the same domain, in the sub-folders (e.g., *http://store.com/uk* and *http://store.com/us*).

**Related Topics**

* [Setup a Website Host](../../../../backend/setup/installation-in-sub-folder.md#system-websites-prepare-to-host-a-website-in-the-domain-sub-folder)
* [Configure a Website](web-configuration/index.md#user-guide-system-websites-configure-website)
* [Manage a Website](manage.md#user-guide-system-websites-manage-websites)
