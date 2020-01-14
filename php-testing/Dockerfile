FROM arnidan/php:latest

RUN apt update && apt install -y \
    libxml2-dev \
    libzip-dev \
    libsqlite3-dev \
    librabbitmq-dev \
    libssh-dev \
    libsodium-dev

RUN docker-php-ext-install \
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
        sodium \
    && pecl install amqp \
    && docker-php-ext-enable amqp

RUN php -m

