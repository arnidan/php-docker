ARG PHP_VERSION=8.2

FROM ghcr.io/arnidan/php-docker/php:${PHP_VERSION}

RUN apk add --no-cache libxslt-dev && docker-php-ext-install xsl

ENV PATH "$PATH:/root/.composer/vendor/bin"

RUN composer global require edgedesign/phpqa --update-no-dev
