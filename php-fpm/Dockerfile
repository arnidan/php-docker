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

# ponytail: prebuilt .so from Alpine's phpXY-pecl-* packages instead of a ~5h pecl compile under QEMU.
# Same PHP minor = same extension API. Versions lag pecl a bit; apk fetch fails loudly if a package disappears.
RUN if [ "$WITH_GRPC" = "1" ]; then \
        v=$(php -r 'echo PHP_MAJOR_VERSION . PHP_MINOR_VERSION;') \
        && apk add --no-cache libstdc++ \
        && cd /tmp \
        && for ext in grpc protobuf; do \
            apk fetch "php$v-pecl-$ext" \
            && tar -xzf "php$v-pecl-$ext"-*.apk "usr/lib/php$v/modules/$ext.so" \
            && mv "usr/lib/php$v/modules/$ext.so" "$(php-config --extension-dir)/" \
            && docker-php-ext-enable "$ext" || exit 1; \
        done \
        && rm -rf /tmp/*; \
    fi
