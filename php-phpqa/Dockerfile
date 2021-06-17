FROM arnidan/php:latest

RUN apt update \
    && apt install -y libxslt-dev \
    && docker-php-ext-install xsl

ENV PATH "$PATH:/root/.composer/vendor/bin"

RUN composer global require edgedesign/phpqa --update-no-dev

ENTRYPOINT ["docker-php-entrypoint"]