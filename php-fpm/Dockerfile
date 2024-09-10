ARG PHP_VERSION=8.3

FROM php:${PHP_VERSION}-fpm-alpine

ARG WITH_GRPC=0

RUN apk --no-cache add zip git

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

ENV MAKEFLAGS=" -j 4"

RUN install-php-extensions \
        intl \
        xml \
        zip \
        simplexml \
        mysqli \
        pdo \
        pdo_mysql \
        pdo_sqlite \
        pdo_pgsql \
        pcntl \
        bcmath \
        sockets \
        redis

RUN if [ "$WITH_GRPC" = "1" ]; then \
        install-php-extensions protobuf grpc; \
    fi