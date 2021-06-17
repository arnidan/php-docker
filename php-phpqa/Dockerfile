FROM arnidan/php:latest

ENV PATH "$PATH:/root/.composer/vendor/bin"

RUN composer global require edgedesign/phpqa --update-no-dev

ENTRYPOINT ["docker-php-entrypoint"]