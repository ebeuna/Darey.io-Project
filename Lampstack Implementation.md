# Preparing prerequisite
## AWS setup and connecting to yout EC2 instance
I have set up my AWS and webstack implementation instance.
![Screenshot (34)](https://github.com/ebeuna/project-2/assets/140742446/d74e171c-3533-4f59-a318-9fd73d14cedb)
## connecting to my webstack instance using git bash terminal
![Screenshot (35)](https://github.com/ebeuna/project-2/assets/140742446/ebb2f64e-78e1-4021-8fe7-ec6c8d58c62a)
# Installing Apache and Updating the Firewall
## Step 1: Installing Apache and Updating the Firewall
sudo apt update
![sudo apt update](https://github.com/ebeuna/project-2/assets/140742446/84b7a38a-29b6-4871-8a7e-ba05a5225101)
![sudo apt update 2](https://github.com/ebeuna/project-2/assets/140742446/c057c658-641b-4a48-aa0d-9e042d00dc22)
sudo apt install apache2
![sudo apt install apache2](https://github.com/ebeuna/project-2/assets/140742446/ad5d8e01-68de-42f8-8595-51a161198c49)
![sudo apt install apache2](https://github.com/ebeuna/project-2/assets/140742446/47771622-4fa2-4a40-a259-b2af62478766)
sudo systemctl status apache2
![systemctl status](https://github.com/ebeuna/project-2/assets/140742446/40e44463-4f8f-42cf-94c1-5a30e2ba4bd4)
$ curl http://localhost:80
![curl http](https://github.com/ebeuna/project-2/assets/140742446/c532eefc-0c89-4685-a27b-15e1564d3afd)
http://13.49.66.72
![apache2 ubuntu default](https://github.com/ebeuna/project-2/assets/140742446/7b2841c4-6411-4ad7-ba93-afdf4b1af72d)
# Installing Mysql
## step 2: Installing Mysql
sudo apt install mysql-server
![Screenshot (36)](https://github.com/ebeuna/project-2/assets/140742446/19cd841a-6df8-467a-88dd-c584fa964e9c)
sudo mysql
![sudo mysql](https://github.com/ebeuna/project-2/assets/140742446/cbc422c4-4a1d-4f15-9c19-d4acf799b92c)
sudo mysql_secure_installation
![sudo mysql install 2](https://github.com/ebeuna/project-2/assets/140742446/8ba90eac-a24a-47d9-b689-88ff498ccea2)
sudo mysql -p
![sudo mysql -p](https://github.com/ebeuna/project-2/assets/140742446/1e8170d2-4881-48c7-b797-0c9b78d0af58)
# Installing PHP
## step 3: Installing PHP
sudo apt install php libapache2-mod-php php-mysql
![Screenshot (37)](https://github.com/ebeuna/project-2/assets/140742446/9e10b336-da91-4ac9-971b-61029ec9473c)
php -v
![php -v](https://github.com/ebeuna/project-2/assets/140742446/cf393714-b5de-43a7-85cc-8c1d56a338ce)
# Creating a virtual Host for my Website using Apache
## Step 4: Creating a virtual Host for my Website using Apache
sudo mkdir /var/www/projectlamp
![Screenshot (40)](https://github.com/ebeuna/project-2/assets/140742446/014ba275-1316-481c-bffb-839b89c611ba)
sudo chown -R $USER:$USER /var/www/projectlamp
![Screenshot (42)](https://github.com/ebeuna/project-2/assets/140742446/72b280c6-4f3b-4d5d-9fb1-791828ecc0b9)
sudo vi /etc/apache2/sites-available/projectlamp.conf
![Screenshot (43)](https://github.com/ebeuna/project-2/assets/140742446/09ab9079-4d91-4c2f-ad4d-a649e9f65519)
sudo ls /etc/apache2/sites-available
![Screenshot (44)](https://github.com/ebeuna/project-2/assets/140742446/07d44ede-7335-4afd-8b47-74ac00b32358)
sudo a2ensite projectlamp

sudo a2dissite 000-default

sudo apache2ctl configtest

sudo systemctl reload apache2
![Screenshot (45)](https://github.com/ebeuna/project-2/assets/140742446/82011714-d2c7-43cc-9afe-afb73038378c)
# Enable PHP on the Website
## Step 5: Enable PHP on the Website
sudo vim /etc/apache2/mods-enabled/dir.conf
![Screenshot (38)](https://github.com/ebeuna/project-2/assets/140742446/d201dd5e-e9cb-4a32-a4e3-3f8732e73359)
sudo systemctl reload apache2
![Screenshot (41)](https://github.com/ebeuna/project-2/assets/140742446/acb35a4c-3bd5-46ce-a233-e46b446a112a)
sudo vim /var/www/projectlamp/index.php
![Screenshot (39)](https://github.com/ebeuna/project-2/assets/140742446/4e16718b-e9dd-47c0-b868-ee5184169a0d)
Refereshing my public ip-51.20.9.40
![Screenshot (32)](https://github.com/ebeuna/project-2/assets/140742446/493146c9-7026-42e8-8f3b-b2bf72026810)



