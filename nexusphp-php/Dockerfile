FROM php:fpm-alpine
RUN apk add --no-cache autoconf gcc linux-headers libc-dev make ssmtp && \
        pecl install redis && docker-php-ext-enable redis
RUN apk add --no-cache libpng libpng-dev && \
        docker-php-ext-install pdo pdo_mysql gd \
        && apk del libpng-dev

