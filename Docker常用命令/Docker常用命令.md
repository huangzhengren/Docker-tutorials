- [`Docker`常用命令](#docker常用命令)
  - [查看镜像列表](#查看镜像列表)
  - [查找镜像](#查找镜像)
  - [拉取镜像](#拉取镜像)
  - [拉取特定标签的镜像](#拉取特定标签的镜像)
  - [查看所有容器列表](#查看所有容器列表)
  - [根据`IMAGE ID`删除镜像](#根据image-id删除镜像)
  - [根据镜像名称和标签删除镜像](#根据镜像名称和标签删除镜像)
  - [根据镜像名称删除镜像，默认删除的是`latest`标签的镜像](#根据镜像名称删除镜像默认删除的是latest标签的镜像)
  - [根据`IMAGE ID` 同时删除多个镜像](#根据image-id-同时删除多个镜像)
  - [根据镜像名称和标签同时删除多个镜像](#根据镜像名称和标签同时删除多个镜像)
  - [根据镜像名称同时删除多个镜像，默认删除的是`latest`标签的镜像](#根据镜像名称同时删除多个镜像默认删除的是latest标签的镜像)
  - [指定`Linux`到`Docker`容器的映射端口](#指定linux到docker容器的映射端口)

# `Docker`常用命令

## 查看镜像列表

```shell
[qiqi@node01 software]$ sudo docker images
```

## 查找镜像

```shell
[qiqi@node01 software]$ sudo docker search hello-world
```

## 拉取镜像

```shell
[qiqi@node01 software]$ sudo docker pull hello-world
```

## 拉取特定标签的镜像

```shell
[qiqi@node01 software]$ sudo docker pull nginx:1.20
```

## 查看所有容器列表

```shell
[qiqi@node01 software]$ sudo docker ps -a
```

## 根据`IMAGE ID`删除镜像

```shell
[qiqi@node01 software]$ sudo docker rmi hello-world
```

## 根据镜像名称和标签删除镜像

```shell
[qiqi@node01 software]$ sudo docker rmi hello-world:latest
```

## 根据镜像名称删除镜像，默认删除的是`latest`标签的镜像

```shell
[qiqi@node01 software]$ sudo docker rmi hello-world
```

## 根据`IMAGE ID` 同时删除多个镜像

```shell
[qiqi@node01 software]$ sudo docker rmi 993ef3592f66 d1165f221234
```

## 根据镜像名称和标签同时删除多个镜像

```shell
[qiqi@node01 software]$ sudo docker rmi nginx:1.20 hello-world:latest
```

## 根据镜像名称同时删除多个镜像，默认删除的是`latest`标签的镜像

```shell
[qiqi@node01 software]$ sudo docker rmi nginx hello-world
```

## 指定`Linux`到`Docker`容器的映射端口

```shell
[qiqi@node01 software]$ sudo docker run -p 80:80 nginx:1.20
```

