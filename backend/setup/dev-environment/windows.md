<a id="setup-dev-env-docker-symfony-windows"></a>

# Set up Environment for OroPlatform Based Application on Windows Subsystem for Linux (WSL) 2

This guide demonstrates how to set up [Docker and Symfony Server development stack](docker-and-symfony/index.md#setup-dev-env-docker-symfony) for Oro applications on Windows 10, version 1903 or higher. Please make sure you have the latest version of the Windows OS before you start.

## Environment Setup

1. Install <a href="https://apps.microsoft.com/detail/9pdxgncfsczv?hl=en-US&gl=US" target="_blank">a supported Ubuntu LTS release</a> for WSL 2. Run the following command from Windows PowerShell or Windows Terminal:
   ```powershell
   wsl --install -d Ubuntu
   ```

   To verify that the distribution is using WSL 2, run:
   ```powershell
   wsl --list --verbose
   ```

   If the Ubuntu distribution is using WSL 1, upgrade it to WSL 2 by running:
   ```powershell
   wsl --set-version <distribution-name> 2
   ```

   Replace `<distribution-name>` with the name of your installed distribution as shown by `wsl --list --verbose`.
2. Install <a href="https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701" target="_blank">Windows Terminal</a>. While not required, we recommend using it as it comes with the built-in WSL integration. Run Windows Terminal as an administrator. You may be prompted to reboot your PC after installation.
   ![An example of a successful installation of Windows Terminal](img/backend/setup/wsl/terminal-successfull-installation.png)

   If you encounter an error during installation, please follow the link provided in the terminal to troubleshoot the issue or refer to the <a href="https://docs.microsoft.com/en-us/windows/wsl/install" target="_blank">official Microsoft WSL documentation</a>:
   ![An example of an error during terminal installation](img/backend/setup/wsl/terminal-error.png)

   Once rebooted, create a new UNIX username and password to log into Ubuntu.
   ![An example of terminal messages displayed once you log into ubuntu](img/backend/setup/wsl/logged-in-ubuntu.png)

   To switch to Ubuntu on your Windows Powershell, click on the drop-down next to the **+** tab and select Ubuntu from the list.
   ![Ubuntu option in the PowerShell drop-down](img/backend/setup/wsl/powershell-ubuntu-dropdown-list.png)

   To avoid switching to Ubuntu manually every time, you can set up your Windows PowerShell to run Ubuntu by default on startup. For this, navigate to your Windows settings > Startup and change the **Default Profile** to *Ubuntu*, as illustrated in the screenshot below:
   ![Change default terminal profile to Ubuntu](img/backend/setup/wsl/ubuntu-on-powershell.png)

   As WSL integration does not always work well with the Windows file system, go to the Linux file system by typing in `cd` in the terminal:
   ![An example of switching to the Linux file system](img/backend/setup/wsl/switch-to-linux-filesystem.png)
3. Install <a href="https://docs.docker.com/docker-for-windows/install/" target="_blank">Docker Desktop for Windows</a>. After the installation is complete, open Docker Desktop and verify that **Settings > General > Use the WSL 2 based engine** is enabled. Reboot your PC if prompted during the installation.
   ![Docker Desktop installation](img/backend/setup/wsl/docker-installation-wsl2.png)
4. Enable <a href="https://docs.docker.com/docker-for-windows/wsl/" target="_blank">Docker Desktop WSL 2 backend</a> for the Ubuntu distribution that you installed in step 1.
   * In the **General Settings** of the Docker application, make sure that *Use the WSL 2 based engine* option is selected.
   * In **Resources > WSL Integration**, enable WSL integration for the Ubuntu distribution and restart Docker Desktop.

   ![Configure WSL 2 on the docker side](img/backend/setup/wsl/docker-wsl2-config.png)
5. Log into the Ubuntu distribution using Windows Terminal. Run all remaining commands in the Ubuntu terminal unless instructed otherwise.
6. Install PHP 8.5 and the required extensions in Ubuntu:

   #### HINT
   It is recommended to run all commands one by one to make sure they exit successfully and avoid missing potential warnings. If you have unreliable connection leading to command failure, please rerun it.

   ```none
   sudo apt install software-properties-common
   sudo add-apt-repository -y ppa:ondrej/php
   sudo apt update
   sudo apt -y install php8.5 php8.5-fpm php8.5-cli php8.5-pdo php8.5-mysqlnd php8.5-xml php8.5-soap php8.5-gd php8.5-zip php8.5-intl php8.5-mbstring php8.5-curl php8.5-bcmath php8.5-ldap php8.5-pgsql php8.5-mongodb
   ```

> You will be prompted to type in your password as you are running the commands as a sudo user.
1. Configure PHP:
   ```none
   echo -e "memory_limit = 2048M \nmax_input_time = 600 \nmax_execution_time = 600 \nrealpath_cache_size=4096K \nrealpath_cache_ttl=600 \nopcache.enable=1 \nopcache.enable_cli=0 \nopcache.memory_consumption=512 \nopcache.interned_strings_buffer=32 \nopcache.max_accelerated_files=32531 \nopcache.save_comments=1" | sudo tee -a  /etc/php/8.5/fpm/php.ini
   echo -e "memory_limit = 2048M" | sudo tee -a  /etc/php/8.5/cli/php.ini
   ```
2. Install Node.js 24:
   ```none
   sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
   curl -sL https://deb.nodesource.com/setup_24.x | sudo -E bash -
   sudo apt -y install nodejs
   ```
3. Install PNPM 10 Using NPM:
   ```none
   npm install -g pnpm@latest-10
   ```

   #### NOTE
   If the installation fails because of insufficient permissions, rerun the command with `sudo`.
4. Install Composer:

> ```none
> php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php
> php -r "unlink('composer-setup.php');"
> sudo mv composer.phar /usr/bin/composer
> ```
1. Install Symfony Server:
   ```none
   sudo apt -y install libnss3-tools
   wget https://get.symfony.com/cli/installer -O - | bash
   echo 'export PATH="$HOME/.symfony5/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   symfony server:ca:install
   ```

   You can also enable TLS, but as Symfony Server does not automate certificate installation for WSL on Windows, you have to copy the generated certificate manually from the `/usr/local/share/ca-certificates/` folder to the host filesystem and install it manually to your web browser:
   ![An illustration of copying the generated certificate manually from the ``/usr/local/share/ca-certificates/`` folder to the host filesystem](img/backend/setup/wsl/symfony-certificate-1.png)

   An example of importing a certificate in Chrome:
   ![Opening certificates in Chrome settings](img/backend/setup/wsl/chrome-certificates-2.png)![Importing certificate to Chrome](img/backend/setup/wsl/import-certificate-3.png)
2. Configure the network. WSL 2 changes the way networking is configured compared to WSL 1. You must enable traffic proxying to permit traffic through the Windows firewall.

   Before you continue, open **PowerShell** as an administrator. Right-click **PowerShell** and select **Run as administrator**, or run the following command from a terminal to launch an elevated PowerShell window:
   ```powershell
   Start-Process powershell -Verb RunAs
   ```

   Approve the User Account Control (UAC) prompt when prompted. The `netsh interface portproxy` and `netsh advfirewall` commands require administrator privileges.

   Run the following command in Ubuntu to obtain the IP address of the WSL 2 virtual machine:
   ```bash
   ip addr | grep eth0
   ```

   ![IP address of WSL 2 virtual machine](img/backend/setup/wsl/ip-addr-ubuntu.png)

   Map the WSL 2 port to the internal host:
   ```powershell
   netsh interface portproxy add v4tov4 listenport=8000 listenaddress=0.0.0.0 connectport=8000 connectaddress=172.22.33.170
   ```

   #### NOTE
   The IP address assigned to the WSL 2 virtual machine can change after Windows or WSL restarts. If the forwarded port stops working, obtain the current IP address again and update the `connectaddress` value in the `netsh interface portproxy` command.

   Configure Windows Defender Firewall, as illustrated below:
   ![Configure Windows Defender Firewall step 1](img/backend/setup/wsl/firewall-1.png)![Configure Windows Defender Firewall step 2](img/backend/setup/wsl/firewall-2.png)![Configure Windows Defender Firewall step 3](img/backend/setup/wsl/firewall-3.png)![Configure Windows Defender Firewall step 4](img/backend/setup/wsl/firewall-4.png)![Configure Windows Defender Firewall step 5](img/backend/setup/wsl/firewall-5.png)![Configure Windows Defender Firewall step 6](img/backend/setup/wsl/firewall-6.png)
3. Restart the terminal and the web browser to get them ready.

## What’s Next

* [Tips and Recommendations](docker-and-symfony/index.md#setup-dev-env-docker-symfony-recommendations)
* [Installation of the Oro Application via the Command-Line Interface](docker-and-symfony/index.md#setup-dev-env-docker-symfony-install-application)
* Consider using the Visual Studio Code or PhpStorm with the built-in WSL integration for development.

<!-- Frontend -->
