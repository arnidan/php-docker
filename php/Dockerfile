ARG PHP_VERSION=8.2

FROM php:${PHP_VERSION}-alpine

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt update && apt install -y zip
