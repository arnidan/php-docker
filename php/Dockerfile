FROM php:alpine

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN chmod +x /usr/bin/composer \
     && /usr/bin/composer global require "hirak/prestissimo:^0.3"
