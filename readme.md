# PHP-FPM Docker image for Expression Engine

Docker image for a php-fpm container crafted to run Expression engine based applications.

## Specifications:

* PHP 5.4
* OpenSSL PHP Extension
* PDO PHP Extension
* Mbstring PHP Extension
* ZIP PHP Extension
* MCRYPT PHP Extension
* GD PHP Extension
* PHP ini values for ExpressEngine (see express.ini)

## Tags available:

When calling the image you want to use within your `docker-compose.yml` file,
you can specify a tag for the image. Tags are used for various versions of a
given Docker image. By default, `latest` is the one used when no tag is specified.

* `latest` which is using PHP 5.4
* `5.4` (for version 2 of EE)

## docker-compose usage:

```yml
version: '2'
services:
    php-fpm:
        image: cyberduck/php-fpm-expression-engine(:<optional-tag>)
        volumes:
            - ./:/var/www/
            - ~/.ssh:/root/.ssh # can be useful for composer if you use private CVS
        networks:
            - my_net #if you're using networks between containers
```