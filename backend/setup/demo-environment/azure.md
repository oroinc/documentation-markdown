<a id="demo-environment-azure"></a>

# Azure Cloud Platform

Azure Marketplace enables you to deploy pre-configured demo instances of the latest LTS releases of OroCRM and OroCommerce Community Editions with or without demo data.

To proceed with the installation, make sure you have registered with Azure marketplace and have a valid <a href="https://portal.azure.com" target="_blank">Azure portal account</a>.

## Deploy the Solution

To deploy the solution, follow the steps below:

1. Navigate to <a href="https://azuremarketplace.microsoft.com/en-us/marketplace/" target="_blank">Azure Marketplace</a> and search for the required Oro application (OroCRM VM or OroCommerce VM) in the search bar.
   ![OroCRM VM or OroCommerce VM in Azure Marketplace search dropdown](img/backend/setup/azure/search.png)
2. Once you selected the type of the application to deploy, click **GET IT NOW** under the application logo on your left.
3. In the pop-up dialog, select the software plan – an instance with or without demo data. The application with demo data provides all the necessary information for you to test the application, such as a preconfigured list of customers, products, submitted orders, quotes, the structured master and web catalogs.
   ![Select the software plan pop up dialog](img/backend/setup/azure/software-plan.png)
4. Click **Continue**.

   You are redirected to Azure Portal to complete the installation.
   At this point, you are asked to log into Azure Portal if you have not already done so.
5. Once again, select the type of the application to deploy.
6. Click **Create**.
   ![Create a virtual machine of the selected type](img/backend/setup/azure/create-vm.png)
7. Complete the required fields in the **Basics** tab:
   * *Subscription* - Select your subscription type
   * *Resource Group* - Create a new resource group, or select an existing one.

     A resource group is a container that holds related resources for an Azure solution. Resource group names only allow alphanumeric characters, periods, underscores, hyphens and parenthesis and cannot end in a period.
   * *Virtual Machine Name* - Provide a virtual machine name.

     Virtual machines in Azure have two distinct names: a virtual machine name used as the Azure resource identifier and in the guest host name. When you create a VM in the portal, the same name is used for both the virtual machine name and the host name. The virtual machine name cannot be changed after the VM is created. You can change the host name when you log into the virtual machine.

   ![Creating a VM - Basics tab](img/backend/setup/azure/basics-1.png)
   * *Region* - Choose your region, e.g., (US) East US
   * *Availability Options* - Set to *No infrastructure redundancy required*
   * *Image* - Choose the base operating system or application for the virtual machine, e.g. OroCommerce with demo data VM
   * *Size* - Select a VM size to support the workload that you want to run. The size that you choose then determines factors such as processing power, memory, and storage capacity.
   * *Authentication type* - Choose whether to use password or SSH public key for authentication.
     * For *password*, complete fields Username, Password, Confirm password
     * For *SSH public key*, complete fields Username and SSH public key

   ![Creating a VM - Basics tab (continued)](img/backend/setup/azure/basic-2.png)
8. Click **Next:Disks**. The fields in the next step are predefined with demo data.
   ![Creating a VM - Disks tab](img/backend/setup/azure/disks.png)
9. Click **Next:Networking**. The fields in the next step are predefined with demo data.
   ![Creating a VM - Networking tab](img/backend/setup/azure/networking.png)
10. Click **Next:Management**. The fields in the next step are predefined with demo data.
    ![Creating a VM - Management tab](img/backend/setup/azure/management.png)
11. Click **Next:Advanced**. The fields in the next step are predefined with demo data.
    ![Creating a VM - Advanced tab](img/backend/setup/azure/advanced.png)
12. Click **Next:Tags**. The fields in the next step are predefined with demo data.
    ![Creating a VM - Tags tab](img/backend/setup/azure/tags.png)
13. Click **Next:Review+create**. The fields in the next step are predefined with demo data.

    You should see **Running Final Validation**, followed by **Validation Passed**.
    ![Creating a VM - Validation](img/backend/setup/azure/validation.png)
14. Click **Create** at the bottom.
15. Track the deployment process in the notification dialog.
    ![Tracking deployment progress in the notifications bar](img/backend/setup/azure/deployment.png)
16. Make sure that the deployment is completed successfully, and click **Go to resource**.
    ![Deployment complete notification](img/backend/setup/azure/deployment-complete.png)
17. Click **DNS name: Configure**, and fill DNS name label.
    ![Configure DNS](img/backend/setup/azure/dns.png)
18. Click **Save**.
    ![Save DNS config](img/backend/setup/azure/dns-config.png)
19. Return to the virtual machine and refresh the page.
    ![Click on the VM name to return to its details page](img/backend/setup/azure/return.png)
20. Next to the DNS Name, click **Copy to Clipboard**.
    ![Copy DNS to clipboard](img/backend/setup/azure/copy-dns.png)
21. Paste the DNS into the address bar of a new browser window, and add  */admin* to the URL (e.g., http://<DNSprefix>.cloudapp.azure.com/admin).
    ![Paste the DNS into the address bar](img/backend/setup/azure/dns-url.png)

    The Oro application interface should now be displayed.
    ![OroCommerce startup page](img/backend/setup/azure/admin-startup.png)

    #### IMPORTANT
    **OroCRM VM Demo Data**: If you have deployed OroCRM VM with demo data, use **admin** as login and the password to access the back-office of the application. To access the application via SSH, specify your username and password/public key, and restart services (systemctl restart oro\*).

    **OroCommerce VM Demo Data**: If you have deployed OroCommerce VM with demo data, use *AmandaRCole@example.org* both as your login and password to access the storefront (http://<DNSprefix>.cloudapp.azure.com). To access the back-office of the application (http://<DNSprefix>.cloudapp.azure.com/admin/admin), use *admin* as login and password. To access the application via SSH, specify your username and password, or a public key, and restart services (systemctl restart oro\*).

## Configure Application URL

For the demo applications to work correctly, you need to configure the application URL (for OroCRM and OroCommerce), and Secure URL and URL (for OroCommerce).

1. Navigate to **System Configuration > General Setup > Application Settings** in the application back-office, and provide the *Application URL* (e.g., http://<DNSprefix>.cloudapp.azure.com, or a different domain).
   ![Change application URL in the configuration settings](img/backend/setup/azure/change-app-url.png)

1. (*For OroCommerce only*) Navigate to **System Configuration > Websites > Routing** in the application back-office, and provide *Secure URL* and *URL*.
   ![Change secure url and url in the website routing configuration](img/backend/setup/azure/secure-url.png)
2. Return to the Azure Portal, and reboot the virtual machine.
   ![Restart VM](img/backend/setup/azure/restart-vm.png)

   Follow the progress of the restart in the notification bar on your top right.
3. Copy and paste the DNS into the address bar of a new browser window and press Enter.

   If you have deployed the OroCommerce application, the storefront should now be displayed.

   #### NOTE
   Due to <a href="https://docs.microsoft.com/en-us/archive/blogs/azuresecurity/pro-tip-on-sending-email-from-azure-virtual-machines-to-external-domains" target="_blank">Azure blocking port 25</a>, we recommend configuring SMTP settings once you install the application if you would like to send messages from the Oro application you have deployed.

   ![DNS in the URL for storefront](img/backend/setup/azure/dns-storefront.png)

<!-- Frontend -->
