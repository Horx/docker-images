## Doc

[Github](https://github.com/Horx/docker-images/tree/master/shadowsocks-go)

## Config

config.json with multi port and password:

```json
{
  "server":"1.1.1.1",
  "port_password": {
    "7001": "SOME_STRONG_PASSWORD",
    "8001": "ANOTHER_PASSWORD"
  },
  "method": "aes-128-cfb",
  "timeout":600,
  "local_port": 1080
}
```

config.json with single port and password:

```json
{
  "server":"1.1.1.1",
  "server_port": 7001,
  "local_port": 1080,
  "password":"SOME_STRONG_PASSWORD",
  "timeout":600,
  "method":"aes-256-cfb"
}
```

## Start

```shell
docker run --name shadowsocks -d \
-v /PATH/TO/config.json:/etc/shadowsocks/config.json \
-p 7001:7001 -p 8001:8001 horx/shadowsocks-go
```

if you just run shadowsocks with single port:

```shell
docker run --name shadowsocks -d \
-v /PATH/TO/config.json:/etc/shadowsocks/config.json \
-p 7001:7001 horx/shadowsocks-go
```
