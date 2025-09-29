<a id="bundle-docs-commerce-cookie-consent-bundle"></a>

# CookieConsentBannerBundle

Cookies can be used to uniquely identify a person, which means that they represent personal data.
In compliance with the General Data Protection Regulations (GDPR), it is required to let website visitors
and customers know what types of cookies will be used, and allow them to choose which ones they want to agree to.
Implied consents and consents given by visiting a website are not enough.

To comply with the GDPR policy, OroCommerce enables you to set up a **Cookie Banner** with your custom text to be
displayed in the storefront of the OroCommerce website, and translate it into your preferred language.

## Add a Cookie Banner

To set up a cookie banner:

1. Add new a package as a dependency in the composer.json file:

```none
"require": {
  "oro/cookie-consent": "5.0.*"
}
```

1. Run the following commands:

   **For dev mode**
   ```bash
   rm -rf var/cache/*
   composer install --prefer-dist --no-dev
   php bin/console oro:platform:update --env=prod --force
   php bin/console oro:message-queue:consume --env=dev
   ```

   **For prod mode**
   ```php
   rm -rf var/cache/*
   composer install --prefer-dist --no-dev
   php bin/console oro:platform:update --env=prod --force
   php bin/console oro:message-queue:consume --env=prod
   ```

1. Reload the application in the browser.

## Add a Translation

To add a translation to the cookie banner to present information in the desired language:

1. Run the following command:
   ```php
   php bin/console oro:translation:load --env=prod
   ```
2. In the back-office, navigate to **System > Localization > Translations**.
3. Using filters, locate following translation keys:
   * *oro_cookie_banner.text*
   * *oro_cookie_banner.button_label*
4. Add translation for the banner text and label.
5. Click **Update Cache** on the top right.
6. Once cache is updated, the translated banner will be displayed in the storefront.

#### BUSINESS TIP
## Business Tip

Do you want to use advanced technologies to drive <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digital transformation in manufacturing</a>? Our guide offers relevant tips, examples, and pitfalls to avoid.

**Related Topics**

* [Cookie Consent Banner](../../../user/storefront/cookie-consent-banner/index.md#frontstore-guide-cookie-banner)
* [Configure Consent Banner](../../../user/back-office/system/configuration/commerce/customer/global-customer-users.md#configuration-guide-commerce-configuration-cookie-consents)

<!-- Frontend -->
