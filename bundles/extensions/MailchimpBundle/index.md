<a id="bundle-docs-extensions-mailchimp"></a>

# OroMailChimpBundle

<a href="https://github.com/oroinc/OroCRMMailChimpBundle" target="_blank">OroMailChimpBundle</a> provides <a href="https://github.com/oroinc/platform/tree/master/src/Oro/Bundle/IntegrationBundle" target="_blank">integration</a> with <a href="https://mailchimp.com/" target="_blank">MailChimp</a> marketing automation platform for Oro applications.

The bundle enables users to create and configure the integration, schedule, or manually start synchronization between Oro application marketing lists and MailChimp subscribers list and import data of MailChimp email campaigns into the Oro application.

## Setting Up Connection

For steps on configuring the integration on the Mailchimp and Oro sides, please see [user configuration documentation](../../../user/back-office/system/integrations/mailchimp-integration.md#user-guide-mc-integration).

## Connecting a Marketing List to MailChimp Audience

After the integration is created and enabled, Oro marketing lists can be connected to the MailChimp audience.

#### HINT
More information on how to <a href="https://mailchimp.com/help/create-audience/" target="_blank">create an audience</a> is available on the Mailchimp website.

For steps on connecting a marketing list to Mailchimp, please see the [Send Email Campaign via Mailchimp](../../../user/back-office/marketing/email-campaigns/sending-email-campaign-via-mailchimp.md#user-guide-mailchimp-campaign) topic.

## Import Synchronization Logic

Import is performed with the *oro:cron:integration:sync* cron command.

- **Lists**: All MailChimp audiences are imported with Merge Vars information
- **Static Segments**: Only the segments connected to marketing lists are synchronized
- **Campaigns**: Only campaigns sent to the static segment connected to an Oro marketing list are imported

A new email campaign is created in the Oro application for a MailChimp campaign and synchronized during the following imports:

- **Members**: All members for the lists connected to an Oro Static Segment are imported. *Export API is used with the Since filter*
- **Member Activities**: Member activities are loaded for Campaigns that were imported to the Oro application. *Export API is used with the Since filter*

Each member’s activity is mapped to the Oro Marketing List Item and Email Campaign Statics by Email. So more than one marketing list item and email campaign statics record can be created if several entities have the same email in the marketing list.
Activities ‘open’, click’, ‘bounce’, ‘unsub’, ‘abuse’ increment the corresponding counters of the email campaign statics.
Activity ‘sent’ increments the ‘contacted times’ counter and sets the ‘last contacted at’ variable of the marketing list item.

## Export Logic

Export is performed with the *oro:cron:mailchimp:export* cron command.

The following steps are performed in the course of the marketing list members synchronization with MailChimp:

* All the marketing list members are checked for subscription to the MailChimp audience. Unsubscribed members are scheduled for the subscription.
* All the marketing list members absent from the static segment are scheduled for the mass addition to the segment.
* All the members present in the static segment but absent in the marketing list are scheduled for removal from the static segment.

Segment export has four steps:

- **handle_add_state** adds a new member to MailChimp
- **handle_remove_state** removes members from the segment in MailChimp
- **handle_unsubscribe_state** unsubscribes members from the audience in MailChimp
- **handle_delete_state** deletes members from the audience in MailChimp

#### NOTE
> When the MailChimp audience has more than 100 merge vars, sync env variable *oro_mailchimp.client.merge_fields_count* with the actual number of merge vars.

To make marketing list members accepted without the merge vars values even when they are required, set the env variable `oro_mailchimp.client.member_skip_merge_validation` to *true*.

> Place any configuration variable into the config/config.yml file.

## Extended Merge Vars

Extended Merge Vars is a functionality to add MailChimp Merge Vars.
It is created from the definition of the MarketingList segment.
Merge Vars is equal to the column in the segment definition. It can be used to personalize MailChimp email templates.

During export, it executes the following steps:

- Creates Extended Merge Vars from the segment definition
- Creates MailChimp Merge Vars and exports its values to every MailChimp subscriber on the list

Predefined cart item Merge Vars is added if the segment is built on the Shopping Cart entity. It is currently limited to 3 cart items.

## Known Issues

Email Campaign Statistics and MailChimp Statistics may differ. Email Campaign Statistics is calculated based on the Export API data which at the moment contains only clicks and opens. MailChimp Statistics contains summary statistics for the MailChimp Email Campaign.

#### BUSINESS TIP
## Business Tip

The industrial sector is undergoing a digital transformation. Discover how eCommerce helps in your <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">manufacturing digital transformation</a> journey.

<!-- Frontend -->

**Related Topic**

* [Configure Mailchimp Integration](../../../user/back-office/system/integrations/mailchimp-integration.md#user-guide-mc-integration)
* [Send Email Campaign via Mailchimp](../../../user/back-office/marketing/email-campaigns/sending-email-campaign-via-mailchimp.md#user-guide-mailchimp-campaign)
