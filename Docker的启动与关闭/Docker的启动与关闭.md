- [`Docker`的启动与关闭](#docker的启动与关闭)
  - [启动`Docker`](#启动docker)
  - [停止`Docker`](#停止docker)
  - [重启`Docker`](#重启docker)
  - [查看`Docker`状态](#查看docker状态)
  - [启用`Docker`开机自启动](#启用docker开机自启动)
  - [禁用`Docker`开机自启动](#禁用docker开机自启动)
- [其他相关命令](#其他相关命令)
  - [查看`Docker`服务是否开机启动](#查看docker服务是否开机启动)
  - [查看`Docker`的资源统计情况](#查看docker的资源统计情况)
  - [查看`Docker`信息](#查看docker信息)
  - [查看`Docker`帮助信息](#查看docker帮助信息)

# `Docker`的启动与关闭

## 启动`Docker`

```shell
[qiqi@node01 software]$ sudo systemctl start docker
[qiqi@node01 software]$ sudo systemctl start docker.service
```

## 停止`Docker`

```shell
[qiqi@node01 software]$ sudo systemctl stop docker
[qiqi@node01 software]$ sudo systemctl stop docker.service
```

## 重启`Docker`

```shell
[qiqi@node01 software]$ sudo systemctl restart docker
[qiqi@node01 software]$ sudo systemctl restart docker.service
```

## 查看`Docker`状态

```shell
[qiqi@node01 software]$ sudo systemctl status docker
[qiqi@node01 software]$ sudo systemctl status docker.service
```

## 启用`Docker`开机自启动

```shell
[qiqi@node01 software]$ sudo systemctl enable docker
[qiqi@node01 software]$ sudo systemctl enable docker.service
```

## 禁用`Docker`开机自启动

```shell
[qiqi@node01 software]$ sudo systemctl disable docker
[qiqi@node01 software]$ sudo systemctl disable docker.service
```

# 其他相关命令

## 查看`Docker`服务是否开机启动

```shell
[qiqi@node01 software]$ sudo systemctl list-unit-files | grep docker
```

## 查看`Docker`的资源统计情况

```shell
[qiqi@node01 software]$ sudo docker stats
```

## 查看`Docker`信息

```shell
[qiqi@node01 software]$ sudo docker info
```

## 查看`Docker`帮助信息

```shell
[qiqi@node01 software]$ sudo docker --help
[qiqi@node01 software]$ sudo docker info --help
```

