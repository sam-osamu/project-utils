FROM nginx:latest

RUN \
  # Change bash settings.
  sed -E "s/# export LS_OPTIONS=/export LS_OPTIONS=/g" /root/.bashrc -i && \
  sed -E "s/# alias ls=/alias ls=/g" /root/.bashrc -i && \
  sed -E "s/# alias ll=/alias ll=/g" /root/.bashrc -i && \
  sed -E "s/# alias l=/alias l=/g" /root/.bashrc -i && \
  # Install the required packages.
  apt-get update && \
  apt-get install -y \
    git \
    vim \
    iputils-ping \
    net-tools \
    && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* && \
  # Remove nginx default settings.
  cp -R /etc/nginx/conf.d /etc/nginx/conf.d.org && \
  rm -f /etc/nginx/conf.d/default.conf

COPY ./resource/conf/001-laravel.conf /etc/nginx/conf.d/001-laravel.conf

