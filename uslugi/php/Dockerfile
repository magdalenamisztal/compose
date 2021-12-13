FROM php:5-fpm

RUN apt-get update && apt-get install -q -y ssmtp mailutils && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install mysql mysqli sysvsem

RUN echo "hostname=localhost" > /etc/ssmtp/ssmtp.conf
