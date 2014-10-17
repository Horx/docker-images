FROM ubuntu:14.04
MAINTAINER Li Meng Jun "lmjubuntu@gmail.com"

# Set the env variable DEBIAN_FRONTEND to noninteractive
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
# Installing the environment required: ssh
RUN apt-get install -y mysql-server --no-install-recommends && rm -rf /var/lib/apt/lists/*
RUN apt-get clean
# Set locale (fix the locale warnings)
RUN localedef -v -c -i en_US -f UTF-8 en_US.UTF-8 || :

# Copy the files into the container
ADD startup.sh /usr/local/bin/mysql_run
RUN chmod +x /usr/local/bin/mysql_run

ENV TZ Asia/Shanghai

EXPOSE 3306
# Start mysql-server.
CMD ["/usr/local/bin/mysql_run"]
