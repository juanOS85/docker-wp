FROM php:7.0-apache

# Required libraries to install PHP extensions
RUN apt-get update && apt-get install -y \
    libicu-dev \
    libmcrypt-dev \
    libxml2-dev \
    zlib1g-dev

# PHP extensions
RUN docker-php-ext-install iconv intl mysqli mcrypt mbstring xml zip

ADD wp.ini /usr/local/etc/php/conf.d/

# Apache
ADD 000-wp.conf /etc/apache2/sites-available/

# Enable default site
RUN a2ensite 000-wp.conf
RUN a2dissite 000-default

# Enable required Apache modules
RUN a2enmod rewrite expires
