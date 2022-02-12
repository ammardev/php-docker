# PHP Image with my configurations

[![Docker Hub Link](https://img.shields.io/badge/Docker%20Hub-2CA5E0?logo=docker&logoColor=white)](https://hub.docker.com/r/ammardev0/php)

[![Build, Push php 7.1 image](https://github.com/ammardev/php-docker/actions/workflows/php-7.1.yml/badge.svg)](https://github.com/ammardev/php-docker/actions/workflows/php-7.1.yml)
[![Build, Push php 7.3 image](https://github.com/ammardev/php-docker/actions/workflows/php-7.3.yml/badge.svg)](https://github.com/ammardev/php-docker/actions/workflows/php-7.3.yml)
[![Build, Push php 8.0 image](https://github.com/ammardev/php-docker/actions/workflows/php-8.0.yml/badge.svg)](https://github.com/ammardev/php-docker/actions/workflows/php-8.0.yml)
[![Build, Push php 8.1 image](https://github.com/ammardev/php-docker/actions/workflows/php-8.1.yml/badge.svg)](https://github.com/ammardev/php-docker/actions/workflows/php-8.1.yml)

This is a Docker image for PHP FPM with my own configuration.
The image has Composer installed by default with many PHP extensions enabled.

## Usage

By default, the container will create a webserver using PHP built-in web server feature.

```bash
docker run -v $PWD:/var/www -p 80:80 ammardev0/php
```

You can execute any other command. That will run your command inside the container without running the web server.

```bash
docker run ammardev0/php php -v
```

## Available tags/versions

* `7.1`
* `7.3`
* `8.0`
* `8.1` / `latest`

## Extensions

* XDebug
* Memcached
* Redis
* MongoDB
* GD
* bcmath
* pdo_mysql
* zip
* exif
* opcache
* calendar
* pcntl

## Aliases

The image has many aliases enabled by default (Assuming that you are using the zsh shell).

```bash
art = php artisan
```

```bash
test = clear && php artisan test
```

## Other useful tools

This package has the following tools installed:

* ZSH shell
* Composer
* Laravel Envoy (Installed Globally)