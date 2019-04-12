# 安装Docker CE

## 卸载旧版本
较旧版本的Docker被称为docker或docker-engine。如果已安装这些，请卸载它们以及相关的依赖项

```
$ sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```
## 安装Docker CE
### 使用存储库安装
在新主机上首次安装Docker CE之前，需要设置Docker存储库。之后，您可以从存储库安装和更新Docker。
### 设置存储库
1. 安装所需的包。yum-utils提供了yum-config-manager 效用，并device-mapper-persistent-data和lvm2由需要 devicemapper存储驱动程序。
```
$ sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```
2. 使用以下命令设置稳定存储库。
```
$ sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```
### 安装DOCKER CE
安装最新版本的Docker CE和containerd，或者转到下一步安装特定版本：
```
$ sudo yum install docker-ce docker-ce-cli containerd.io
```