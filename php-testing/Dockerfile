FROM ghcr.io/arnidan/php-docker/php:8.2

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions \
        intl \
        xml \
        zip \
        simplexml \
        mysqli \
        pdo \
        pdo_mysql \
        pdo_sqlite \
        pcntl \
        bcmath \
        sockets \
        redis \
        mongodb
