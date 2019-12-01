FROM mysql:5.7.28
COPY ./my.cnf /etc/mysql/conf.d/

RUN \
  groupmod -g 1000 mysql && \
  usermod -u 1000 -g 1000 mysql && \
  apt-get update && \
  apt-get -y install \
    vim \
    iputils-ping \
    net-tools \
    mysql-client \
    && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

