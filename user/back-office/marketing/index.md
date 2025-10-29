<!-- meta: description = Marketing campaigns, promotions, and web catalog management guides for the Oro application back-office users -->

<a id="user-guide-marketing"></a>

<a id="user-guide-marketing-automation"></a>

# Manage Marketing Activities in the Back-Office

In Oro applications, you can manage, perform, and track the results of your marketing activities, like email campaigns and website activities tracking.

You can integrate with the external services (Mailchimp and Dotdigital) and synchronize marketing campaign configuration and results between these services and Oro application.

In Oro application and external systems, you can launch marketing campaigns distributed via email to the custom group of contacts. The custom group is generated as [marketing list](marketing-lists/index.md#user-guide-marketing-lists).

Once the marketing efforts get their results, you can monitor the collected marketing information in the context of the customers, leads, and many more perspectives

#### NOTE
Enable or disable marketing automation in Oro application via the [system configuration](../system/configuration/marketing/general-setup-marketing/index.md#marketing-system-configuration).

## Via Oro Application

In Oro application, you can use the following marketing tools:

* **Marketing Lists** — Group email data into a target [marketing list](marketing-lists/index.md#user-guide-marketing-lists). It may be automatically generated using flexible filters and may contain any record with an email information, like leads or customer users.
* **Marketing Campaign** — Track statistics of the marketing efforts related to the same [marketing campaign](marketing-campaigns/index.md#user-guide-marketing-campaigns).
* **Email Campaigns** — Schedule or send an email campaign that uses a marketing list as a target audience and may optionally be related to the existing marketing campaign and monitor the results.
* **Website Tracking** — Generate a javascript [tracking code](tracking-websites/index.md#user-guide-marketing-tracking) that may be embedded in your or third-party websites to track users activity that brings valuable insight into your customer needs and your marketing efforts.

#### NOTE
Configure tracking settings in Oro application via the [system configuration](../system/configuration/system/general-setup/tracking.md#admin-configuration-tracking).

## Via Dotdigital

Oro application supports integration with Dotdigital, allowing you to do the following:

- Map the [marketing lists](marketing-lists/index.md#user-guide-marketing-lists) to address books in Dotdigital and keep them synchronized.
- Use your address books to create email campaigns in Dotdigital and import them to Oro application.
- Create new contact data fields to capture additional information about your contacts.
- Use Dotdigital campaign statistics and Oro application reporting tools to analyze the campaign efficiency.

Before you can use Dotdigital with Oro application, ensure that all the necessary integration steps are complete:

* Configure Dotdigital for integration — please refer to the [Dotdigital Configuration guide](../system/integrations/dotdigital/dotdigital-configuration.md#user-guide-dotmailer-configuration).
* Check the [Dotdigital Data Fields and Mappings](email-campaigns/dotdigital-data-fields-mappings.md#user-guide-dotmailer-data-fields) to the Oro application data.
* Set up the schedule for data synchronization between Dotdigital and Oro application — see [Dotdigital Synchronization Settings](../system/configuration/system/integrations/dotdigital-integration-settings.md#admin-configuration-dotmailer-integration-settings).
* Optionally, configure Dotdigital single sign on — please follow the [Dotdigital Single Sign-on](../system/integrations/dotdigital/dotdigital-single-sign-on.md#user-guide-dotmailer-single-sign-on) steps.

After configuring the integration and data synchronization, you can [Send Email Campaign via Dotdigital guide](email-campaigns/sending-email-campaign-via-dotdigital.md#user-guide-dotmailer-campaign).

## Via Mailchimp

Oro application supports out of the box integration with Mailchimp, allowing you to do the following:

* Map the [Marketing Lists](marketing-lists/index.md#user-guide-marketing-lists) as segments in Mailchimp and keep them synchronized.
* Use existing segments in Mailchimp and import them to Oro application.
* Schedule importing statistics of the Mailchimp campaigns into Oro Application.

To use Mailchimp with Oro application, ensure that all the necessary integration steps are complete. See [Mailchimp Integration](../system/integrations/mailchimp-integration.md#user-guide-mc-integration) for more information.

After the integration is configured, you can [Send Email Campaign via Mailchimp](email-campaigns/sending-email-campaign-via-mailchimp.md#user-guide-mailchimp-campaign).

<!-- automation_finish -->
