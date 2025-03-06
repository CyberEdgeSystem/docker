FROM php:8.2-apache

RUN docker-php-ext-install \
    pdo_mysql \
    && a2enmod \
    rewrite

# Убедитесь, что путь правильный относительно Dockerfile
COPY ./laravel.conf /etc/apache2/sites-available/000-default.conf

# Встановлення необхідних залежностей для Composer
RUN apt-get update && apt-get install -y \
    zip unzip git curl

# Встановлення Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
