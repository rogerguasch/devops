FROM php:8.1-fpm

WORKDIR /app

RUN  apt-get update && apt-get install -y ca-certificates git
RUN echo "Europe/Berlin" > /etc/timezone && dpkg-reconfigure -f noninteractive tzdata
