FROM ruby:2.2
MAINTAINER HanHor "hanhor.wu@gmail.com"

ENV TZ Asia/Shanghai

RUN apt-get update && apt-get install -y nodejs --no-install-recommends && rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y mysql-client --no-install-recommends && rm -rf /var/lib/apt/lists/*

ENV RAILS_VERSION 4.2.1

RUN gem install rails --version "$RAILS_VERSION"
