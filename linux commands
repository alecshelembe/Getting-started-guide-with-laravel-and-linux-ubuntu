
---
Laravel start-up commands
--
cp .env.example .env
php artisan key:generate
php artisan migrate
chown -R www-data storage
chown -R www-data bootstrap/cache
composer install --optimize-autoloader --no-dev
php artisan storage:link


LAMP Stack with laravel full linux installation guide

---
Step 1: Install and connect to your machine using ssh be sure to create or upload your id_rsa.pub file and add it to autherized_keys
--
/etc/ssh/sshd_config
sudo apt install openssh-server -y
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
sudo ufw allow ssh
sudo ufw allow 22/tcp
sudo ufw allow 8080/tcp
sudo systemctl start ssh
sudo systemctl enable ssh
sudo ufw status
sudo systemctl restart ssh
sudo ufw enable
sudo apt update

---
Step 2: Install apache to deliver your website 
---
sudo apt install apache2 -y
sudo ufw allow 'Apache'
sudo ufw allow 'Apache Full'

---
Step 3: install mysql as a database this works with phpmyadmin
--
sudo apt install mysql-server -y
sudo mysql_secure_installation
sudo systemctl start mysql
sudo systemctl enable MySQL

create user 'alec'@'localhost' identified by '1!Alec123';
create database api;
GRANT ALL PRIVILEGES ON api.* TO 'alec'@'localhost';
flush privileges;
exit;

---
Step 4: Install php and relevent extentions for laravel
--
sudo apt install -y software-properties-common
sudo add-apt-repository -y ppa:ondrej/php
sudo apt install -y php8.2  
sudo apt install php8.2-curl php8.2-gd php8.2-dom php8.2-mbstring php8.2-xml php8.2-mysql zip unzip
sudo update-alternatives --set php /usr/bin/php8.2

sudo apt install php8.2-gd
php -m | grep -E 'gd|dom'
sudo apt update
sudo apt install php-gd php-xml -y

---
Step 5: Install phpmyadmin to better navigate your database (remove for production)
--
sudo apt install phpmyadmin -y
sudo ln -s /etc/phpmyadmin/apache.conf /etc/apache2/conf-available/phpmyadmin.conf
sudo a2enconf phpmyadmin

---
Step 6: Install the latest nodejs version to your machine, update your source packages
--
sudo apt remove nodejs npm
sudo apt clean
sudo apt autoremove
sudo apt purge nodejs
curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo apt install npm

---
Another step: If your installing wordpress to your machine 
--
mv /var/www/html/wordpress/wp-config-sample.php /var/www/html/wordpress/wp-config.php
sudo a2enmod rewrite
wget https://wordpress.org/latest.zip
sudo chown -R www-data:www-data /var/www/html/wordpress
cd /var/www/html/wordpress
find . -type d -exec chmod 755 {} \;
find . -type f -exec chmod 644 {} \;`
chmod 600 wp-config.php
sudo chown -R www-data:www-data /var/www/html/wordpress

---
Step 7: Install php composer the package manager for php  
--

php -m
sudo a2enmod rewrite
sudo service apache2 restart
cd /usr/bin
curl -sS https://getcomposer.org/installer | sudo php
sudo mv composer.phar composer
composer

---
step 8: Install and authenticate with GitHub
--
sudo apt install gh -y
gh auth login

---
Another step: when creating your .conf file under /etc/apache/sites-enabled be sure to give url permissions like below
--
<Directory /var/www/package/public>
     Options Indexes FollowSymLinks MultiViews
     AllowOverride All
     Require all granted
</Directory>

---
step 9: Install certbot for you lets encrypt ssl certificates
--
sudo apt install certbot python3-certbot-apache -y
sudo certbot --apache
certbot install --cert-name investec-developer-project-repo.visitmyjoburg.co.za

---
If your running on a different port
--
sudo nano /etc/apache2/ports.conf
sudo ufw status verbose
Listen 8081 (add this to line)
sudo a2ensite demo.conf (shortcut to enable .conf files)
--
sudo a2enmod ssl

---
refresh laravel application
--
php artisan config:cache
php artisan config:clear
php artisan view:clear
php artisan cache:clear

sudo systemctl restart ufw apache2 mysql ssh

php artisan clear-compiled
composer dump-autoload

php artisan route:list

---
mysql commands
--
CREATE USER 'external'@'localhost' IDENTIFIED BY '1!External123';
GRANT SELECT, INSERT, UPDATE, DELETE ON your_database.* TO 'external'@'localhost';
FLUSH PRIVILEGES;
SHOW GRANTS FOR 'external'@'localhost';
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'external'@'localhost';
sudo ufw reload
GRANT INSERT ON api.social_posts TO 'external'@'localhost';


--------------
ssh-keygen -t ed25519 -C "alecshelembe@gmail.com"
sudo apt install espeak

npx tailwindcss -o public/css/output.css
php artisan qrcode:generate-daily
php artisan storage:link
git clone -b Google-auth https://github.com/alecshelembe/thestreetking.git
https://github.com/alecshelembe/licence.git
sudo tail -f /var/log/apache2/error.log

curl -X GET "https://thevapeokes.com/wp-json/visitmyjoburg/v1/info?key=https://visitmyjoburg.co.za';
    $secret_key = '1qazsw34edc" \
     -H "Origin: https://visitmyjoburg.co.za"
