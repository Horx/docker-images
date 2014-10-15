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
  rm -rf /var/lib/apt/lists/* && \
  echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
  chown -R www-data:www-data /var/lib/nginx  &&\
  rm -rf /etc/nginx/sites-enabled/default

# Config
# Set number of worker_processes to auto.
# Close default log, you'll open it in your custom conf file.
RUN sed \
    -e 's@worker_processes .*@worker_processes auto;@' \
    -e 's@access_log .*@access_log off;@' \
    -e 's@error_log .*@error_log off;@' \
    -i /etc/nginx/nginx.conf


# Define mountable directories.
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/conf.d/", "/etc/nginx/certs", "/var/log/nginx"]

ENV TZ Asia/Shanghai

# Define working directory.
WORKDIR /etc/nginx

# Define default command.
CMD ["nginx"]

# Expose ports.
EXPOSE 80 443
