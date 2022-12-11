ARG PHP_VERSION=8.2
FROM ghcr.io/arnidan/php-docker/php:${PHP_VERSION}

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions xsl

ENV PATH "$PATH:/root/.composer/vendor/bin"

RUN composer global require edgedesign/phpqa --update-no-dev
