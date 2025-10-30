<a id="sys-conf-commerce-contacts-seller-info"></a>

# Configure Global Seller Info Settings

#### NOTE
The Seller Info settings are available as of OroCommerce version 6.1.1.

Some business information, such as your company name, contact details, and tax ID, may need to appear in customer-facing materials such as emails and invoices. You can now manage these details directly from the system configuration.

#### NOTE
Seller information can be configured globally, [per organization](../../../user-management/organizations/org-configuration/commerce/contacts/seller-info-org.md#org-commerce-configuration-contacts-seller-info), and [per website](../../../websites/web-configuration/commerce/contacts/seller-info-website.md#system-website-configuration-commerce-contacts-seller-info).

To configure the seller information settings globally:

1. Navigate to **System > Configuration** in the main menu.
2. Select **Commerce > Contacts > Seller Info** in the menu to the left.

   #### NOTE
   For faster navigation between the configuration menu sections, use [Quick Search](../../quick-search.md#user-guide-system-configuration-quick-search).

   ![Global seller information settings](user/img/system/config_commerce/contacts/seller-info-global.png)
3. Clear the **Use Default** checkbox to adjust the system settings.
4. In the **General Info** section, enter the following information about your business:

* **Company Name** – Enter your official business name.
* **Business Address** – Enter your full business address.
* **Phone Number** – Enter a contact phone number.
* **Contact Email** – Enter your official email address. It must be a valid email format (e.g., `info@example.com`).
* **Website** – Enter your website’s address. It must be a valid URL starting with http or https.
* **Tax ID** – Enter your business tax identification number.

1. Click **Save settings**.

Once configured, you can use this information in:

* [Email templates](../../../emails/email-templates.md#user-guide-email-template) - Add the corresponding variables (e.g., {{ system.sellerCompanyName }} ) to the email template content box to personalize your emails.
  > ![Sample of an email template with seller info variables](user/img/system/config_commerce/contacts/seller-info-email-templates.png)
* Invoices
