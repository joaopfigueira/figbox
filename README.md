# Figbox

## The flexible Vagrant box that developers love


### What is Figbox?
Figbox is a provision shell script for a Vagrant box that uses a base Ubuntu 16.04 LTS Xenial 64 OS.

The objective of Figbox is to have a flexible development environment that you can easily adapt to power your projects.


## Requirements
Before you use Figbox, you need to have Virtualbox and Vagrant installed. It is possible to use other virtualization providers, like VMware, but only Virtualbox was used and tested.

Virtualbox and Vagrant are free and available for OS X, Linux and Windows. Download them from here:
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Vagrant ](https://www.vagrantup.com/downloads.html)

## Installation
You can install Figbox using Git or Composer:

#### Git
```
$ git clone https://github.com/joaopfigueira/figbox.git
```
Or:

Go to https://github.com/joaopfigueira/figbox and download the repository as a ZIP file.

#### Composer
```
$ composer create-project joaofigueira/figbox path --prefer-dist
```
The easiest way to install Figbox is to use Composer, but if you don't have Composer, PHP or Git installed in your system, you can still download the repository as a ZIP file.

## Configuration
Before you start using your new development environment, you should choose what you will be using.

Open ```provision/bootstrap.sh``` in a text editor and edit:
```
USE_APACHE=true

# PHP stuff
USE_PHP=true
USE_COMPOSER=true
COMPOSER_AUTO=false
USE_PHPUNIT=true

# Database stuff
USE_MYSQL=true
USE_PHPMYADMIN=true
DB_HOST=localhost
DB_NAME=projectdb
DB_USER=root
DB_PASSWD=root
MYSQL_IMPORT=true

#Git stuff
USE_GIT=true
GIT_USER="Git User"
GIT_EMAIL=user.email@domain.com

# Node stuff
 USE_NODE=false
 USE_GULP=false
 USE_BOWER=false
 USE_GRUNT=false
 
 USE_ANGULAR=false

 USE_MAILCATCHER=false
```
You can choose what you want installed in your new box by setting true or false. That's all it takes!

Please note that in adition to choosing if you want Git installed, you can also set it up with your user.


## Usage
Boot up / provision box:
``` 
$ vagrant up 
```

SSH into box:
``` 
$ vagrant ssh
``` 

Shutdown box:
``` 
$ vagrant halt
``` 

Shutdown and delete box:
``` 
$ vagrant destroy
``` 

To access you project:

Apache: ```http://localhost:8080``` 

Mailcather: ```http://localhost:1080``` 

Angular: ```http://localhost:4200```


## Features
#### Currently there are options for:

- Apache
- PHP
- Composer
- PHPUnit
- MySQL
- phpMyAdmin
- MailCatcher
- Git
- Node + npm
- Gulp
- Bower
- Grunt
- Angular

##### Auto import SQL
If ```MYSQL_IMPORT``` is set to true, when provisioning and if the file ```provision/sql``` exists, that file will be imported in the database as SQL.

That is useful if you destroy the box but later may want to return to it.

##### Auto composer
If ```COMPOSER_AUTO``` is set to true, when provisioning, a ```composer install``` will run.

That is useful in case you what to boot the project with a customized composer file.


###### Have fun!
