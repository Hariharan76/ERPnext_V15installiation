# Frappe Web Framework Installation
A list of various frappe installation methods documented for future reference.

# Version 15
<h3><b> Step 1: Install WSL and Ubuntu </b></h3>

#### In windows powershell (Run as Administrator) run 
    wsl.exe --install ubuntu-22.04
    
#### After creating a new username and password, run 
    sudo apt-get update

#### Followed by
    sudo apt-get upgrade
      
<h3><b> Step 2: Install Frappe Pre-requisites </b></h3>

#### We need to install the following prerequisite packages for Frappe V15
    Python 3.12            yarn 1.12+  
    Node.js 18             pip 20+ 
    MariaDB 10.6.6+        cron
    Redis 6                NGINX
    wkhtmltopdf (version 0.12.5 with patched qt)

#### Python 3.12
    sudo apt-get install python3

#### Node.js 18
    sudo apt-get install npm
    
