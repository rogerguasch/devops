FROM composer:latest as composer

FROM php:8.1-fpm

WORKDIR /app

RUN  apt-get update && apt-get install -y ca-certificates git \
  && pecl install xdebug-3.1.3

COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY php/config /usr/local/etc/php/conf.d/

RUN echo "Europe/Berlin" > /etc/timezone && dpkg-reconfigure -f noninteractive tzdata

## Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*