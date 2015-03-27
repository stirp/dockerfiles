FROM php:5.6.7-apache

RUN apt-get update && apt-get install -y curl libcurl3 libcurl3-dev php5-curl
RUN docker-php-ext-install curl pdo_mysql

COPY php.ini /usr/local/etc/php/php.ini
COPY apache.conf /etc/apache2/apache2.conf

RUN /usr/sbin/a2enmod rewrite

ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

CMD ["apache2-foreground"]
