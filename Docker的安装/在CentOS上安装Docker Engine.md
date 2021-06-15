- [在`CentOS`上安装`Docker Engine`](#在centos上安装docker-engine)
  - [卸载旧版本](#卸载旧版本)
  - [安装`yum-utils`包(它提供`yum-config-manager`实用程序)并设置稳定的存储库](#安装yum-utils包它提供yum-config-manager实用程序并设置稳定的存储库)
    - [安装`yum-utils`包](#安装yum-utils包)
    - [设置稳定的存储库](#设置稳定的存储库)
  - [安装`Docker`引擎，并确认指纹匹配`060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35`](#安装docker引擎并确认指纹匹配060a-61c5-1b55-8a7f-742b-77aa-c52f-eb6b-621e-9f35)
  - [查看`Docker`版本](#查看docker版本)

# 在`CentOS`上安装`Docker Engine`

## 卸载旧版本

```shell
[qiqi@node01 software]$ sudo yum remove docker docker-client docker-client-latest docker-common docker-lastest docker-latest-logrotate docker-logrotate docker-engine
```

## 安装`yum-utils`包(它提供`yum-config-manager`实用程序)并设置稳定的存储库

### 安装`yum-utils`包

```shell
[qiqi@node01 software]$ sudo yum install -y yum-utils
```

### 设置稳定的存储库

* 阿里云存储库

```shell
[qiqi@node01 software]$ sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

## 安装`Docker`引擎，并确认指纹匹配`060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35`

```shell
[qiqi@node01 software]$ sudo yum install docker-ce docker-ce-cli containerd.io
```

## 查看`Docker`版本

```shell
[qiqi@node01 software]$ docker -v
[qiqi@node01 software]$ docker --version
[qiqi@node01 software]$ docker version
```

