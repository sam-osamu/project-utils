FROM alphine:edge

RUN mkdir -p /usr/local/bin
RUN wget https://get.docker.com/builds/Linux/x86_64/docker-latest.tgz -O - \
  | tar -xzC /usr/local/bin --strip=1 docker/docker

ENV TZ=Asia/Tokyo

CMD busybox crond -l 2 -L /dev/stderr -f
