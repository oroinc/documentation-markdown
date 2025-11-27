<a id="user-guide-hangouts"></a>

# Configure Voice and Video Calls via Hangouts in the Back-Office

#### WARNING
Google has retired Google Hangouts and associated services, and this integration is no longer supported.

Oro application’s integration with Google Hangouts enables you to make Hangouts voice or video calls from within your Oro application, providing an advantage for sales and support teams by helping them connect with customers directly. You can make voice calls to a single phone number, or launch a audio/video conference with up to 5 participants. Call data is logged automatically, including any notes made during the call.

For the integration between Hangouts and your Oro application to be successful, make sure you:

* Have an active Google account (if you try using the feature when not logged in, you will be prompted to log-in)
* If you are using a browser other than Chrome, install a Google Hangout or Google Talk extension for the browser.
* If you are going to call phone-numbers beyond USA and Canada, make sure you have funds in your Google Wallet.

## Configure the Integration

#### NOTE
Google Hangouts are configured globally and [per organization](../../../../user-management/organizations/org-configuration/general-setup-org/integrations/organization-google.md#user-guide-hangouts-org).

To enable the integration in the Oro application on the global level:

1. Navigate to the **System > Configuration** in the main menu.
2. Click **Integrations > Google Settings** in the panel to the left.
3. In the **Google Hangouts** section, select the following checkboxes:
   * **Enable for Emails** — to call via email (you can invite up to 5 users to a Google Hangout by emailing them)
   * **Enable for Phones** — to make phone calls

   ![image](user/img/system/integrations/google/enable.png)

## Initiate a Hangout Call

### Call from a Record Page

In order to start a hangout call from the page of a record:

1. Navigate to the page of the record that you need to contact (account, lead, contact, user, etc.) .
2. Hover the mouse over a phone number or an email address on the page.
   ![Hangout icon on a contact record page](user/img/system/integrations/google/hover.png)
3. Click the hangouts icon.
4. In the **Invite Contacts to a Google Hangout** form , click **Start a Hangout**.
   ![Invite Contacts to a Google Hangout form](user/img/system/integrations/google/invite.png)
5. If you have already logged into your Google account, the call starts immediately, otherwise you will be prompted to log in.

<a id="user-guide-hangouts-call"></a>

### Call a Phone Number

If you call your contact via their phone number, and the telephone calling has been enabled for your Google Hangouts,
the call will start immediately.

Otherwise, you will be prompted to enable it:

![image](user/img/system/integrations/google/enable_phone.png)

Most calls within the USA and Canada are free, and you can pay your balance for other regions using Google Wallet.

### Call via Email

If you call via email, the call is initiated. You can invite other call participants (up to 5 total),
remove them (click **X** next to the name) or send them a link to the session.

![image](user/img/system/integrations/google/invite_more.png)

Once the contact has joined the session, you can talk.

### Call via the Log Call Form

To make calls from the [Log Call](../../../../../activities/calls/index.md#doc-activities-calls) form, click **Start a Hangout** in the bottom right corner.

![image](user/img/system/integrations/google/log_call_hangout.png)

### Call from the Calendar Page

To start a Hangout call with contacts invited to an event:

1. Navigate to your [calendar](../../../../../activities/calendar-events/index.md#doc-activities-events) (or the calendar widget on the dashboard).
2. Click the event name.
3. If the event has at least one guest invited, the **Start a Hangout** button is displayed.
   ![image](user/img/system/integrations/google/view_event.png)
4. Click **Start a Hangout** to start a call using the email addresses of the first five guests.

<!-- stop -->

**Related Topics**

* [Activities: Calls](../../../../../activities/calls/index.md#doc-activities-calls)
* [Configure Global Google Settings](index.md#admin-configuration-integrations-google)
* [Configure Google Integration Settings](google-integration.md#system-configuration-integrations-google)
* [Configure Google Single Sign On](google-single-sign-on.md#user-guide-google-single-sign-on)
* [Configure Google Tag Manager Integration](../../../../integrations/gtm/index.md#gtm-ga-4-integration)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
