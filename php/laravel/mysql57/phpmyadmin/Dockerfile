FROM phpmyadmin/phpmyadmin:latest

RUN \
  apt-get update && \
  apt-get -y install \
    default-mysql-client \
    vim \
    iputils-ping \
    net-tools \
    && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*
