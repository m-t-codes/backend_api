# About this project

## Cloning this project
after cloning this repo following steps are nessessary to run it localy.

requires PHP 8.0.2 or higher e.g. 8.1

### installing php 8.1 on Linux

sudo apt update && sudo apt -y upgrade

Add repository Ubuntu 20.04|18.04 (Not needed on Ubuntu 22.04)
    sudo apt update
    sudo apt install lsb-release ca-certificates apt-transport-https software-properties-common -y
    sudo add-apt-repository ppa:ondrej/php

The only input from you is to hit <Enter key> and add the repository:
    sudo apt update
    
    sudo apt install php8.1
    
    php --version
    
Installing commonly used PHP extensions:
    sudo apt install php8.1-{bcmath,xml,fpm,mysql,zip,intl,ldap,gd,cli,bz2,curl,mbstring,pgsql,opcache,soap,cgi}
    
It's possible that after all this our apache is running, lets stop the httpd server and stop the autoboot
    sudo systemctl stop httpd
    sudo systemctl disable httpd
    
    
### Copy the .env.example 
    cp .env.example .env
    
### Install all required dependencies
    docker run --rm -v $(pwd):/opt -w /opt laravelsail/php80-composer:latest composer install

    sudo chown -R $USER: .
    
    sail up -d
    
    sail artisan key:generate
