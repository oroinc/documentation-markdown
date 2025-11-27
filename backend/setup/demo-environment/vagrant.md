<a id="vagrant-installation"></a>

# Vagrant Provision

To get familiar with the application functionality, you can install Oro applications with
environment components using <a href="https://www.vagrantup.com/" target="_blank">Vagrant</a>.

Every Oro application has a *Vagrantfile* that enables you to set up a virtual machine with the Oro application via the
vagrant up command.

For example, to set up a VM with OroCommerce CE application v. 5.1.0 locally, run:

```none
git clone -b 5.1.0 https://github.com/oroinc/orocommerce-application.git oroapp && cd oroapp
vagrant up
```

Once the command has run, you can access the application via the `http://localhost.dev.oroinc.com:8000/` URL.

The environment in the resulting VM and the provisioning steps in the Vagrantfile replicate the process described in the [Setup Application Environment Guide](../dev-environment/index.md#dev-guide-development-practice-setup-dev-env-setup-env) and the [Installation Guide](../installation.md#installation).

For more details on preparing the virtual platform for the virtual machine, please see the [Installation and Configuration]() section below.

## Installation and Configuration

### Requirements

* Windows, macOS, Linux, or any other OS supported by Virtualbox and Vagrant
* 4096M available RAM on your PC

### Installation Steps

Start by installing the required software:

1. <a href="https://www.virtualbox.org/wiki/Downloads" target="_blank">Install VirtualBox</a>.
2. <a href="https://developer.hashicorp.com/vagrant/docs/installation/" target="_blank">Install Vagrant</a>.
3. <a href="https://www.atlassian.com/git/tutorials/install-git" target="_blank">Install Git.</a>

When you have installed VirtualBox, Vagrant, and Git, do the following:

1. Get the Oro application source code:
   ```none
   git clone -b 5.1.0 <oro_application_clone_url> oroapp && cd oroapp
   ```

   Replace the <oro_application_clone_url> with the repository URL for the necessary Oro application:

   | OroCommerce Community Edition                | [https://github.com/oroinc/orocommerce-application](https://github.com/oroinc/orocommerce-application)                                   |
   |----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
   | OroCommerce Community Edition for Germany    | [https://github.com/oroinc/orocommerce-application-de](https://github.com/oroinc/orocommerce-application-de)                             |
   | OroCommerce Enterprise Edition               | [https://github.com/oroinc/orocommerce-enterprise-application](https://github.com/oroinc/orocommerce-enterprise-application)             |
   | OroCommerce Enterprise Edition for Germany   | [https://github.com/oroinc/orocommerce-enterprise-application-de](https://github.com/oroinc/orocommerce-enterprise-application-de)       |
   | OroCommerce Enterprise Edition (without CRM) | [https://github.com/oroinc/orocommerce-enterprise-nocrm-application](https://github.com/oroinc/orocommerce-enterprise-nocrm-application) |
   | OroCRM Community Edition                     | [https://github.com/oroinc/crm-application](https://github.com/oroinc/crm-application)                                                   |
   | OroCRM Enterprise Edition                    | [https://github.com/oroinc/crm-enterprise-application](https://github.com/oroinc/crm-enterprise-application)                             |
   | OroPlatform Community Edition                | [https://github.com/oroinc/platform-application](https://github.com/oroinc/platform-application)                                         |
   | OroCommerce Platform                         | [https://github.com/oroinc/orocommerce-platform-application](https://github.com/oroinc/orocommerce-platform-application)                 |

   #### NOTE
   You can download and unpack the archive with the Oro application source code instead of using the Git repository. For more information, please see [Get the Oro Application Source Code](../get-source-files.md#installation-get-files).
2. Configure and run the virtual machine using Vagrant:

   For Community Editions of the Oro Applications run:
   ```none
   vagrant up
   ```

   for the Enterprise Editions of Oro applications, specify the following environment variables:
   - **gittoken** - <a href="https://github.com/settings/tokens" target="_blank">Github token</a> use it to install Oro application dependencies
   - **licence** - Enterprise Licence key for your Oro Application
   - **licencestart** - Enterprise License Start Day key for your Oro Application. The value format is YYYY-MM-DD, f.e. 2022-02-24.

   for Linux bash example:
   ```none
   gittoken=YourGithubToken licencestart=YourEnterpsiseLicenceKeyStartDay 2licence=YourEnterpsiseLicenceKey vagrant up
   ```

   for Windows PowerShell terminal example:
   ```none
   $env:licence = "YourEnterpsiseLicenceKey"; $env:gittoken = "YourGithubToken"; vagrant up
   ```

   #### NOTE
   At the first start, vagrant will ask you to install the required vagrant-env plugin. You must agree (press Y) and repeat the command vagrant up.

   Once the command execution is complete and the setup is finished, you can use the Oro application.

   #### NOTE
   When you run vagrant up for the first time, the Oro application installation may take some time, as the following time-consuming provisioning steps happen:
   > * InstallBaseSystem - Base Oracle Linux 8 box download. Upgrade and install docker and docker compose plugin
   > * Build - Run composer install for the Oro application in docker. Create docker image
   > * Install - Oro application installation; note that loading demo data takes extra time.
   > * Deploy - Deploy application

   The total time for the environment to get up and running depends on multiple factors, such as internet connection speed, CPU frequency, etc. It usually takes from 1- to 15 minutes.

   #### NOTE
   You can re-run all or one of the required steps. For example, if the application code has changed, then you need to restart 3 steps: - Build, Install, Deploy.

   ```none
   vagrant provision --provision-with Build,Install,Deploy
   ```

### Customize Installation Process

To customize the default installation settings, add the required variables in .env-build.

**Application settings**

```none
ORO_USER_NAME=admin
ORO_USER_PASSWORD=admin
ORO_USER_FIRSTNAME=John
ORO_USER_LASTNAME=Doe
ORO_USER_EMAIL=admin@example.com
ORO_SAMPLE_DATA=n                # y | n (whether to perform loading demo data during installation)
ORO_ORGANIZATION_NAME=ORO
ORO_LANGUAGE=en
ORO_FORMATTING_CODE=en_US
ORO_APP_DOMAIN=localhost.dev.oroinc.com
```

To customize the application hostname:

* Set the new ORO_APP_DOMAIN parameter value in the .env-build (e.g., yourdomain.local)
* Map the new hostname to the application host IP address in your local <a href="https://en.wikipedia.org/wiki/Hosts_(file)" target="_blank">hosts</a>  file, like in the following examples:
  ```none
  192.168.56.10 yourdomain.local www.yourdomain.local
  ```

Now you can open the Oro application in a browser via the `http://yourdomain.local/` URL.

### Running Multiple Virtual Machines

To run multiple virtual machines simultaneously on a single host, ensure that every virtual instance uses a unique forwarded port. Before running an additional instance, modify its forwarded port in the *host* section of the *config.vm.network “forwarded_port”* setting in the Vagrant file. You can increment the value for every new virtual instance, e.g., **instance A** can have *config.vm.network “forwarded_port”, guest: 80, host: 8000* configuration, and **instance B** can have *config.vm.network “forwarded_port”, guest: 80, host: 8001*. Also you should change port in variable ORO_WEBSOCKET_FRONTEND_DSN=//\*:8000/ws for websocket frontend.

### Access the Installed Oro Application

Once the VM setup has finished, you can access the application in your browser with the credentials defined by your installation configuration.

The default login details are:

* *Application Storefront URL*: `http://localhost.dev.oroinc.com:8000/`
* *Application Admin UI URL*: `http://localhost.dev.oroinc.com:8000/admin/`
* *Admin Login*: admin
* *Admin Password*: admin

If you have changed the application host, admin login, or password, please refer to the .env-build for these details.

### Shared Working Directory

Vagrant maps the working directory on your host machine to the  */vagrant* directory in the virtual machine file system.
Once the VM is up, any changes to the files in the host working directory are applied to the  */vagrant* directory in the virtual machine file system, and vice versa. To update the application, you need to run the provision steps Build, Install, Deploy again.

```none
vagrant provision --provision-with Build,Install,Deploy
```

### SSH Access to the Virtual Machine

To connect to the virtual machine via SSH, run the following command in the working directory on your host machine:

```none
vagrant ssh
```

You will be logged in to the virtual machine as *vagrant* user with *sudo* permission (you do not need a password to use the *sudo* command).

To configure SSH access to the virtual machine for the utilities that run on the host machine, like IDE, get the explicit SSH credentials by running the following command:

```none
vagrant ssh-config
```

### Vagrant Сommands

* vagrant up – Creates and configures the virtual machine according to the Vagrantfile. Unless vagrant destroy has been launched on consecutive runs, vagrant up powers on the virtual machine. The provisioning scripts run only once.
* vagrant provision –provision-with Build,Install,Deploy –  Run provisioning scripts defined in the Vagrantfile.
* vagrant halt – Stops the virtual machine and saves the virtual machine image (without the current RAM state) to the host hard drive.
* vagrant suspend – Stops the virtual machine and saves the virtual machine image and the current RAM state on the host hard drive.
* vagrant resume – Resume the suspended virtual machine.
* vagrant destroy – Destroys the virtual machine and frees the host machine’s resources.

For more information, please see the <a href="https://developer.hashicorp.com/vagrant/docs/" target="_blank">official Vagrant documentation</a>.

<!-- Frontend -->
