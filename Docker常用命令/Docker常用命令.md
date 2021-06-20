- [`Docker`常用命令](#docker常用命令)
  - [查看镜像列表](#查看镜像列表)
  - [查找镜像](#查找镜像)
  - [拉取镜像](#拉取镜像)
  - [拉取特定标签的镜像](#拉取特定标签的镜像)
  - [查看所有容器列表](#查看所有容器列表)
  - [查看正在运行的容器列表](#查看正在运行的容器列表)
  - [根据过滤条件筛选`STATUS`为`exited`的容器列表](#根据过滤条件筛选status为exited的容器列表)
  - [显示最新创建的容器(包括所有状态)](#显示最新创建的容器包括所有状态)
  - [显示最近7个创建的容器(包括所有状态)(默认-1)](#显示最近7个创建的容器包括所有状态默认-1)
  - [根据`CONTAINER ID`启动容器](#根据container-id启动容器)
  - [根据`CONTAINER ID`停止容器](#根据container-id停止容器)
  - [根据`CONTAINER ID`删除容器](#根据container-id删除容器)
  - [根据`CONTAINER ID`删除多个容器](#根据container-id删除多个容器)
  - [根据容器名称启动容器](#根据容器名称启动容器)
  - [根据容器名称停止容器](#根据容器名称停止容器)
  - [根据容器名称删除容器](#根据容器名称删除容器)
  - [根据容器名称删除多个容器](#根据容器名称删除多个容器)
  - [根据`CONTAINER ID`或容器名称组合删除多个容器](#根据container-id或容器名称组合删除多个容器)
  - [根据`IMAGE ID`删除镜像](#根据image-id删除镜像)
  - [根据镜像名称和标签删除镜像](#根据镜像名称和标签删除镜像)
  - [根据镜像名称删除镜像，默认删除的是`latest`标签的镜像](#根据镜像名称删除镜像默认删除的是latest标签的镜像)
  - [根据`IMAGE ID` 同时删除多个镜像](#根据image-id-同时删除多个镜像)
  - [根据镜像名称和标签同时删除多个镜像](#根据镜像名称和标签同时删除多个镜像)
  - [根据镜像名称同时删除多个镜像，默认删除的是`latest`标签的镜像](#根据镜像名称同时删除多个镜像默认删除的是latest标签的镜像)
  - [根据`IMAGE ID`或镜像名称同时删除多个镜像](#根据image-id或镜像名称同时删除多个镜像)
  - [指定`Linux`到`Docker`容器的映射端口并运行容器](#指定linux到docker容器的映射端口并运行容器)
  - [带参数并指定容器名称运行容器](#带参数并指定容器名称运行容器)
  - [带参数运行容器，并指定容器名称和映射端口](#带参数运行容器并指定容器名称和映射端口)
  - [使用带标签名称的镜像创建容器，并带参数运行容器，指定容器名称和映射端口](#使用带标签名称的镜像创建容器并带参数运行容器指定容器名称和映射端口)
  - [进入容器伪终端,并指定容器名称和映射端口](#进入容器伪终端并指定容器名称和映射端口)

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

## 查看正在运行的容器列表

```shell
[qiqi@node01 software]$ sudo docker ps
```

## 根据过滤条件筛选`STATUS`为`exited`的容器列表

```shell
[qiqi@node01 software]$ sudo docker ps -f STATUS=exited
[qiqi@node01 software]$ sudo docker ps --filter status=exited
```

## 显示最新创建的容器(包括所有状态)

```shell
[qiqi@node01 software]$ sudo docker ps -l
```

## 显示最近7个创建的容器(包括所有状态)(默认-1)

```shell
[qiqi@node01 software]$ sudo docker ps -n 7
```

## 根据`CONTAINER ID`启动容器

```shell
[qiqi@node01 software]$ sudo docker start aff209e658c5
```

## 根据`CONTAINER ID`停止容器

```shell
[qiqi@node01 software]$ sudo docker stop aff209e658c5
```

## 根据`CONTAINER ID`删除容器

```shell
[qiqi@node01 software]$ sudo docker rm aff209e658c5
```

## 根据`CONTAINER ID`删除多个容器

```shell
[qiqi@node01 software]$ sudo docker rm 203df7bfe593 dd943f947f0c
```

## 根据容器名称启动容器

```shell
[qiqi@node01 software]$ sudo docker start boring_maxwell
```

## 根据容器名称停止容器

```shell
[qiqi@node01 software]$ sudo docker stop boring_maxwell
```

## 根据容器名称删除容器

```shell
[qiqi@node01 software]$ sudo docker rm boring_maxwell
```

## 根据容器名称删除多个容器

```shell
[qiqi@node01 software]$ sudo docker rm nostalgic_johnson gallant_matsumoto
```

## 根据`CONTAINER ID`或容器名称组合删除多个容器

```shell
[qiqi@node01 software]$ sudo docker rm e988fc6c7ea7 focused_hawking
```

## 根据`IMAGE ID`删除镜像

```shell
[qiqi@node01 software]$ sudo docker rmi 993ef3592f66
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

## 根据`IMAGE ID`或镜像名称同时删除多个镜像

```shell
[qiqi@node01 software]$ sudo docker rmi d1165f221234 nginx
```

## 指定`Linux`到`Docker`容器的映射端口并运行容器

```shell
[qiqi@node01 software]$ sudo docker run -p 80:80 nginx:1.20
```

## 带参数并指定容器名称运行容器

```shell
[qiqi@node01 software]$ sudo docker run -it --name qiqi_nginx nginx
```

## 带参数运行容器，并指定容器名称和映射端口

```shell
[qiqi@node01 software]$ sudo docker run -it --name qiqi_nginx -p 80:80 nginx
```

## 使用带标签名称的镜像创建容器，并带参数运行容器，指定容器名称和映射端口

```shell
[qiqi@node01 software]$ sudo docker run -it --name qiqi_nginx -p 80:80 nginx:1.20
```

## 进入容器伪终端,并指定容器名称和映射端口

```shell
[qiqi@node01 software]$ sudo docker run -it --name qiqi_nginx -p 80:80 nginx:1.20 /bin/bash
```

