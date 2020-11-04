# LAMP конфигурация



$ sudo apt-get update

$ sudo apt-get install apache2

$ sudo apache2ctl configtest

Конф

$ sudo nano /etc/apache2/apache2.conf



```text
ServerName server_domain_or_IP
```

$ sudo ufw app list

$ sudo ufw app info "Apache Full"

$ sudo ufw allow in "Apache Full"

$ sudo apt-get install curl

$ sudo apt-get install mysql-server

$ mysql\_secure\_installation

CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8 COLLATE utf8\_unicode\_ci;

GRANT ALL ON wordpress.\* TO 'wordpressuser'@'localhost' IDENTIFIED BY 'password';

FLUSH PRIVILEGES;

$ sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql

$ sudo apt-get install php-curl php-gd php-mbstring php-mcrypt php-xml php-xmlrpc

htaccess  $ sudo nano /etc/apache2/apache2.conf



```text
<Directory /var/www/html/>
    AllowOverride All
</Directory>
```

$ sudo a2enmod rewrite

$ sudo apache2ctl configtest

$ sudo systemctl restart apache2

index.php  info



```text
<?php
phpinfo();
?>
```

download

$ curl -O [https://wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz)

$ tar xzvf latest.tar.gz

создать htaccess

touch /tmp/wordpress/.htaccess

chmod 660 /tmp/wordpress/.htaccess

Config default

$ cp /tmp/wordpress/wp-config-sample.php /tmp/wordpress/wp-config.php

для upgrade  $ mkdir /tmp/wordpress/wp-content/upgrade

sudo cp -a /tmp/wordpress/. /var/www/html

Права

$ sudo chown -R sammy:www-data /var/www/html

$ sudo find /var/www/html -type d -exec chmod g+s {} \;

$ sudo chmod g+w /var/www/html/wp-content

$ sudo chmod -R g+w /var/www/html/wp-content/themes

$ sudo chmod -R g+w /var/www/html/wp-content/plugins

wordpres salt

$ curl -s [https://api.wordpress.org/secret-key/1.1/salt/](https://api.wordpress.org/secret-key/1.1/salt/)

внести в nano /var/www/html/wp-config.php

базу данных конфиг

Финиш



```text
http://доменное_имя_или_IP_адрес
```

### Обновление WordPress <a id="&#x41E;&#x431;&#x43D;&#x43E;&#x432;&#x43B;&#x435;&#x43D;&#x438;&#x435;-wordpress"></a>

$ sudo chown -R www-data /var/www/html

потом вернуть назад  sudo chown -R sammy /var/www/html



