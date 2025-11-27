<a id="setup-dev-env-docker-symfony-ubuntu"></a>

# Set up Environment for OroPlatform Based Application on Ubuntu 24.04

This guide demonstrates how to set up [Docker and Symfony Server development stack](docker-and-symfony/index.md#setup-dev-env-docker-symfony) for Oro applications on Ubuntu 24.04 LTS.

## Environment Setup

1. Install PHP 8.3 with all required extensions:
   ```none
   sudo apt install software-properties-common
   sudo add-apt-repository -y ppa:ondrej/php
   sudo apt update
   sudo apt -y install php8.3 php8.3-fpm php8.3-cli php8.3-pdo php8.3-mysqlnd php8.3-xml php8.3-soap php8.3-gd php8.3-zip php8.3-intl php8.3-mbstring php8.3-opcache php8.3-curl php8.3-bcmath php8.3-ldap php8.3-pgsql php8.3-dev
   ```

   Install the MongoDB PHP Extension with PECL:
   ```none
   sudo pecl install mongodb-1.15.0
   ```

   For more information, see <a href="https://www.php.net/manual/en/mongodb.installation.php" target="_blank">MongoDB PHP Extension installation</a>.
2. Configure PHP:
   ```none
   echo -e "extension=mongodb.so \n\nmemory_limit = 2048M \nmax_input_time = 600 \nmax_execution_time = 600 \nrealpath_cache_size=4096K \nrealpath_cache_ttl=600 \nopcache.enable=1 \nopcache.enable_cli=0 \nopcache.memory_consumption=512 \nopcache.interned_strings_buffer=32 \nopcache.max_accelerated_files=32531 \nopcache.save_comments=1" | sudo tee -a  /etc/php/8.3/fpm/php.ini
   echo -e "extension=mongodb.so \n\nmemory_limit = 2048M" | sudo tee -a  /etc/php/8.3/cli/php.ini
   ```
3. Install Node.js 20:
   ```none
   sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
   curl -sL https://deb.nodesource.com/setup_20.x | sudo -E bash -
   sudo apt -y install nodejs
   ```
4. Install Docker and Docker Compose:
   ```none
   # Set up Docker's apt repository
   sudo install -m 0755 -d /etc/apt/keyrings
   sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
   sudo chmod a+r /etc/apt/keyrings/docker.asc

   echo \
     "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
     $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
     sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   sudo apt update

   # Install Docker and Docker Compose
   sudo apt -y install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   sudo usermod -aG docker $(whoami)
   sudo systemctl enable --now docker
   ```

   For more information, see <a href="https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository" target="_blank">Docker installation on Ubuntu</a>.
5. Install Composer v2:
   ```none
   php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php
   php -r "unlink('composer-setup.php');"
   sudo mv composer.phar /usr/bin/composer
   ```
6. Install Symfony Server and enable TLS:
   ```none
   sudo apt -y install libnss3-tools
   wget https://get.symfony.com/cli/installer -O - | bash
   echo 'PATH="$HOME/.symfony/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   symfony server:ca:install
   ```
7. Restart the terminal and web browser to get them ready.

#### BUSINESS TIP
## Business Tip

Digital technologies are gradually being adopted by manufacturing companies. Learn how eCommerce can help you achieve <a href="https://oroinc.com/b2b-ecommerce/blog/digital-transformation-in-manufacturing/" target="_blank">digitalization in manufacturing</a>.

## What’s Next

* [Follow the recommendations](docker-and-symfony/index.md#setup-dev-env-docker-symfony-recommendations)
* [Install the Oro Application via the Command-Line Interface](docker-and-symfony/index.md#setup-dev-env-docker-symfony-install-application)

<!-- Frontend -->
