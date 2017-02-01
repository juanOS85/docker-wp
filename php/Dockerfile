FROM php:7.0-apache

# PHP
RUN docker-php-ext-install mysqli

ADD wp.ini /usr/local/etc/php/conf.d/

# Apache
ADD 000-wp.conf /etc/apache2/sites-available/

RUN a2ensite 000-wp.conf
RUN a2dissite 000-default

RUN a2enmod rewrite expires
