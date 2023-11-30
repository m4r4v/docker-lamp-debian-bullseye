# Docker-Lamp-Debian-Bullseye

> author: m4r4v
> docker hub: https://hub.docker.com/repository/docker/m4r4v/lamp-debian-bullseye
> github: https://github.com/m4r4v

The following tutorial creates a LAMP ina docker container using Debian Bullseye as OS

## Step 1

Create a directory and move to it

```bash
mkdir lamp-debian-bullseye && cd lamp-debian-bullseye
```

## Step 2

Create a directory

```bash
mkdir lamp-debian-bullseye
```

## Step 3

Create container

```shell
docker run -p 8086:80 -p 3306:3306 -d -v ${PWD}:/var/www/html/ -e MYSQL_ROOT_PASSWORD=seccret --name lamp-debian-bullseye php:8.2.10-apache-bullseye
```

## Step 4

Update and Upgrade OS

```bash
apt update -y && sudo apt upgrade -y
```

## Step 5

Install packages

```bash
sudo apt install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev wget dirmngr software-properties-common apt-transport-https curl lsb-release ca-certificates mariadb-server vim
```


## Step 8

Install docker dependencies

```bash
sudo docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ && docker-php-ext-install gd mysqli pdo pdo_mysql
```


## Step 9

Setup mysql and change root password

```bash
sudo mariadb-secure-installation
```

