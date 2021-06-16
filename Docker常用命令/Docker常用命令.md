- [`Docker`常用命令](#docker常用命令)
  - [查看镜像列表](#查看镜像列表)
  - [查找镜像](#查找镜像)
  - [拉取镜像](#拉取镜像)
  - [拉取特定标签的镜像](#拉取特定标签的镜像)
  - [查看所有容器列表](#查看所有容器列表)

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

