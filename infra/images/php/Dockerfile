FROM php:8.0.11-fpm

# Install dependencies including git and php extensions
RUN apt-get update && apt-get install -y --no-install-recommends \
        git \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        && docker-php-ext-install \
        zip \
        intl \
        mysqli \
        pdo pdo_mysql

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# Install Symfony CLI
RUN curl -sS https://get.symfony.com/cli/installer | bash && mv /root/.symfony5/bin/symfony /usr/local/bin/symfony
COPY app/ /var/www/app
WORKDIR /var/www/app