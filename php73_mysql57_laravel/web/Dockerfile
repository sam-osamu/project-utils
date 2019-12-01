FROM nginx:latest

RUN sed -E "s/# export LS_OPTIONS=/export LS_OPTIONS=/g" /root/.bashrc -i
RUN sed -E "s/# alias ls=/alias ls=/g" /root/.bashrc -i
RUN sed -E "s/# alias ll=/alias ll=/g" /root/.bashrc -i
RUN sed -E "s/# alias l=/alias l=/g" /root/.bashrc -i

RUN apt-get update
RUN apt-get install -y git vim iputils-ping net-tools

RUN cp -R /etc/nginx/conf.d /etc/nginx/conf.d.org
RUN rm -f /etc/nginx/conf.d/default.conf
COPY ./resource/conf/001-laravel.conf /etc/nginx/conf.d/001-laravel.conf

