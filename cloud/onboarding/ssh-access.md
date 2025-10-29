<a id="public-identity-management-ssh"></a>

#### IMPORTANT
You are viewing the upcoming documentation for OroCloud, scheduled for release later in 2025. For accurate and up-to-date information, please refer only to the documentation of <a href="https://doc.oroinc.com/cloud/" target="_blank">the latest LTS version</a>.

# SSH Access

<!-- begin_include -->

You can connect to OroCloud environment using the SSH console. This can be established only via VPN connection using OpenVPN protocol.

You need to request SSH access to OroCloud environment via the customer support portal. The request should include:

* First and last name(s) of the user(s), and their Organization(s)
* E-mail addresses of the user(s)

Customer users need to have the following clients installed:

* VPN client supporting OpenVPN protocol. See the [Connect to VPN topic](../connect-vpn.md#cloud-connect-vpn) for the list of suitable VPN clients.
* SSH client

Once customer request for SSH connection fulfilled users receives an email with OpenVPN configuration and key. Having this email user must perform the steps outlined in the sections below:

## Reset your password and add an SSH key using Oro Identity Portal

1. Open <a href="https://idp.oro.cloud" target="_blank">Oro Identity Portal</a> and click **Forgot Password**.
   ![Login page to the public identity management](cloud/img/cloud/login_identity_portal.png)
2. Enter your email in the password recovery dialog.
   ![Password recovery dialog](cloud/img/cloud/recovery_dialog.png)
3. Check your mailbox for a message from the ORO Inc IDP Portal ([idp-admin@oro.cloud](mailto:idp-admin@oro.cloud)).
   ![Login page with a pop up prompting to check an email](cloud/img/cloud/email_instructions.png)

   The message contains the following text:

   *Someone has just requested to change the credentials for your OroCloud account. If this was you, please click on the link below to reset them.*

    *<LINK>*

   *This link will expire in 5 minutes.*

   *If you did not mean to reset your credentials, safely ignore this message. No changes will be applied.*
4. Follow the link and set your new password.
   ![Update password flash message](cloud/img/cloud/change_password.png)
5. Enter your personal SSH public key into Oro Identity Portal replacing the stub value created by the portal upon account generation.

   #### WARNING
   The stub SSH public key created with your account has to be replaced with the SSH key that you are going to use for SSH connection. If you do not change the key, you will not be able to log into your servers.
6. Click **Save**.

   You will receive a new email prompting you to confirm the password change.
7. Click on the link in the email to verify your new password and return to Oro Identity Portal.

## Connect to the OroCloud Environment

1. Add VPN config file from the email sent by OroCloud support to your [VPN client configuration](../connect-vpn.md#cloud-connect-vpn).
2. Provide the username and the password specified in Oro Identity Portal.

   #### WARNING
   Do not modify the VPN config.

   ![VPN authentication](cloud/img/cloud/vpn_authentication.png)
3. Use any SSH client of your choice to connect with your OroCloud environment IP or hostname. Your SSH username can be found in Oro Identity Portal; it is the same as the username for OpenVPN.

<!-- finish_include -->
