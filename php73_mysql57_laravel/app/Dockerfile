FROM php:7.2.25-fpm

RUN \
  # Change bash settings.
  sed -E "s/# export LS_OPTIONS=/export LS_OPTIONS=/g" /root/.bashrc -i && \
  sed -E "s/# alias ls=/alias ls=/g" /root/.bashrc -i && \
  sed -E "s/# alias ll=/alias ll=/g" /root/.bashrc -i && \
  sed -E "s/# alias l=/alias l=/g" /root/.bashrc -i && \
  # Preparing for nodejs.
  curl -sL https://deb.nodesource.com/setup_8.x | bash - && \
  # Install the required packages.
  apt-get update && \
  apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libmcrypt-dev \
    git \
    vim \
    iputils-ping \
    net-tools \
    unzip \
    nodejs \
    && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* && \
  # Install the php extensions.
  docker-php-ext-install \
    pdo_mysql \
    mysqli \
    mbstring \
    gd \
    iconv \
    && \
  # Change PHP settings.
  cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini && \
  sed -E "s/post_max_size = 8M/post_max_size = 96M/g" /usr/local/etc/php/php.ini -i && \
  sed -E "s/upload_max_filesize = 2M/upload_max_filesize = 64M/g" /usr/local/etc/php/php.ini -i && \
  sed -E "s/max_file_uploads = 20/max_file_uploads = 30/g" /usr/local/etc/php/php.ini -i && \
  # Install composer.
  curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

