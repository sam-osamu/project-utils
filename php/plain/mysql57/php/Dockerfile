FROM php:7.3.5-apache

RUN apt-get update
RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libmcrypt-dev git vim iputils-ping net-tools
RUN docker-php-ext-install pdo_mysql mysqli mbstring gd iconv

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini
RUN sed -E "s/post_max_size = 8M/post_max_size = 96M/g" /usr/local/etc/php/php.ini -i
RUN sed -E "s/upload_max_filesize = 2M/upload_max_filesize = 64M/g" /usr/local/etc/php/php.ini -i
RUN sed -E "s/max_file_uploads = 20/max_file_uploads = 30/g" /usr/local/etc/php/php.ini -i

