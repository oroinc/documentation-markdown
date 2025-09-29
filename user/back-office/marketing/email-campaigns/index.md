<!-- updated on 06 July 2017 -->

# Manage Email Campaigns in the Back-Office

With Email Campaigns in Oro application, you can send an email with birthday wishes and a special offer to all of your loyal customers who were born in June or deliver a compliment to every customer who has purchased from you since April.

Before you start using Email campaigns, prepare your contact sources (e.g. a [marketing list](../marketing-lists/index.md#user-guide-marketing-lists)) and create an [Email Template](../../system/emails/email-templates.md#user-guide-email-template).

After that, you can easily set-up an Email Campaign, within which all the contacts on the list will
receive personalized emails.

This article describes how to set up an Email Campaign in Oro application and manage it.

<a id="user-guide-email-campaigns-create"></a>

## Create an Email Campaign

To create a new email campaign:

1. Navigate to **Marketing > Email Campaigns** in the main menu.
2. Click **Create Email Campaign** in the top right corner to get
   to the *Create Email Campaign* page.
3. In the *General* section, provide the following information:

   | **Name**             | **Description**                                                                                                                                                                                                                                                                                                                                             |
   |----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Name\***           | Name used to refer to the campaign in the system.                                                                                                                                                                                                                                                                                                           |
   | **Marketing List\*** | Choose one of available marketing lists. The letter will be sent to email addresses defined by<br/>the list.<br/>More details about the marketing lists are available in the [Marketing Lists](../marketing-lists/index.md#user-guide-marketing-lists)<br/>guide.                                                                                           |
   | **Schedule\***       | Defines whether the mailing shall be activated manually (*Manual*) or scheduled for a specific<br/>date (*Deferred*).<br/><br/>If *Deferred* is chosen, the **Scheduled For** field will appear. Choose the date and time of the mailing in the<br/>calendar.<br/><br/>![email_campaign_schedule](user/img/marketing/marketing/email_campaign_schedule.png) |
   | **Owner\***          | Limits the list of users that can manage the campaign to those,  whose<br/>roles allow managing<br/>email campaigns of the owner (e.g. the owner, members of the same business unit, system administrator, etc.).                                                                                                                                           |
   | **Sender Email**     | Optional.                                                                                                                                                                                                                                                                                                                                                   |
   | **Sender Name**      | Optional.                                                                                                                                                                                                                                                                                                                                                   |
   | **Campaign**         | Optional. A [Marketing Campaign](../marketing-campaigns/index.md#user-guide-marketing-campaigns) this email campaign is part of.                                                                                                                                                                                                                            |
   | **Description**      | Optional.                                                                                                                                                                                                                                                                                                                                                   |

   #### NOTE
   Custom fields may be added, subject to specific business needs.
4. In the **Mailing Settings** section, select the transport and the email template to use for the email campaign.

   | **Name**   | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Transport  | The field defines the service to be used for the mailing. Out of the box, the only option is Oro application.<br/>Other services can be added in the course of customization.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
   | Template   | Choose the [email template](../../system/emails/email-templates.md#user-guide-email-template) to be used from the drop-down.<br/><br/>#### NOTE<br/>You can only see the templates assigned to no entity or the same entity as the marketing list.<br/><br/>#### IMPORTANT<br/>Keep in mind that the ability to view and add email templates from the dropdown list depends on specific roles and permissions defined in the system configuration. For example, with the User permissions, you can view and add the templates created by you exclusively. The Business Unit permissions give the access to the email templates created by any user who belongs to the same business unit as you. For more information about available access levels and permissions, see the [Understand Roles and Permissions](../../system/user-management/roles/index.md#user-guide-user-management-permissions-roles) guide. |
5. Once you finish configuring the marketing campaign, click **Save and Close** in the top right corner of the page.
   ![View the Create Email Campaign page](user/img/marketing/marketing/email_campaign_send.png)

<a id="user-guide-email-campaigns-plus-marketing"></a>

### Assign an Email Campaign to a Marketing Campaign

If you want to include one or several email campaign(s) to an
[Oro Application Marketing Campaign](../marketing-campaigns/index.md#user-guide-marketing-campaigns), choose the Marketing Campaign name in the Campaign list.

Multiple email campaigns may be assigned to a marketing campaign.

<a id="user-guide-email-campaigns-actions"></a>

## Manage Email Campaign Records

The following actions are available for an email campaign from the grid:

- Delete the campaign from the system: <i class="fas fa-trash-alt" aria-hidden="true"></i>
- Edit the campaign: <i class="fa fa-edit fa-lg" aria-hidden="true"></i>
- View the details of the campaign: <i class="fa fa-eye fa-lg" aria-hidden="true"></i>

<a id="user-guide-email-campaigns-send"></a>

## Send an Email Campaign Manually

To launch an email campaign:

1. Navigate to **Marketing > Email Campaigns** in the main menu.
2. Click on the Email Campaign to preview its contents.
3. Review the recipients list to ensure it covers only the planned target contacts.
4. Click the **Send**.

This generates an email based on the template you’ve selected, populates it with the contact’s details and sends it to the email from the contact information.

#### NOTE
If an Email Campaign has been created as a result of integration with [Mailchimp](../../system/integrations/mailchimp-integration.md#user-guide-mc-integration) or
[dotmailer](../../system/integrations/dotmailer/index.md#user-guide-dm-integration), its record will be automatically created in Oro application, and related statistics will be uploaded and synchronized.

<!-- stop -->
<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
