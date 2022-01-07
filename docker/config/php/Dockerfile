FROM php:8.0-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y git && apt install -y unixodbc-dev

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql

# Install Pecl extensions xdebug
RUN pecl install xdebug sqlsrv pdo_sqlsrv \
    && docker-php-ext-enable xdebug pdo_sqlsrv

# Get latest Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www
