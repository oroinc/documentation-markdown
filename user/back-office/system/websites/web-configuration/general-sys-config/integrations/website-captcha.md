<a id="website-configuration-captcha-settings"></a>

# Configure CAPTCHA Settings per Website

CAPTCHA, which stands for Completely Automated Public Turing test to tell Computers and Humans Apart, is a type of challenge-response test used to verify whether the user is human. CAPTCHAs are crucial for maintaining the integrity, security, and usability of online systems. They ensure that interactions and transactions on websites are legitimate and performed by real users, protecting against malicious activities.

In OroCommerce, you can configure CAPTCHA on [global](../../../../configuration/system/integrations/captcha-settings.md#admin-configuration-integrations-captcha-global), [organization](../../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-captcha.md#organization-configuration-captcha), and website levels using any of the tree supported service: Google reCAPTCHA, hCAPTCHA and Cloudflare Turnstile.

To configure CAPTCHA settings per website:

1. Navigate to **System > Websites** in the main menu.
2. For the necessary website, hover over the <i class="fa fa-ellipsis-h fa-lg" aria-hidden="true"></i> **More Options** menu to the right of the necessary website and click <i class="fas fa-cog" aria-hidden="true"></i> to start editing the configuration.
3. Click **System Configuration > Integrations > CAPTCHA Settings** in the menu to the left.
   ![CAPTCHA configuration settings on the website level](user/img/system/websites/web_configuration/captcha-website-settings.png)

   To override the organization’s configuration settings, clear the **Use Organization** option next to the required option.

1. In the **General** section, you have the following options:
   * **Enable CAPTCHA Protection** — Enable or disable the CAPTCHA protection feature for the OroCommerce application.
   * **CAPTCHA Service** — Select the CAPTCHA service for the storefront. Available options are Google reCAPTCHA, hCAPTCHA and Cloudflare Turnstile.
   * **Protect Forms** — Select which forms to enable the CAPTCHA protection for. Developers can add protection for custom forms via the DI Tag. For more information on how to do it, see [FormBundle documentation](../../../../../../../bundles/platform/FormBundle/captcha-protection.md#bundle-docs-platform-form-bundle-captcha).
2. In the **Google reCAPTCHA** section, provide the following information:
   * **Site Key** — Provide a site key generated in the Google admin console.
   * **Secret Key** —  Provide a secret key generated in the Google admin console.
   * **Minimal Allowed Score** — Google reCAPTCHA v3 returns a score based on which you can take variable action in the context of your site. For example, 1.0 is very likely a good interaction, 0.0 is very likely a bot.

   For more information on these options, please refer to the <a href="https://developers.google.com/recaptcha/docs/v3" target="_blank">Google reCapture documentation</a>.
3. In the **hCaptcha** section, provide the following information:
   * **Site Key** — Provide a site key generated in the hCapture account.
   * **Secret Key** — Provide a secret key generated in the hCapture account.

   For more information on these options and how to create an hCapture account, please refer to the <a href="https://docs.hcaptcha.com/" target="_blank">hCapture documentation</a>.
4. In the **Cloudflare Turnstile**, provide the following information:
   * **Site Key** — Provide a site key to invoke Turnstile on your site generated in the settings of your Turnstile widget in your Cloudflare account.
   * **Secret Key** — Provide a secret key to connect to the Cloudflare Turnstile server generated in the settings of your Turnstile widget in your Cloudflare account.

   For more information on these options, please refer to the <a href="https://developers.cloudflare.com/turnstile/" target="_blank">Cloudflare Turnstile documentation</a>.
5. Click **Save Settings**.

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
