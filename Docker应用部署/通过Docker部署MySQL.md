- [通过`Docker`部署`MySQL`](#通过docker部署mysql)
  - [查看镜像列表](#查看镜像列表)
  - [查找`mysql`镜像](#查找mysql镜像)
  - [拉取`mysql`镜像](#拉取mysql镜像)
  - [以守护进程的方式，通过`mysql`镜像创建并运行容器`qiqi_mysql`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口，设置`MySQL`的`root@'localhost'`的密码为`qiqi`](#以守护进程的方式通过mysql镜像创建并运行容器qiqi_mysql配置宿主机到容器的目录映射指定宿主机到容器的映射端口设置mysql的rootlocalhost的密码为qiqi)
  - [查看容器是否运行](#查看容器是否运行)
  - [通过`Navicat`客户端工具登录`MySQL`，返回报错`2059- Authentication plugin ‘caching_sha2_password' cannot be loaded`，进入容器登录`MySQL`修改`root`用户使用的加密插件](#通过navicat客户端工具登录mysql返回报错2059--authentication-plugin-caching_sha2_password-cannot-be-loaded进入容器登录mysql修改root用户使用的加密插件)
  - [使用`Navicat`客户端工具再次登录`MySQL`，测试连接是否成功](#使用navicat客户端工具再次登录mysql测试连接是否成功)

# 通过`Docker`部署`MySQL`

## 查看镜像列表

```shell
[qiqi@node01 software]$ sudo docker images
```

## 查找`mysql`镜像

```shell
[qiqi@node01 software]$ sudo docker search mysql
```

## 拉取`mysql`镜像

```shell
[qiqi@node01 software]$ sudo docker pull mysql
```

## 以守护进程的方式，通过`mysql`镜像创建并运行容器`qiqi_mysql`，配置宿主机到容器的目录映射，指定宿主机到容器的映射端口，设置`MySQL`的`root@'localhost'`的密码为`qiqi`

```shell
[qiqi@node01 ~]$ sudo docker run -dit -v /data/qiqi_mysql/conf:/etc/mysql/conf -v /data/qiqi_mysql/data:/var/lib/mysql --name qiqi_mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=qiqi mysql
```

## 查看容器是否运行

```shell
[qiqi@node01 software]$ sudo docker ps | grep qiqi_mysql
```

## 通过`Navicat`客户端工具登录`MySQL`，返回报错`2059- Authentication plugin ‘caching_sha2_password' cannot be loaded`，进入容器登录`MySQL`修改`root`用户使用的加密插件

* 进入`qiqi_mysql`容器伪终端

```shell
[qiqi@node01 software]$ sudo docker exec -it qiqi_mysql /bin/bash
```

* 在伪终端中登录`MySQL`

```shell
root@dcd293e39774:/# mysql -uroot -p
```

* 修改`ROOT`用户使用的加密插件

```mysql
mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password;
mysql> ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password;
```

* `FLUSH PRIVILEGES;`报错`ERROR 1820 (HY000): You must reset your password using ALTER USER statement before executing this statement.`，这是因为初始化`MySQL`后，第一次需要重新修改`root`密码

```mysql
mysql> FLUSH PRIVILEGES;
mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'qiqi';
mysql> ALTER USER 'root'@'%' IDENTIFIED BY 'qiqi';
```

* 再次执行`FLUSH PRIVILEGES;`,刷新权限成功

```mysql
mysql> FLUSH PRIVILEGES;
```

## 使用`Navicat`客户端工具再次登录`MySQL`，测试连接是否成功