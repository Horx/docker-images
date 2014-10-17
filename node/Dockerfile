FROM ubuntu:14.04
MAINTAINER HanHor "hanhor.wu@gmail.com"

RUN apt-get update && \
    apt-get install -y --force-yes nodejs npm && \
    ln -s /usr/bin/nodejs /usr/bin/node

ENV TZ Asia/Shanghai

WORKDIR /home/core/apps/myapp

EXPOSE 3000

CMD node app.js
