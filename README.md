# Frappe Web Framework Installation
A list of various frappe installation methods documented for future reference.

## Version 15
<h3><b> Step 1: Install WSL and Ubuntu </b></h3>

#### In windows powershell (Run as Administrator) run 
    wsl --install -d ubuntu

##### If you face an error while opening the installed distro in wsl (Even afterrestarting the system), try
    wsl --update


#### After creating a new username and password, run 
    sudo apt-get update
Followed by

    sudo apt-get upgrade
      
<h3><b> Step 2: Install Frappe Pre-requisites </b></h3>

#### We need to install the following prerequisite packages for Frappe V15
    Python 3.10 or 3.11    pip 20+  
    Node.js 18             yarn 1.12+ 
    MariaDB 10.6.6+        cron
    Redis 6                NGINX
    wkhtmltopdf (version 0.12.5 with patched qt)

#### Python 3.10 & pip 20+
The following command installs both the latest version of python 3 and pip
    
    sudo apt-get install python3

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
