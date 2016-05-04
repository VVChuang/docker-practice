FROM php:5.6-apache

# Setting php.ini
COPY config/php.ini /usr/local/etc/php/

MAINTAINER VV <vivi@ifalo.com.tw>

# Install composer
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# Install git and zlib
RUN apt-get update -y && apt-get install -y zlib1g-dev git && apt-get clean && rm -r /var/lib/apt/lists/*

# Install zip
RUN docker-php-ext-install zip

# Install laravel
RUN composer global require "laravel/installer"

COPY hello-world /var/www/html

# Change Owner
RUN chown -R www-data /var/www/html/

# Setting root is public
RUN sed -i 's/DocumentRoot.*/DocumentRoot \/var\/www\/html\/public/g' /etc/apache2/apache2.conf
RUN a2enmod rewrite