FROM php:fpm-alpine as base
FROM base as builder

MAINTAINER Fisher Pri Catz "fisher.wei@wqfw.de"

RUN apk --no-cache update && \
    apk --no-cache upgrade
RUN apk add --no-cache busybox fcgi autoconf gcc linux-headers libc-dev make && \
    pecl install redis && \
    docker-php-ext-enable redis
RUN apk add --no-cache libpng libjpeg-turbo freetype libzip && \
    apk add --no-cache libpng-dev libjpeg-turbo-dev freetype-dev libzip-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ && \
    docker-php-ext-install pdo pdo_mysql gd zip && \
    apk del libpng-dev libjpeg-turbo-dev freetype-dev libzip-dev
RUN wget -O /usr/local/bin/php-fpm-healthcheck https://raw.githubusercontent.com/renatomefi/php-fpm-healthcheck/master/php-fpm-healthcheck && \
    chmod +x /usr/local/bin/php-fpm-healthcheck

