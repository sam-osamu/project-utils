FROM php:7.2.25-fpm

RUN sed -E "s/# export LS_OPTIONS=/export LS_OPTIONS=/g" /root/.bashrc -i
RUN sed -E "s/# alias ls=/alias ls=/g" /root/.bashrc -i
RUN sed -E "s/# alias ll=/alias ll=/g" /root/.bashrc -i
RUN sed -E "s/# alias l=/alias l=/g" /root/.bashrc -i

RUN apt-get update
RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libmcrypt-dev git vim iputils-ping net-tools unzip
RUN docker-php-ext-install pdo_mysql mysqli mbstring gd iconv

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini
RUN sed -E "s/post_max_size = 8M/post_max_size = 96M/g" /usr/local/etc/php/php.ini -i
RUN sed -E "s/upload_max_filesize = 2M/upload_max_filesize = 64M/g" /usr/local/etc/php/php.ini -i
RUN sed -E "s/max_file_uploads = 20/max_file_uploads = 30/g" /usr/local/etc/php/php.ini -i

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install -y nodejs

