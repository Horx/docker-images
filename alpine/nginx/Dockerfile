FROM horx/alpine:latest
MAINTAINER HanHor <hanhor.wu@gmail.com>

RUN apk add --update nginx && \
    rm -rf /var/cache/apk/* && \
    chown -R nginx:www-data /var/lib/nginx

EXPOSE 80 443
