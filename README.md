MONOLITHIC

Task Completion Report: Deploying WordPress and MySQL on a Single EC2 Instance

We launched an EC2 instance with the desired specifications.

Installed MySQL using the package manager, and set a secure root password.

I created a database and user for WordPress.

Downloaded and configured WordPress files.

Edited wp-config.php with database details and secret keys.

Installed and configured Apache as the web server.

Accessed the WordPress site using the public IP address.

Install Apache server on Ubuntu sudo apt install apache2

Install php runtime and php mysql connector sudo apt install php libapache2-mod-php php-mysql

Install MySQL server sudo apt install mysql-server

Login to MySQL server sudo mysql -u root

Change authentication plugin to mysql_native_password (change the password to something strong) ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Testpassword@123'; I created a database and user for WordPress.
Create a new database user for wordpress (change the password to something strong)
CREATE USER 'wp_user'@localhost IDENTIFIED BY 'Testpassword@123';

7. Create a database for wordpress
CREATE DATABASE wp;

8. Grant all privilges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp_user'@localhost;

9. Download wordpress
cd /tmp
wget https://wordpress.org/latest.tar.gz

10. Unzip
tar -xvf latest.tar.gz

11. Move wordpress folder to apache document root
sudo mv wordpress/ /var/www/html

Resources Used:

AWS EC2 Documentation MySQL Documentation WordPress Download WordPress Configuration Guide Apache HTTP Server Documentation Monolithic architecture 
