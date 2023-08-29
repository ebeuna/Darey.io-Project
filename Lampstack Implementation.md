# Preparing prerequisite
## AWS setup and connecting to yout EC2 instance
### I have set up my AWS with a free EC2 Ubuntu virtual server called *webstack implementation instance*.
![Screenshot (34)](https://github.com/ebeuna/project-2/assets/140742446/d74e171c-3533-4f59-a318-9fd73d14cedb)
### I need to connect to my EC2 Ubuntu virtual server by first changing the directory to where my private key is located and run some command in my gitbash terminal which is displaced below. 
![Screenshot (35)](https://github.com/ebeuna/project-2/assets/140742446/ebb2f64e-78e1-4021-8fe7-ec6c8d58c62a)
# Installing Apache and Updating the Firewall
## Step 1: Installing Apache and Updating the Firewall
### Before installing Apache, I need to update a list of package in package manager by running the command below.
![sudo apt update](https://github.com/ebeuna/project-2/assets/140742446/84b7a38a-29b6-4871-8a7e-ba05a5225101)
![sudo apt update 2](https://github.com/ebeuna/project-2/assets/140742446/c057c658-641b-4a48-aa0d-9e042d00dc22)
### After running the update, I went ahead to install Apache2 by running the command below.
![sudo apt install apache2](https://github.com/ebeuna/project-2/assets/140742446/ad5d8e01-68de-42f8-8595-51a161198c49)
![sudo apt install apache2](https://github.com/ebeuna/project-2/assets/140742446/47771622-4fa2-4a40-a259-b2af62478766)
### After installation, I need to verify that the package *Apache2* is running as a service in my operating system by running the command below.
### Note: if its green and running then its okay and I have just launch my first webserver in the cloud.
![systemctl status](https://github.com/ebeuna/project-2/assets/140742446/40e44463-4f8f-42cf-94c1-5a30e2ba4bd4)
### Let us try and access it locally in our ubuntu shell by runnung the command below.
### Note: we just made sure that our *Apache web server* responds to our curl command.
![curl http](https://github.com/ebeuna/project-2/assets/140742446/c532eefc-0c89-4685-a27b-15e1564d3afd)
### To test how our Apache HTTP server respond to requests from the internet, I opened a web server of my choice and try to access the url *http//13.49.66.72:80* i.e my public ip address through a default port that web browser uses to access web pages on the internet called 80. 
### Note: The page below shows my webserver is correctly installed and accessible through my firewall.
![apache2 ubuntu default](https://github.com/ebeuna/project-2/assets/140742446/7b2841c4-6411-4ad7-ba93-afdf4b1af72d)
# Installing Mysql
## step 2: Installing Mysql
### Now that my web server is running, I need to install a database where I can store and manage data for my site. MySql is a popular database used within PHP environment. so I will install MySql-server by running the command below.
![Screenshot (36)](https://github.com/ebeuna/project-2/assets/140742446/19cd841a-6df8-467a-88dd-c584fa964e9c)
### when the installation is complete, I need to log into mysql console by running the command below.
### Note: This will connect me to Mysql server as an administrative database user root which is inferred by the use of sudo command.
![sudo mysql](https://github.com/ebeuna/project-2/assets/140742446/cbc422c4-4a1d-4f15-9c19-d4acf799b92c)
### I run a security script that removed some insecure default settings and lock down access to my database system.
![sudo mysql install 2](https://github.com/ebeuna/project-2/assets/140742446/8ba90eac-a24a-47d9-b689-88ff498ccea2)
### After running the security script, I tested if am still able to log into the Mysql console.
### Note: the flag -p in the command below prompt me to enter the password I used after changing the root user password.
![sudo mysql -p](https://github.com/ebeuna/project-2/assets/140742446/1e8170d2-4881-48c7-b797-0c9b78d0af58)
# Installing PHP
## step 3: Installing PHP
### I need to install a *PHP package* that will process code to display dynamic content to the end user, a PHP module called *php-mysql* that allows PHP to communicate with Mysql based database and *libapache2-mod-php* that enables Apache to handle PHP files. 
### Note: I installed the three package at once.
![Screenshot (37)](https://github.com/ebeuna/project-2/assets/140742446/9e10b336-da91-4ac9-971b-61029ec9473c)
### Once the installation is complete, I run the command below to confirm my PHP version.
![php -v](https://github.com/ebeuna/project-2/assets/140742446/cf393714-b5de-43a7-85cc-8c1d56a338ce)
# Creating a virtual Host for my Website using Apache
## Step 4: Creating a virtual Host for my Website using Apache
### Apache on ubuntu has one server block enabled by default that is configured to serve documents from the /var/www/htmldirectory. we will leave this configuration as it is and add our directory next to the default one and the directory is called *projectlamp* by running the command below. 
![Screenshot (40)](https://github.com/ebeuna/project-2/assets/140742446/014ba275-1316-481c-bffb-839b89c611ba)
### we need to assign ownership of the directory with the $USER environment variable by running the command below.
![Screenshot (42)](https://github.com/ebeuna/project-2/assets/140742446/72b280c6-4f3b-4d5d-9fb1-791828ecc0b9)
### we will be using vi code to create and open a new configuration file in Apache's site-available by running the command below.
### Note: This will create a blank file. I pasted in the following bare-bones configuration by hitting on i on the kwyboard to enter the insert mode and paste the text in the screenshot below. I then hit on the esc botton and type :wq! (w for write and q for quit) and press the enter botton to save the file.
![Screenshot (43)](https://github.com/ebeuna/project-2/assets/140742446/09ab9079-4d91-4c2f-ad4d-a649e9f65519)
### The *ls* command was used to show the new file in the sites-available directory. 
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



