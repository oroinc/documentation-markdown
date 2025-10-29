<a id="user-guide-payment-prerequisites-paypal-express"></a>

# Prerequisites for PayPal Express Services Integration

<!-- begin -->

## Install Oro PayPal Express Integration Package

Before you can use PayPal Express in OroCommerce, [install](../../../../../../../backend/extension/install-extension.md#cookbook-extensions-composer) the <a href="https://packagist.oroinc.com/?#oro/paypal-express" target="_blank">Oro PayPal Express Integration</a>  package.

## Register a Business Account with PayPal

To register a business account for your OroCommerce PayPal Express integration, follow the next steps:

1. Open <a href="https://developer.paypal.com/" target="_blank">https://developer.paypal.com/</a> and click **Log In**.
2. On the login page that opens, click **Sign Up**.
3. On the following page, select **Business Account** and click **Continue**.
4. Select the service plan (Payment Pro, Payments Standard, or Express Checkout).

   The Get Started page opens.
   ![image](user/img/system/integrations/paypal/paypal_business_account_1.png)
5. Type in your email.

   The Sign up for a Business account page opens.
   ![image](user/img/system/integrations/paypal/paypal_business_account_2.png)
6. Enter the password and password confirmation.
7. Provide your business contact information.
8. Read the *PayPal User Agreement*.
9. Click **Agree and Continue**.

   On the following page, select your type of business and provide the requested additional information.
   ![image](user/img/system/integrations/paypal/paypal_business_account_3.png)
10. Provide the requested personal information.
    ![image](user/img/system/integrations/paypal/paypal_business_account_4.png)
11. Click **Submit**.

    The PayPal Business Account opens.
12. In *Account Setup*, confirm your email, link your bank account, and configure the credit card statement.

<a id="paypal-express-test-account"></a>

## Create a Sandbox Test Account

The PayPal Express sandbox test account is identical to the regular PayPal account but is hosted in the sandbox environment.

To create a sandbox test account, follow the next steps:

1. Log into the <a href="https://developer.paypal.com/" target="_blank">https://developer.paypal.com/</a> with the credentials generated in the previous step.
2. Navigate to **Dashboard** and click **Accounts** in the **Sandbox** section.
3. Click **Create Account** to create a new sandbox account.
4. Fill in the account details (Account Type, Email Address, Password, PayPal Balance) and click **Create Account**.
5. Once the account is created, you can check its details by clicking the **Profile** link below the newly created account.
   ![image](user/img/system/integrations/paypal/paypal_sandbox_account.png)

Here, you can view your profile details, sandbox API credentials, your test credit card number, the PayPal balance, and other configuration by clicking the corresponding tab.

> ![image](user/img/system/integrations/paypal/paypal_sandbox_profile_details.png)

<a id="paypal-express-sandbox-credentials"></a>

## Obtain Sandbox Credentials

Once you have created a sandbox account, you need to obtain the test credentials, such as **Client ID** and **Client Secret**, to check the integration between OroCommerce and PayPal Express in the test mode without any charges.

To receive the credentials, you need to create a corresponding REST API application:

1. Log into the <a href="https://developer.paypal.com/" target="_blank">https://developer.paypal.com/</a> with your existing credentials.
2. Navigate to **Dashboard > My Apps & Credentials** in the main menu to the left.
3. Scroll down to the **REST API apps** section and click **Create App** to request the credentials.
   ![image](user/img/system/integrations/paypal/paypal_rest_API_credentials.png)
4. Enter a name for your application and select a sandbox developer account from the list.
5. Click **Create App**.
   ![image](user/img/system/integrations/paypal/paypal_rest_API_credentials_steps.png)
6. On the page that opens, select **Sandbox** to get the requested **Client ID** and **Client Secret** values.
   ![image](user/img/system/integrations/paypal/paypal_sandbox_API_credentials.png)
7. Use the credentials to set up the test integration between PayPal Express and OroCommerce.

<a id="paypal-express-production-credentials"></a>

## Obtain Production Credentials

Once you have successfully configured the PayPal Express integration as described in the [PayPal Express](index.md#config-guide-payment-paypal-express) guide, and the connection to the test environment is working properly, you can move to a production stage, but this time use the production credentials.

1. Log into the <a href="https://developer.paypal.com/" target="_blank">https://developer.paypal.com/</a> with your existing credentials.
2. Navigate to **Dashboard > My Apps & Credentials** in the main menu to the left.
3. Scroll down to the **REST API apps** section and select the required application by clicking it.
4. On the page that opens, select **Live** to get the requested **Client ID** and **Client Secret** values.
   ![image](user/img/system/integrations/paypal/paypal_live_API_credentials.png)
5. Use the credentials to set up the production integration between PayPal Express and OroCommerce.

#### NOTE
Remember NOT to select the **Sandbox Mode** checkbox as you are configuring the production integration.
