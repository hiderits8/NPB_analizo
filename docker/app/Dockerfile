FROM arm64v8/php:8.3-fpm

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    libicu-dev libzip-dev libonig-dev git unzip \
    && docker-php-ext-install pdo_mysql intl zip opcache \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html