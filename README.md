# Frappe Web Framework Installation
A list of various frappe installation methods documented for future reference.

## Version 15
<h3><b> Step 1: Install WSL and Ubuntu </b></h3>

In windows powershell (Run as Administrator) run 

    wsl --install -d ubuntu

If you face an error while opening the installed distro in wsl (Even afterrestarting the system), try

    wsl --update


After creating a new username and password, run 
    
    sudo apt-get update

Followed by

    sudo apt-get upgrade
      
<h3><b> Step 2: Install Frappe Pre-requisites </b></h3>

We need to install the following prerequisite packages for Frappe V15

    Python 3.10 or 3.11    pip 20+  
    Node.js 18             yarn 1.12+ 
    MariaDB 10.6.6+        cron
    Redis 6                NGINX
    wkhtmltopdf (version 0.12.6 with patched qt)

#### Python 3.10 & pip 20+
Use the following command to install the latest version of python 3
    
    sudo apt-get install python3

Then run the following to install the latest version of pip

    sudo apt install python3-pip
    
#### Node.js 18
To install node.js we first install nvm

    curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash

To use nvm immediately, run
    
    source ~/.profile

Then install the correct version of node using

    nvm install 18.12.0

#### Yarn 1.12+
To install yarn we need to install npm first

    sudo apt-get install npm

Then we install the latest version of yarn using

    sudo npm install -g yarn

#### Redis 6
Run the following command to install the latest version of redis

    sudo apt-get install redis-server

#### wkhtmltopdf 12.6 (with patched qt)
Run the following set of commands to install the correct version of wkhtmltopdf and its dependencies

    sudo apt-get install xfonts-75dpi
    sudo apt-get install xfonts-base
    wget https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6.1-2/wkhtmltox_0.12.6.1-2.jammy_amd64.deb
    sudo dpkg -i wkhtmltox_0.12.6.1-2.jammy_amd64.deb
    rm wkhtmltox_0.12.6.1-2.jammy_amd64.deb

#### mariadb 10.6.6+
Run the following commands to install mariadb

    sudo apt install software-properties-common
    sudo apt-get update
    sudo apt-get install mariadb-server
    sudo mysql_secure_installation

(During the initial input for root password, just press enter and when prompted to change the root password, change it.)

Now we need to make the following changes to the mariadb configurations

    sudo nano /etc/mysql/my.cnf

Add the following to the end of the file

    [mysqld]
    character-set-client-handshake = FALSE
    character-set-server = utf8mb4
    collation-server = utf8mb4_unicode_ci

    [mysql]
    default-character-set = utf8mb4

    