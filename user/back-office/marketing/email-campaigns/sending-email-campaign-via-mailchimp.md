<a id="user-guide-mailchimp-campaign"></a>

# Send an Email Campaign via Mailchimp

Oro applications support an out-of-the-box integration with Mailchimp, enabling you to:

* Map the Marketing Lists as segments in Mailchimp and keep them synchronized.
* Use existing segments in Mailchimp and import them to the Oro application.
* Schedule importing statistics of the Mailchimp campaigns into Oro Application.

![Sending email campaign via mailchimp](user/img/marketing/marketing/mailchimp/mc_diagram.png)

#### NOTE
To use Mailchimp with the Oro application, ensure that all the necessary integration steps are completed. See [Mailchimp Integration](../../system/integrations/mailchimp-integration.md#user-guide-mc-integration) for more information.

## Prepare Data for the Campaign in Oro

Email campaigns are based on data in marketing lists.

To create a campaign in the Oro application, create a [Marketing List](../marketing-lists/index.md#user-guide-marketing-lists) first. This list will create a segment on the Mailchimp side:

1. Navigate to **Marketing > Marketing Lists > Create Marketing List** in the main menu.
2. Complete the following fields:
   * **Name** — The name used to refer to the marketing list in the system.
   * **Description** — Optional field. Can be filled with text to help you and other users understand the purpose of the list in future.
   * **Entity** — Data to be synchronized into the marketing list will depend on the selected entity.
   * **Type** — The type of marketing list update. *Dynamic* means that all changes you make to your marketing list are automatic. *On Demand*  means that updates are performed manually.
   * **Owner** — Limits the list of users that can manage the marketing list to the users, whose [roles](../../system/user-management/roles/index.md#user-guide-user-management-permissions-roles) allow managing marketing lists of the owner.

   #### IMPORTANT
   You can add multiple columns to your marketing list in Oro, but only First Name, Last Name, and Email details are synced over to Mailchimp.
3. Add email information to the marketing list to send an email campaign via Mailchimp.
   ![Add email field to the columns](user/img/marketing/marketing/mailchimp/o_marketing_list_email.png)
4. Click **Save and Close**.

## Sync Oro Marketing List Data with a Mailchimp Audience

### Mailchimp Side

To create an audience on the Mailchimp side:

1. Login to your Mailchimp account.
2. Click **Audience** in the menu above.
3. In the **Manage Audience** dropdown, select **View audiences**.
   ![In the Manage Audience dropdown, select to view audiences](user/img/marketing/marketing/mailchimp/mc_create_audience.png)
4. Click **Create Audience** on the top right and then **Create Audience** in the popup.
   ![Create a new audience in Mailchimp](user/img/marketing/marketing/mailchimp/create_audience.png)
5. Provide the following information:
   * **List Name** — The name of the list that will be seen by all your subscribers.
   * **Default From Email Address** — Enter the address people can reply to.
   * **Default From Name** — The name that will be displayed as the sender of the email, e.g., name of your company.
   * **Campaign URL Settings** — Choose a verified domain to use in your <a href="https://mailchimp.com/help/customize-email-campaign-urls/?_ga=2.63720488.668787307.1531314044-10372005.1530783947" target="_blank">campaign URLs</a>. You must be authorized to use the domain name you choose.
   * **Remind People How They Signed up to Your List** — Provide meaningful information in the text field, or reuse a reminder from another list, if necessary.
   * **Contact Information for This List** — Enter/edit your contact address information.
   * **Notifications** — Select the notifications to be sent to your provided email.
     * *Daily summary* — Summary of subscribe/unsubscribe activity
     * *One-by-one* — Subscribe notifications as they happen
     * *One-by-one* — Unsubscribe notifications as they happen
   * **Form Settings** — enable double opt in and/or the GDPR fields.
     > * *Enable double opt-in* — Send contacts an opt-in confirmation email when they subscribe to your list.
     > * *Enable GDPR fields* — Customize forms to include GDPR fields.
6. Click **Save** at the bottom of the page.

### Oro Side

To upload subscribers from OroCRM into the newly created Mailchimp audience, synchronize the applications:

1. Open Oro application.
2. Navigate to **System > Manage Integrations** in the main menu.
3. Click on the Mailchimp integration to open its page.
4. Click **Schedule Sync**.

To map contents of the Oro application marketing list to use a segment of the **Subscribers List** in Mailchimp:

1. Navigate to **Marketing > Marketing Lists** in the main menu.
2. Click on the required marketing list to open its details page.
3. Click **Connect to Mailchimp** in the top right corner.
4. Provide **Mailchimp Segment Name**.
5. Select **Mailchimp Integration**.
6. Select **Mailchimp Subscribers List**, the audience that you have created.
7. Click **Connect**.
   ![Map contents of an Oro marketing list to use a segment of the subscribers' list in Mailchimp](user/img/marketing/marketing/mailchimp/o_select_mc_subscribers_list2.png)

Once you are connected, the Mailchimp button is displayed at the top with the following actions in the dropdown:

* **Synchronize** — Start sync manually
* **Connection Settings** — Change connection or integration for the current marketing list in the Oro application
* **Disconnect** — Disconnect the list from the segment

![The marketing list is connected to mailchimp](user/img/marketing/marketing/mailchimp/ml_connected_to_mc.png)

#### NOTE
Please be aware that if a marketing list contains invalid emails, they can be rejected by Mailchimp and excluded from further synchronization.

At this point, if you go back to Mailchimp, you will be able to see data from the Oro application (subscribers’ first and last names and contact details)
synced into your Mailchimp list. Please keep in mind that other information that you may have specified when creating a list on the Oro side, such as dates of
birth or custom details, *are not synced*.

![Columns that will be synced](user/img/marketing/marketing/mailchimp/mc_test_list2.jpg)

## Create a Campaign in Mailchimp

### Select Campaign Type

Now that you have configured the integration with Mailchimp and created a
marketing list, you can create and send an email campaign in Mailchimp:

1. Log into your Mailchimp account.
2. Click **Campaigns** in the main menu.
3. Click **Create Campaign** on the top right.
   ![Create and send campaign on the Mailchimp side](user/img/marketing/marketing/mailchimp/mc_create_campaign.png)
4. Click **Create an Email** in the popup.
   ![The popup dialog in Mailchimp displaying the button to create a new email](user/img/marketing/marketing/mailchimp/new_create_email_camp_mc.png)
5. Select the type of the campaign to send:
   * Regular
   * Automated
   * Plain-text
   * A/B Test

   #### WARNING
   Please note that Oro is unable to receive email campaigns from segments used in automation programs.
6. Enter the campaign name.

## Add Campaign Details

Once you selected the campaign type, provide the following information for the campaign:

![Steps for the campaign in mailchimp](user/img/marketing/marketing/mailchimp/create_campaign_mc_steps.png)
1. **To** — Click **Add Recipients** to select the list segment for the email campaign.
   * **Audience** — Select your marketing list from the dropdown.
   * **Segment or Tag** — Select the marketing list segment or the related tag that you created previously.

     #### NOTE
     Make sure that you send your email campaign to a **segment** of the list, i.e. a selected number of contacts within the entire list of subscribers. Otherwise, the contacts will **not** get synced back to the Oro application.

     **Pre-Built Segments** section of the same page allows you to choose contacts based on subscriber engagement (New Subscribers, Active Subscribers, Inactive Subscribers), or customer behavior (Repeat Customers)  and demographics (available after connection to your store).
   * **Personalize the** *To* **field > Merge Tag** — Select this checkbox to personalize the emails in your campaign. This adds relevance to your emails and helps avoid spam filters. You will be asked to include **Merge Tags** to your email. Merge tags are personalization options. They include the names of the subscribers you want to send your emails to. In the provided field, specify merge tags for your recipients, i.e. \*|FNAME|\* or \*|FNAME|\* \*|LNAME|\*.

Click **Save** to proceed to the next step.

1. **From** — Click **Add From** to provide the sender name and email address.
2. **Subject** — Click **Add Subject** to provide the subject line and preview text for the campaign.

4. **Content** — Click **Design Email** to add content for your email. You will be redirected to a new page to select a pre-set campaign template or
create your own.

> When you have chosen the template that suits you best, go the next page and design your email following the instructions on the page.

> ![Select a template among a pre-set number of campaign templates or create your own](user/img/marketing/marketing/mailchimp/design_campaign_template.png)

> To ensure that your address each of your contacts by name, select **Merge Tags** and **First Name** in the options within **Content** text window. This way, if you type in Hi \*|FNAME|\*, your subscribers will see their first name instead of their email address in the campaign they receive from you.

> Click **Save and Close** and review what you have done before it goes out to your subscribers.

5. In the **Settings and Tracking** you can add the options relevant to your campaign (e.g., track opens, track clicks, etc). If you
wish to promote your email in social media, select **Connect to Twitter** or **Connect to Facebook**.

1. Review campaign details and click **Send** on the top right.
   ![Review campaign details before sending](user/img/marketing/marketing/mailchimp/review_campaign_content.png)
2. Click **Send Now**
   ![Send the email campaign from mailchimp](user/img/marketing/marketing/mailchimp/prepare_for_launch.png)
3. To look at your campaign statistics in the Mailchimp mobile app, click **Track Performance in Our Mobile App** on the same page.
   ![A message informing that the email campaign is sent](user/img/marketing/marketing/mailchimp/campaign_sent.png)

   To do this manually, navigate to **Campaigns > View Report**.
   > ![View the report for a selected campaign](user/img/marketing/marketing/mailchimp/view_report_campaign_mc.png)

   Here, you check out subscriber activity for your newly created email campaign.

## Receive Campaign Statistics on the Oro Side

Once you have sent out your email campaign in Mailchimp, information about your email campaign should have been exported to OroCRM.

As soon as export has been completed, your email campaign should appear in **Marketing > Email Campaigns.** By clicking on your recent campaign,
you will be able to see subscriber activity statistics, such as the number of clicks, bounces, opens, etc. Numbers in each column for each contact define the number of times an action has been performed, e.g., 2 opened, 1 click, 1 unsubscribe. These statistics will help you understand the outcome of your campaign and let you filter contacts for the next one.

![Receive campaign statistics on the Oro application side](user/img/marketing/marketing/mailchimp/o_email_campaign_info.jpg)

#### NOTE
Please note that sometimes Mailchimp’s summary information may not match the OroCRM summary in the same report. This may happen because one set of statistics comes from Mailchimp directly. The other is generated as we receive specific reporting data back about recipients.

For instance, if you need to exclude customers who did not open your email from the next campaign, go to **Marketing > Marketing List> Create New Marketing List.** Fill in the mandatory fields, remembering to include at least one contact column below.

In the [Filters](../../reports-segments/filters.md#user-guide-getting-started-filters) section:

1. Drag **Apply Segment** to the field on the right.
2. Choose the list that you used for your previous campaign.
3. Drag **Field Condition** to set the conditions to the list.
4. Select **Customer User > Marketing Activity > Email Campaign > Email Campaign (Mailchimp Campaign) > Opens.**
5. Select **Field Value.** In our case, it is 0.
   ![Select field value in filters](user/img/marketing/marketing/mailchimp/o_segment_opens_zero.jpg)

   The same way you can apply any conditions of your choice.
6. When you are ready, click **Save and Close**.

This list is now displayed on the [Marketing List Page](../marketing-lists/index.md#user-guide-marketing-lists) and contains contacts sorted according to your conditions.

#### BUSINESS TIP
## Business Tip

Keeping close tabs on the rising digital commerce trend? Make sure to read about a <a href="https://oroinc.com/oromarketplace/b2b-marketplace/" target="_blank">B2B wholesale marketplace</a>, its characteristics, and notable examples.

**Related Articles**

* [Configure Mailchimp Integration](../../system/integrations/mailchimp-integration.md#user-guide-mc-integration)
