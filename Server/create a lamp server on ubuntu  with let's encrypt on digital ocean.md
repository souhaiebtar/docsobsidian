
sudo add-apt-repository ppa:ondrej/php
sudo add-apt-repository ppa:ondrej/apache2
apt install apache2 
apt install php8.1-{common,cli,fpm,curl,bz2,mbstring,intl,zip,xml,mysql,gd,pdo}

a2enmod proxy_fcgi setenvif
a2enconf php8.1-fpm


CREATE USER 'prestashop'@'%' IDENTIFIED BY 'azda12&B';
GRANT ALL PRIVILEGES ON prestashop.* TO 'prestashop'@'%';

useradd unknown
usermod -aG sudo unknown

sudo apt install -y certbot python3-certbot-apache

certbot --test-cert -m tsouhaieb@gmail.com --agree-tos  --apache -d test.fesfes.online #staging certificate

certbot -m tsouhaieb@gmail.com  --apache -d store.fesfes.online --agree-tos  # prod certificate