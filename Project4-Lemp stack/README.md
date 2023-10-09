## Step 1 - Preliminaries with NGINX

Used SSH id on termius and connected to my AWS instance successfully

![Alt text](<images/SSH client on Termius.png>)

Successful connection

![Alt text](<images/Successful connection.png>)

Used `apt install` to install all updates before installing the Nginx web server. It showed some archives were missing, and it recommended to use `sudo apt-get update`. 

![Alt text](<images/sudo apt update installed.png>)

Used `sudo apt install nginx` and `sudo systemctl status nginx` to install and start nginx. It was successfull

![Alt text](<isntall and start Nginx .png>)

Used `curl http://localhost:80`t confirm server is up and running on the terminal

![Alt text](<images/localhost curled.png>)


 then used `http://<public ip address>` on the browser. 

 ![Alt text](<images/nginx on browser.png>)

## Step 2 - Installing MySQL

Used `sudo apt install mysql-server` to install mysql.

![Alt text](<images/mysql update.png>)

Used `sudo mysql` to enter the MyQSL shell. 

Defined a password for root user with `ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';` then exited the she with `exit`

![Alt text](<images/Mysql login and password change.png>)

Ran interactive script to remove insecure default settings with
`sudo mysql_secure_installation`

It validated passwords and I chose `1` for password strength. 

![Alt text](<images/Mysql interactive script.png>)

Hit `y` for all prompts from removing anonymous users to disabling remote login and reload privileges. 

![Alt text](<images/Removing anonymous users and others.png>)

Tested mysql login again with `sudo mysql -p` that requested for password validation. 

![Alt text](<images/Tested successful login.png>)

## Step 3 - Php and Mysql module

Used the   `sudo apt install php-fpm php-mysql` to install the PHP fastCGI pricess manager - `php-fpm` to handle php requests on NGINX and `php-mysql`module.

![Alt text](<images/Php and mysql on NGINX.png>)

## Step 4 COnfiguring Nginx for PHP processor

Created a root web directory to help with handling multiple sites using `sudo mkdir /var/www/projectLEMP`

Assigned ownership of the directory with the `$USER` environment vairable. used `sudo chown -R $USER:$USER /var/www/projectLEMP`

![Alt text](<images/creating and ownership for projectLEMP.png>)

Opened a new configuration file in Nginx's `sites-available` directory with the `nano` command. Full command was `$ sudo nano /etc/nginx/sites-available/projectLEMP`

![Alt text](<images/Nano projectLEMP file.png>)

Activate configuration by linking to `sites-enabled` directory with `sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/` command.

Then test for errors with `sudo nginx -t`

![Alt text](<images/Sudo link and test syntax.png>)

Disable default NGINX host with `sudo unlink /etc/nginx/sites-enabled/default`

Reload Nginx with `$ sudo systemctl reload nginx`

Create `index.html` file inside the projectLEMP folder with `sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html`

![Alt text](<images/Unlink default site and create html file.png>)

Tested on the browser

![Alt text](<images/projectlemp on browser.png>)

## Step 5 Test PHP with Nginx

Open a new file called `info.php` with `nano/var/www/projectLEMP/info.php`

![Alt text](<images/Php info file.png>)

Paste valid php code that contains relevant informaton. `<?php phpinfo();`

![Alt text](<images/php info on browser.png>)

removed file for security purpose `sudo rm /var/www/your_domain/info.php`

![Alt text](<images/Removing index php file.png>)

## Step 6 retrieving data from MySQL database with PHP

Used the `sudo mysql -p` command since I created a password for the database. 

![Alt text](<images/Entering database again.png>)

Create data base with ``CREATE DATABASE `first_database`;``

![Alt text](<images/Create database.png>)

Create a new user with ``CREATE USER 'Good_man'@'%' IDENTIFIED WITH mysql_native_password BY 'GoodMan.1';``

Grant newly created user permission with ``GRANT ALL ON first_database.* TO 'Good_man'@'%';``

![Alt text](<images/Creating database and user.png>)

Exit and confirm that the user has permissions for the database with `SHOW DATABASES;`

![Alt text](<images/Show databases.png>)

CREATE TABLE example_database.todo_list (item_id INT AUTO_INCREMENT,content VARCHAR(255),PRIMARY KEY(item_id));


mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");











