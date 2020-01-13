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
        pdo \
        pdo_mysql \
        pcntl \
        bcmath \
        sockets \
        sodium \
    && pecl install amqp \
    && docker-php-ext-enable amqp

RUN docker-php-source extract \
    && cd /usr/src/php \
    && ./buildconf --force \
    && ./configure --enable-phpdbg \
    && make -j8 \
    && make install-phpdbg \
    && make clean \
    && docker-php-source delete

RUN php -m

