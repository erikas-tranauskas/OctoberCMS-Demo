FROM php:8.2-fpm

RUN apt-get update && apt-get install -y \
    zip unzip curl git libpng-dev libonig-dev libxml2-dev libzip-dev \
    && docker-php-ext-install pdo_mysql mbstring zip gd

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN echo "memory_limit = 512M" > /usr/local/etc/php/conf.d/memory-limit.ini