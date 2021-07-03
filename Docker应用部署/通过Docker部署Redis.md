- [通过`Docker`部署`Redis`](#通过docker部署redis)
  - [查看镜像列表](#查看镜像列表)
  - [查找`redis`镜像](#查找redis镜像)
  - [拉取`redis`镜像](#拉取redis镜像)
  - [以守护进程的方式，通过`redis`镜像创建并运行容器`qiqi_redis`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口](#以守护进程的方式通过redis镜像创建并运行容器qiqi_redis配置宿主机到容器的目录映射指定宿主机到容器的映射端口)
  - [查看容器是否运行](#查看容器是否运行)
  - [通过容器名称`qiqi_redis`进入容器伪终端](#通过容器名称qiqi_redis进入容器伪终端)
  - [使用`redis`客户端工具`redis-cli`登录`redis`服务器](#使用redis客户端工具redis-cli登录redis服务器)
  - [使用客户端工具执行`SET name qiqi`和设置`SET age 25`命令](#使用客户端工具执行set-name-qiqi和设置set-age-25命令)
  - [在后台异步保存当前数据库的数据到磁盘](#在后台异步保存当前数据库的数据到磁盘)
  - [在容器伪终端查看`/data`目录下是否存在`dump.rdb`文件](#在容器伪终端查看data目录下是否存在dumprdb文件)

# 通过`Docker`部署`Redis`

## 查看镜像列表

```shell
[qiqi@node01 software]$ sudo docker images
```

## 查找`redis`镜像

```shell
[qiqi@node01 software]$ sudo docker search redis
```

## 拉取`redis`镜像

```shell
[qiqi@node01 software]$ sudo docker pull redis
```

## 以守护进程的方式，通过`redis`镜像创建并运行容器`qiqi_redis`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /data/qiqi_redis:/data --name qiqi_redis -p 6379:6379 redis
```

## 查看容器是否运行

```shell
[qiqi@node01 software]$ sudo docker ps | grep qiqi_redis
```

## 通过容器名称`qiqi_redis`进入容器伪终端

```shell
[qiqi@node01 software]$ sudo docker exec -it qiqi_redis /bin/bash
```

## 使用`redis`客户端工具`redis-cli`登录`redis`服务器

```
root@c4f51e3c6232:/data# redis-cli -h 192.168.86.4 -p 6379
```

## 使用客户端工具执行`SET name qiqi`和设置`SET age 25`命令

```
192.168.86.4:6379> SET name qiqi
192.168.86.4:6379> SET age 25
```

## 在后台异步保存当前数据库的数据到磁盘

```
192.168.86.4:6379> BGSAVE
```

## 在容器伪终端查看`/data`目录下是否存在`dump.rdb`文件

```shell
root@c4f51e3c6232:/data# ls -l /data
```

