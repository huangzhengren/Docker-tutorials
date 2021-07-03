- [Docker目录挂载命令挂载容器数据卷](#docker目录挂载命令挂载容器数据卷)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，自动创建挂载目录并将主机中的`/qiqi/data`目录挂载到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射](#以守护进程的方式运行容器指定容器名称为qiqi_nginx自动创建挂载目录并将主机中的qiqidata目录挂载到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，匿名挂载目录的方式（匿名目录为`/var/lib/docker/volumes/volume_name/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射](#以守护进程的方式运行容器指定容器名称为qiqi_nginx匿名挂载目录的方式匿名目录为varlibdockervolumesvolume_name_data挂载目录到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，具名挂载目录（`qiqi`）的方式（目录为`/var/lib/docker/volumes/qiqi/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射](#以守护进程的方式运行容器指定容器名称为qiqi_nginx具名挂载目录qiqi的方式目录为varlibdockervolumesqiqi_data挂载目录到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，具名挂载目录（`qiqi`）的方式（目录为`/var/lib/docker/volumes/qiqi/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射,宿主机挂载目录`/qiqi/data`目录可读写，容器内只读](#以守护进程的方式运行容器指定容器名称为qiqi_nginx具名挂载目录qiqi的方式目录为varlibdockervolumesqiqi_data挂载目录到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射宿主机挂载目录qiqidata目录可读写容器内只读)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，具名挂载目录（`qiqi`）的方式（目录为`/var/lib/docker/volumes/qiqi/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射,宿主机挂载目录`/qiqi/data`目录可读写，容器内也可读写](#以守护进程的方式运行容器指定容器名称为qiqi_nginx具名挂载目录qiqi的方式目录为varlibdockervolumesqiqi_data挂载目录到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射宿主机挂载目录qiqidata目录可读写容器内也可读写)
  - [列出容器数据卷命令](#列出容器数据卷命令)
  - [根据` VOLUME NAME(qiqi)`查看数据卷信息](#根据-volume-nameqiqi查看数据卷信息)
  - [根据容器名称查看容器信息](#根据容器名称查看容器信息)
- [注意](#注意)

# Docker目录挂载命令挂载容器数据卷

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，自动创建挂载目录并将主机中的`/qiqi/data`目录挂载到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /qiqi/data:/qiqi/data --name qiqi_nginx -p 80:80 nginx
```

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，匿名挂载目录的方式（匿名目录为`/var/lib/docker/volumes/volume_name/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /qiqi/data --name qiqi_nginx -p 80:80 nginx
```

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，具名挂载目录（`qiqi`）的方式（目录为`/var/lib/docker/volumes/qiqi/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射

```shell
[qiqi@node01 software]$ sudo docker run -dit -v qiqi:/qiqi/data --name qiqi_nginx -p 80:80 nginx
```

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，具名挂载目录（`qiqi`）的方式（目录为`/var/lib/docker/volumes/qiqi/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射,宿主机挂载目录`/qiqi/data`目录可读写，容器内只读

```shell
[qiqi@node01 software]$ sudo docker run -dit -v qiqi:/qiqi/data:ro --name qiqi_nginx -p 80:80 nginx
```

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，具名挂载目录（`qiqi`）的方式（目录为`/var/lib/docker/volumes/qiqi/_data`)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射,宿主机挂载目录`/qiqi/data`目录可读写，容器内也可读写

```shell
[qiqi@node01 software]$ sudo docker run -dit -v qiqi:/qiqi/data:rw --name qiqi_nginx -p 80:80 nginx
```

## 列出容器数据卷命令

```shell
[qiqi@node01 software]$ sudo docker volume ls
```

## 根据` VOLUME NAME(qiqi)`查看数据卷信息

```shell
[qiqi@node01 software]$ sudo docker volume inspect qiqi
```

## 根据容器名称查看容器信息

```shell
[qiqi@node01 software]$ sudo docker inspect qiqi
```

# 注意

* `docker inspect`命令如果容器名称和数据卷同名，默认查看的是容器信息而不是数据卷信息
* 宿主机同一目录可以挂载在不同的容器中

