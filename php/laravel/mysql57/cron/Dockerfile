FROM gliderlabs/alpine:latest

ENV TZ=Asia/Tokyo

RUN \
  # Install docker client.
  apk add --update ssl_client && \
  mkdir -p /usr/local/bin && \
  wget https://get.docker.com/builds/Linux/x86_64/docker-latest.tgz -O - | tar -xzC /usr/local/bin --strip=1 docker/docker && \
  # Prepare for cron.
  mkdir -p /var/spool/cron/crontabs

COPY ./resource/cron/crontabs/root /var/spool/cron/crontabs/root

CMD busybox crond -l 2 -L /dev/stderr -f
