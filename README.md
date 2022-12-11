# PHP Docker Images

## ghcr.io/arnidan/php-docker/php

Provides latest PHP with installed composer

## ghcr.io/arnidan/php-docker/php-fpm

Provides latest PHP FPM with installed composer and varios of extensions

## ghcr.io/arnidan/php-docker/php-phpqa

Provides image with installed [phpqa](https://github.com/EdgedesignCZ/phpqa) package.

Example of usage:

```
phpqa --analyzedDirs app --output cli --tools phpcs:0,phpmd,phpcpd:0,phpmetrics:0,phploc,pdepend
```

## ghcr.io/arnidan/php-docker/php-testing

Provides image with some specific packages for testing enironment
