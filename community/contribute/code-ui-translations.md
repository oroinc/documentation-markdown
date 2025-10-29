<a id="doc-community-ui-translations"></a>

# Contribute to Translations

Oro applications support localization and internationalization for multiple languages and locales.
All strings that may be translated are defined in the bundle translation domain files and are exposed via the translation management service <a href="https://crowdin.com/join" target="_blank">Crowdin</a> to enable the collaborative translation efforts.

To contribute to Oro translation into your native language:

1. [Join the translation team](#translations-join-the-team).
2. [Submit your translations](#translations-submit).
3. Wait for your translation to be approved.
4. [Ensure that synchronization is enabled for the target language](#translations-language-settings).

[Contact Oro translation team](#translations-contact) if you face any issues (e.g., your translation does not appear in the Oro application after it has been approved).

<a id="translations-join-the-team"></a>

## Join the Translation Team

1. Sign into your Crowdin account or sign up for a new user account if you do not have one yet:
   1. Open <a href="https://crowdin.com/join" target="_blank">Crowdin</a> in your browser.
   2. Sign in using your github or social network account (Facebook, Google+, Twitter).

      Alternatively, create a new Crowdin account: enter your email, user name, password, and password confirmation, and click **Create account**. Follow the link in the confirmation email to activate you account.
2. Open <a href="https://crowdin.com/project/orocommerce" target="_blank">OroCommerce project</a>.

   #### NOTE
   To offer translations for OroCRM and OroPlatform, please use their dedicated translation projects: <a href="https://crowdin.com/project/oro-crm" target="_blank">OroCRM project</a> and <a href="https://crowdin.com/project/oro-platform" target="_blank">OroPlatform project</a>.
3. Select the target language for OroCommerce translation and click **Join** next to the following message: “You must join the translators team to be able to participate in this project”.
4. Type in the reason for joining the translation team (e.g., “As a developer, I would like to enable Korean translation for OroCommerce and my customization”) and click **Join**.
5. Your request will be reviewed by the Oro support team. Upon approval, you will get an email from Crowdin with an invitation to start contributing.

<a id="translations-submit"></a>

## Submit Your Translations

1. To open the translation project, click **Get Involved** in the email from Crowdin that confirms your OroCommerce project team membership.

   Alternatively, use the <a href="https://crowdin.com/project/orocommerce" target="_blank">OroCommerce project</a> link to open the project.
2. Select the target language (e.g. Korean).

   Translations are stored in yaml files organized by bundles (e.g. OroAlternativeCheckoutBundle, OroCatalogBundle) and by groups (e.g. messages, jsmessages).
3. Select the yaml file with the translations you would like to contribute to.
4. Submit your translation. For more information on using Crowdin, please see the <a href="https://support.crowdin.com/crowdin-intro/" target="_blank">Crowdin tutorial</a>.

After you have submitted the translation, it will be queued for proofreading. Other translators can vote for it.

When the translation is approved, it is marked with a green check mark and moved to the end of the list on the translation page. Approved translations are merged (published) to the Oro application translations once a day and become available in Oro application in the language settings (to open the language settings, in the main menu, navigate to **System > Configuration > Language Settings**).

<a id="translations-language-settings"></a>

## Update Translation in Oro Application

1. Navigate to the **System > Localization > Languages** in the main menu.
2. If your target language is not listed, click **Add Language** at the top right corner. Select the target language from the available list in the popup dialog. Click **Add Language** in the bottom right of the dialog.
3. Import the system elements translation from the <a href="https://crowdin.com/join" target="_blank">Crowdin</a> project by clicking the <i class="fas fa-cloud-download-alt" aria-hidden="true"></i> icon at the end of the row and then **Install** in the popup form. The import is available if the status in the **Updates** column is set to **Can be installed** signifying that the corresponding translation has been provided on the Crowdin website.
4. If the status for your target language is *Disabled*, click the <i class="fa fa-check fa-lg" aria-hidden="true"></i> **Enable** icon at the end of the row.
5. If you see *Update is available* in the **Updates** column, click <i class="fas fa-cloud-download-alt" aria-hidden="true"></i> **Update** at the end of the row to update translations from the Crowdin project.

<!-- Frontend -->

<a id="translations-contact"></a>

## Contact Oro Translation Team

In order to report a translation-related issue, please use the <a href="https://crowdin.com/messages/create/12416174/21370" target="_blank">contact</a> link in the **Owner** section on the <a href="https://crowdin.com/project/orocommerce" target="_blank">OroCommerce project</a> in Crowdin.

Please do not hesitate to contact us from Crowdin if:

* Your translation has been marked as approved for over one day but has not appeared in the Oro application
* Your translation is still not approved after more than seven days of review.
* You would like to help proofread a target language.
* You have any other questions and issues related to translations that are not covered in Oro documentation and the Crowdin tutorial.

**See Also**

* [Version Control](code-version-control.md#code-version-control)
* [Code Style](code-style.md#doc-community-code-style)
* [Set Up a Development Environment](../../backend/setup/dev-environment/index.md#doc-dev-env-best-practices)
* [Contribute to Documentation](documentation.md#documentation-standards)
* [Report an Issue](../report-issues/code.md#doc-community-issue-report)
* [Report a Security Issue](../report-issues/security.md#reporting-security-issues)
* [Contact Community](../index.md#doc-community-contact-community)
* [Release Process](../release-process.md#doc-community-release)

<!-- fa-bars = fa-navicon -->
<!-- Ic Tiles is used as Set As Default in saved views, and as tiles in display layout options -->
<!-- IcPencil refers to Rename in Commerce and Inline Editing in CRM -->
<!-- Check mark in the square. -->
<!-- SortDesc is also used as drop-down arrow -->
