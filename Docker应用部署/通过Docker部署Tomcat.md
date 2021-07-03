# 通过`Docker`部署`Tomcat`

## 查看镜像列表

```shell
[qiqi@node01 software]$ sudo docker images
```

## 查找`tomcat`镜像

```shell
[qiqi@node01 software]$ sudo docker search tomcat
```

### 拉取`tomcat`镜像

```shell
[qiqi@node01 software]$ sudo docker pull tomcat
```

## 以守护进程的方式，通过`tomcat`镜像创建并运行容器`qiqi_tomcat`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口

```shell
[qiqi@node01 software]$ sudo docker run -dit -v /data/qiqi_tomcat:/data/qiqi_tomcat --name qiqi_tomcat -p 8080:8080 tomcat
```

## 查看容器是否运行

```shell
[qiqi@node01 software]$ sudo docker ps | grep qiqi_tomcat
```

## 通过容器名称`qiqi_tomcat`进入容器伪终端

```shell
[qiqi@node01 software]$ sudo docker exec -it qiqi_tomcat /bin/bash
```

## 复制`/usr/local/tomcat/webapps.dist/ROOT`目录到`/usr/local/tomcat/webapps`

```shell
root@70e9bece3f4e:/usr/local/tomcat# cp -r /usr/local/tomcat/webapps.dist/ROOT /usr/local/tomcat/webapps
```

## 通过浏览器访问`http://IP:8080`，查看是否正常显示`Tomcat`页面

