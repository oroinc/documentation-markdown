<a id="setup-dev-env-docker-symfony-ubuntu"></a>

# Set up Environment for OroPlatform Based Application on Ubuntu 20.04

This guide demonstrates how to set up [Docker and Symfony Server development stack](docker-and-symfony/index.md#setup-dev-env-docker-symfony) for Oro applications on Ubuntu 20.04 LTS.

## Environment Setup

1. Install PHP 8.1 with all required extensions:
   ```none
   sudo apt install software-properties-common
   sudo add-apt-repository -y ppa:ondrej/php
   sudo apt update
   sudo apt -y install php8.1 php8.1-fpm php8.1-cli php8.1-pdo php8.1-mysqlnd php8.1-xml php8.1-soap php8.1-gd php8.1-zip php8.1-intl php8.1-mbstring php8.1-opcache php8.1-curl php8.1-bcmath php8.1-ldap php8.1-pgsql php8.1-dev php8.1-mongodb
   ```
2. Configure PHP:
   ```none
   echo -e "memory_limit = 2048M \nmax_input_time = 600 \nmax_execution_time = 600 \nrealpath_cache_size=4096K \nrealpath_cache_ttl=600 \nopcache.enable=1 \nopcache.enable_cli=0 \nopcache.memory_consumption=512 \nopcache.interned_strings_buffer=32 \nopcache.max_accelerated_files=32531 \nopcache.save_comments=1" | sudo tee -a  /etc/php/8.1/fpm/php.ini
   echo -e "memory_limit = 2048M" | sudo tee -a  /etc/php/8.1/cli/php.ini
   ```
3. Install Node.js 16:
   ```none
   sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
   curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   sudo apt -y install nodejs
   ```
4. Install Docker and Docker Compose:
   ```none
   sudo apt -y install docker.io docker-compose-plugin
   sudo usermod -aG docker $(whoami)
   sudo systemctl enable --now docker
   ```
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
