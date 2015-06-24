FROM golang:1.4.2-wheezy
MAINTAINER hanhor.wu@gmail.com

# Just get shadowsocks-go server. Client is not needed.
RUN CGO_ENABLED=0 go get -a -installsuffix nocgo github.com/shadowsocks/shadowsocks-go/cmd/shadowsocks-server && \
    rm -rf src/* pkg /usr/src/go/pkg/linux_amd64_nocgo

#ADD shadowsocks.json /etc/
CMD shadowsocks-server -c /etc/shadowsocks/config.json
