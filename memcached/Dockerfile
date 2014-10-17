FROM ubuntu:14.04
MAINTAINER HanHor "hanhor.wu@gmail.com"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y --force-yes memcached
ENV TZ Asia/Shanghai

EXPOSE 11211
USER daemon

CMD ["-m", "64"]

ENTRYPOINT memcached
