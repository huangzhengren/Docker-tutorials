- [`Docker`配置国内镜像加速](#docker配置国内镜像加速)
  - [启动`Docker`](#启动docker)
  - [编辑`/etc/docker/daemon.json`，配置`Docker`国内镜像加速](#编辑etcdockerdaemonjson配置docker国内镜像加速)
  - [重新加载服务的配置文件](#重新加载服务的配置文件)
  - [重启`Docker`](#重启docker)
  - [运行`hello-world`镜像](#运行hello-world镜像)
  - [其他相关命令](#其他相关命令)
  - [拉取`hello-world`镜像](#拉取hello-world镜像)
  - [查看镜像列表](#查看镜像列表)
  - [查看所有容器列表](#查看所有容器列表)

# `Docker`配置国内镜像加速

## 启动`Docker`

```shell
[qiqi@node01 software]$ sudo systemctl start docker.service
```

## 编辑`/etc/docker/daemon.json`，配置`Docker`国内镜像加速

* 网易：`http://hub-mirror.c.163.com`
* 中国科学技术大学：`https://docker.mirrors.ustc.edu.cn`

```shell
[qiqi@node01 software]$ sudo bash -c "cat > /etc/docker/daemon.json" << EOF
{
    "registry-mirrors": ["http://hub-mirror.c.163.com", "https://docker.mirrors.ustc.edu.cn"]
}
EOF
```

## 重新加载服务的配置文件

```shell
[qiqi@node01 software]$ sudo systemctl daemon-reload
```

## 重启`Docker`

```shell
[qiqi@node01 software]$ sudo systemctl restart docker.service
```

## 运行`hello-world`镜像

* 从本地寻找hello-world镜像，如果没有，则从远程镜像库中拉取到本地并运行

```shell
[qiqi@node01 software]$ sudo docker run hello-world
```

## 其他相关命令

## 拉取`hello-world`镜像

```shell
[qiqi@node01 software]$ sudo docker pull hello-world
```

## 查看镜像列表

```shell
[qiqi@node01 software]$ sudo docker images
```

## 查看所有容器列表

```shell
[qiqi@node01 software]$ sudo docker ps -a
```



