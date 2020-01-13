FROM php:latest

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt update \
    && apt install -y zip

RUN chmod +x /usr/bin/composer \
    && /usr/bin/composer global require "hirak/prestissimo:^0.3"
