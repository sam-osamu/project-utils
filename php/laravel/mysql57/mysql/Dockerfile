FROM mysql:latest

COPY ./my.cnf /etc/mysql/conf.d/

RUN \
  apt-get update && \
  apt-get -y install \
    vim \
    iputils-ping \
    net-tools \
    mysql-client \
    && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

