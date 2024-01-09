ARG PHP_VERSION=8.2
FROM php:${PHP_VERSION}-alpine

RUN apk --no-cache add zip git

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
