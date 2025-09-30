ARG PHP_VERSION=8.4

FROM dunglas/frankenphp:php${PHP_VERSION}

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

ARG WITH_GRPC=0

RUN if [ "$WITH_GRPC" = "1" ]; then \
        install-php-extensions protobuf grpc; \
    fi