FROM php:7.3-fpm

# install composer
RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer
RUN apt-get update \
&& apt-get install -y \
git \
zip \
unzip \
vim \
imagemagick \
libmagickwand-dev \
libzip-dev

RUN pecl install imagick

RUN apt-get update \
    && apt-get install -y libpq-dev \
    && docker-php-ext-install zip pdo_mysql pdo_pgsql \
    && docker-php-ext-enable imagick \
    && docker-php-ext-configure zip --with-libzip

WORKDIR /var/www/html