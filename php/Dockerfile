FROM php:7.0-apache

ADD 000-wp.conf /etc/apache2/sites-available/

RUN a2ensite 000-wp.conf
RUN a2dissite 000-default
