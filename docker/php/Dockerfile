FROM php:8.0.24RC1-fpm as core

RUN apt update && apt upgrade -y

RUN apt install -y autoconf libcurl4-openssl-dev pkg-config libssl-dev libzip-dev htop nano curl zip cron \
                                zlib1g-dev sendmail libfreetype6-dev libjpeg62-turbo-dev libmcrypt-dev mcrypt
RUN docker-php-ext-install zip
RUN docker-php-ext-install iconv
RUN pecl install redis-5.3.4
RUN docker-php-ext-install bcmath
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install gd
RUN docker-php-ext-enable bcmath
RUN docker-php-ext-enable mysqli
RUN docker-php-ext-enable redis

#composer 2
RUN curl -sS https://getcomposer.org/installer | php -- \
--install-dir=/usr/bin --filename=composer

#Cleaning container
RUN apt-get clean && rm -rf /var/lib/apt/lists/*
