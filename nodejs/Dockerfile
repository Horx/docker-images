FROM debian:jessie
MAINTAINER HanHor "hanhor.wu@gmail.com"

ENV TZ Asia/Shanghai

RUN apt-get update && apt-get install -y nodejs --no-install-recommends && rm -rf /var/lib/apt/lists/* && ln -s /usr/bin/nodejs /usr/bin/node
