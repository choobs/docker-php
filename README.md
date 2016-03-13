# Choobs PHP Docker Image #

## Supported tags and respective `Dockerfile` links ##

- [`7.0-cli`, `latest` (7.0/cli/Dockerfile)](https://github.com/choobs/docker-php/blob/master/7.0/cli/Dockerfile)
- [`7.0-fpm` (7.0/fpm/Dockerfile)](https://github.com/choobs/docker-php/blob/master/7.0/fpm/Dockerfile)
- [`5.6-cli` (5.6/cli/Dockerfile)](https://github.com/choobs/docker-php/blob/master/5.6/cli/Dockerfile)
- [`5.6-fpm` (5.6/fpm/Dockerfile)](https://github.com/choobs/docker-php/blob/master/5.6/fpm/Dockerfile)

[![](https://badge.imagelayers.io/choobs/php:latest.svg)](https://imagelayers.io/?images=choobs/php:latest 'Get your own badge on imagelayers.io') [![Docker Stars](https://img.shields.io/docker/stars/choobs/php.svg?style=flat-square)](https://hub.docker.com/r/choobs/php/) [![Docker Pulls](https://img.shields.io/docker/pulls/choobs/php.svg?style=flat-square)](https://hub.docker.com/r/choobs/php/) [![Build Status](https://travis-ci.org/choobs/docker-php.svg?branch=master)](https://travis-ci.org/choobs/docker-php)

## Information ##

- The image is based on the [alpine](https://hub.docker.com/_/alpine/) image.
- The `7.0` version is currently part of alpine edge.
- The `cli` provides php from the command line and `fpm` provides php behind fpm to be used with an nignx proxy for example.
- This image includes the extensions: `ctype`, `json`, `openssl`, `phar`, `xml`.
- This image includes `composer` and `git`.
- Report any issues in the github [issue tracker](https://github.com/choobs/docker-php/issues/new).
