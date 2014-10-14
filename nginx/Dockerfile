FROM ubuntu:14.04
MAINTAINER HanHor "hanhor.wu@gmail.com"

# Set the env variable DEBIAN_FRONTEND to noninteractive
ENV DEBIAN_FRONTEND noninteractive

# Install.
RUN \
  sed -i 's/archive.ubuntu.com/mirrors.aliyun.com/' /etc/apt/sources.list && \
  apt-get update && \
  apt-get install -y software-properties-common && \
  add-apt-repository -y ppa:nginx/stable && \
  apt-get update && \
  apt-get install -y nginx && \
  apt-get clean && \
  sed -e 's@ndaemon *@ndaemon off@' && \
  sed -e 's@access_log *@access_log off@' && \
  sed -e 's@error_log *@error_log off@' && \
  chown -R www-data:www-data /var/lib/nginx  &&\
  rm /etc/nginx/sites-available/default

# Define mountable directories.
VOLUME ["/etc/nginx/conf.d/", "/etc/nginx/certs", "/var/log/nginx"]

ENV TZ Asia/Shanghai

# Define working directory.
WORKDIR /etc/nginx

# Define default command.
CMD ["nginx"]

# Expose ports.
EXPOSE 80
EXPOSE 443
