FROM php:7.2.24
# RUN useradd -ms /bin/bash laravel
RUN apt-get -y update && apt-get install --no-install-recommends -y \
        git \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libzip-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install pdo_mysql gd
RUN cd /tmp && curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer && mkdir /.composer/
RUN chown -R www-data:www-data /var/www/ && chown -R www-data:www-data /.composer/
WORKDIR /var/www/html