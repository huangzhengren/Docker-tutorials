- [通过`Docker`部署`Nginx`](#通过docker部署nginx)
  - [查看镜像列表](#查看镜像列表)
  - [查找`nginx`镜像](#查找nginx镜像)
  - [拉取`nginx`镜像](#拉取nginx镜像)
  - [以守护进程的方式，通过`nginx`镜像创建并运行容器`qiqi_nginx`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口](#以守护进程的方式通过nginx镜像创建并运行容器qiqi_nginx配置宿主机到容器的目录映射指定宿主机到容器的映射端口)
  - [查看容器是否运行](#查看容器是否运行)
  - [通过浏览器访问`http://IP:80`，查看是否正常显示`Nginx`页面](#通过浏览器访问httpip80查看是否正常显示nginx页面)

# 通过`Docker`部署`Nginx`

## 查看镜像列表

```shell
[qiqi@node01 software]$ sudo docker images
```

## 查找`nginx`镜像

```shell
[qiqi@node01 software]$ sudo docker search nginx
```

## 拉取`nginx`镜像

```shell
[qiqi@node01 software]$ sudo docker pull nginx
```

## 以守护进程的方式，通过`nginx`镜像创建并运行容器`qiqi_nginx`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /data/qiqi_nginx:/data --name qiqi_nginx -p 80:80 nginx
```

## 查看容器是否运行

```shell
[qiqi@node01 software]$ sudo docker ps | grep qiqi_nginx
```

## 通过浏览器访问`http://IP:80`，查看是否正常显示`Nginx`页面
