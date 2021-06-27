- [Docker拷贝命令](#docker拷贝命令)
  - [将文件或目录从容器拷贝到主机](#将文件或目录从容器拷贝到主机)
    - [拷贝容器名称为`qiqi_nginx`的`/qiqi/qiqi.txt`文件到主机`/opt/software`目录下](#拷贝容器名称为qiqi_nginx的qiqiqiqitxt文件到主机optsoftware目录下)
    - [拷贝`CONTAINER ID`为`54587772a751`的`/qiqi/qiqi.txt`文件到主机`/opt/software`目录下](#拷贝container-id为54587772a751的qiqiqiqitxt文件到主机optsoftware目录下)
    - [拷贝容器名称为`qiqi_nginx`中的`/qiqi`目录到主机`/opt/software`目录下](#拷贝容器名称为qiqi_nginx中的qiqi目录到主机optsoftware目录下)
    - [拷贝`CONTAINER ID`为`54587772a751`的`/qiqi`目录到主机`/opt/software`目录下](#拷贝container-id为54587772a751的qiqi目录到主机optsoftware目录下)
  - [将文件或目录从主机拷贝到容器](#将文件或目录从主机拷贝到容器)
    - [拷贝主机中的`/qiqi/qiqi.txt`文件到容器名称为`qiqi_nginx`的`/`目录下](#拷贝主机中的qiqiqiqitxt文件到容器名称为qiqi_nginx的目录下)
    - [拷贝主机中的`/qiqi/qiqi.txt`文件到`CONTAINER ID`为`54587772a751`的`/`目录下](#拷贝主机中的qiqiqiqitxt文件到container-id为54587772a751的目录下)
    - [拷贝主机中的`/qiqi`目录到容器名称为`qiqi_nginx`的`/`目录下](#拷贝主机中的qiqi目录到容器名称为qiqi_nginx的目录下)
    - [拷贝主机中的`/qiqi`目录到`CONTAINER ID`为`54587772a751`的`/`目录下](#拷贝主机中的qiqi目录到container-id为54587772a751的目录下)

# Docker拷贝命令

## 将文件或目录从容器拷贝到主机

### 拷贝容器名称为`qiqi_nginx`的`/qiqi/qiqi.txt`文件到主机`/opt/software`目录下

```shell
[qiqi@node01 software]$ sudo docker cp qiqi_nginx:/qiqi/qiqi.txt /opt/software/
```

### 拷贝`CONTAINER ID`为`54587772a751`的`/qiqi/qiqi.txt`文件到主机`/opt/software`目录下

```shell
[qiqi@node01 software]$ sudo docker cp 54587772a751:/qiqi/qiqi.txt /opt/software/
```

### 拷贝容器名称为`qiqi_nginx`中的`/qiqi`目录到主机`/opt/software`目录下

```shell
[qiqi@node01 software]$ sudo docker cp qiqi_nginx:/qiqi /opt/software/
```

### 拷贝`CONTAINER ID`为`54587772a751`的`/qiqi`目录到主机`/opt/software`目录下

```shell
[qiqi@node01 software]$ sudo docker cp 54587772a751:/qiqi /opt/software/
```

## 将文件或目录从主机拷贝到容器

### 拷贝主机中的`/qiqi/qiqi.txt`文件到容器名称为`qiqi_nginx`的`/`目录下

```shell
[qiqi@node01 software]$ sudo docker cp /qiqi/qiqi.txt qiqi_nginx:/
```

### 拷贝主机中的`/qiqi/qiqi.txt`文件到`CONTAINER ID`为`54587772a751`的`/`目录下

```shell
[qiqi@node01 software]$ sudo docker cp /qiqi/qiqi.txt 54587772a751:/
```

### 拷贝主机中的`/qiqi`目录到容器名称为`qiqi_nginx`的`/`目录下

```shell
[qiqi@node01 software]$ sudo docker cp /qiqi/ qiqi_nginx:/
```

### 拷贝主机中的`/qiqi`目录到`CONTAINER ID`为`54587772a751`的`/`目录下

```shell
[qiqi@node01 software]$ sudo docker cp /qiqi/ 54587772a751:/
```

