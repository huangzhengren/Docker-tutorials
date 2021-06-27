- [Docker目录挂载命令挂载容器数据卷](#docker目录挂载命令挂载容器数据卷)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，自动创建挂载目录并将主机中的`/qiqi/data`目录挂载到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射](#以守护进程的方式运行容器指定容器名称为qiqi_nginx自动创建挂载目录并将主机中的qiqidata目录挂载到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射)
  - [以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，匿名挂载目录的方式（匿名目录为/var/lib/docker/volume_name/_data)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射](#以守护进程的方式运行容器指定容器名称为qiqi_nginx匿名挂载目录的方式匿名目录为varlibdockervolume_name_data挂载目录到容器名称为qiqi_nginx的qiqidata目录中并建立主机到容器的端口映射)

# Docker目录挂载命令挂载容器数据卷

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，自动创建挂载目录并将主机中的`/qiqi/data`目录挂载到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /qiqi/data:/qiqi/data --name qiqi_nginx -p 80:80 nginx
```

## 以守护进程的方式运行容器，指定容器名称为`qiqi_nginx`，匿名挂载目录的方式（匿名目录为/var/lib/docker/volume_name/_data)挂载目录到容器名称为`qiqi_nginx`的`/qiqi/data`目录中，并建立主机到容器的端口映射

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /qiqi/data --name qiqi_nginx -p 80:80 nginx
```

