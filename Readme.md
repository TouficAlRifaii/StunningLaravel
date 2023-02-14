# Stunning Laravel


## CheckPoint 1

sudo = it is a command that gives a specific user permissions to use commands at the root

apt-get = it is a command to interact with the Advanced Package Tool  library and it allows us to to search, install, and update packages and softwares. 

ip address = 172.31.44.179

## CheckPoint 4


2- I used cp command 


## CheckPoint 6

2- This command changes the group ownership of the "storage" and "bootstrap/cache" directories and their contents to the "www-data" group, recursively
3- This command grants read, write, and execute permissions to the owner and group of the "storage" and "bootstrap/cache" directories and their contents, recursively



## Findings : how to deploy the laravel website
#### connecting to the server and installing dependancies (using windows, puTTy)
the following steps are after connected to the server and having the project ready for deployment 
1- sudo apt-get install apache2 

2- sudo apt-get install mysql-server

3- sudo apt-get install php

4- sudo apt-get install php-mysql

5- sudo apt-get install libapache2-mod-php

6- sudo apt-get install php-pear

7- sudo apt-get install curl

8- sudo apt-get install php-curl

9- sudo apt-get install php-cli

10- sudo apt-get install git

11- a2enmod rewrite

12- systemctl restart apache2

#### clone your project into /var/www/html 

1- cd /var/www/htmll

2- git clone < link to repo >

#### install composer

1- curl -sS https://getcomposer.org/installer  | sudo php -- --install-dir=/usr/local/bin --filename=composer

2- composer install

#### create .env and generate key 

1- cp .env.example .env

2- sudo vim .env

 once inside vim (to modify the app name)
 
 1- i (insert)
 
 2- :x (save and exit)
 
3- php artisan key:generate

#### configure apache 

1- cd ../etc/apache2

2- sudo vim apache2.conf

  once inside vim (to modify the apache config directory)
  
 1- i
 
 2- :x
 
3- cd sites-enables

4- sudo vim 000-default.conf

 once inside vim (modify document root)
 
 1- i
 
 2- :x
 
5- systemctl restart apache2

#### setting folder rights 

1- sudo chgrp -R www-data storage bootstrap/cache

2- sudo chmod -R ug+rwx storage bootstrap/cache



