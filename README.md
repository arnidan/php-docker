# PHP Docker Images

AMD64 and ARM Docker images with PHP FPM

## Updates

The images build every week. A job also checks the upstream base images every hour. When an upstream image changes (for example, after a PHP security release), the images build again.

## Settings

`session.upload_progress.enabled` is `Off` in all images. The file is `$PHP_INI_DIR/conf.d/zz-security.ini`. To turn it on again, override this file in your image.

## ghcr.io/arnidan/php-docker/php-fpm:{version}

Provides latest PHP FPM with installed composer and various of extensions

## ghcr.io/arnidan/php-docker/php-fpm:{version}-with-grpc

Provides latest PHP FPM with installed composer and various of extensions including grpc and protobuf

The grpc and protobuf extensions are prebuilt binaries from the Alpine `phpXY-pecl-grpc` and `phpXY-pecl-protobuf` packages. Their versions can be older than the latest PECL release.
