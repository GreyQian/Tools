# Docker

> Docker 是一种开源的容器化平台，用于构建、分发和运行应用程序。其功能类似于虚拟机，但是其启动速度和占用内存会远小于虚拟机。

学习资料：

https://yeasy.gitbook.io/docker_practice/

## 基本概念

这里主要有三个概念

- 镜像
- 容器
- 仓库

### 镜像

对于 `Linux` 而言，内核启动后，会挂载 `root` 文件系统为其提供用户空间支持。而 **Docker 镜像**（`Image`），就相当于是一个 `root` 文件系统。总的来说，docker镜像就是一个特殊的文件系统，提供容器运行时所需的程序，库，资源，配置文件等资源

### 容器

镜像（`Image`）和容器（`Container`）的关系，就像是面向对象程序设计中的 `类` 和 `实例` 一样，镜像是静态的定义，容器是镜像运行时的实体。容器可以被创建、启动、停止、删除、暂停等。

**容器的实质是进程**，但与直接在宿主执行的进程不同，容器进程运行于属于自己的独立的命名空间置、因此容器可以拥有自己的 `root` 文件系统、自己的网络配置、自己的进程空间，甚至自己的用户 ID 空间。容器内的进程是运行在一个隔离的环境里，使用起来，就好像是在一个独立于宿主的系统下操作一样。

### 仓库

仓库可看成一个代码控制中心，用来保存镜像。一个Docker Registry中可以包含多个仓库，每个仓库可以包含多个标签（Tag）,每一个Tag用于对应一个镜像。

通常，一个仓库会包含同一个软件不同版本的镜像，而标签就常用于对应该软件的各个版本。我们可以通过 `<仓库名>:<标签>` 的格式来指定具体是这个软件哪个版本的镜像。如果不给出标签，将以 `latest` 作为默认标签。

以 Ubuntu 镜像为例，`ubuntu` 是仓库的名字，其内包含有不同的版本标签，如，`16.04`, `18.04`。我们可以通过 `ubuntu:16.04`，或者 `ubuntu:18.04` 来具体指定所需哪个版本的镜像。如果忽略了标签，比如 `ubuntu`，那将视为 `ubuntu:latest`。

仓库名经常以 *两段式路径* 形式出现，比如 `jwilder/nginx-proxy`，前者往往意味着 Docker Registry 多用户环境下的用户名，后者则往往是对应的软件名。但这并非绝对，取决于所使用的具体 Docker Registry 的软件或服务。

## 安装Docker

### ubuntu

#### 下载

推荐使用官方的下载脚本下载：

```shell
# $ curl -fsSL test.docker.com -o get-docker.sh
$ curl -fsSL get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh --mirror Aliyun
# $ sudo sh get-docker.sh --mirror AzureChinaCloud
```

这里安装的是稳定版，如果安装测试版，使用注释的命令。

#### 启动

```shell
sudo systemctl enable docker
sudo systemctl start docker
```

#### 建立docker组

```shell
sudo groupadd docker
```

将当前用户添加到docker组

```shell
sudo usermod -aG docker $USER
```



#### 测试安装正确性

```
docker run --rm hello-world
```



### windows



## 使用镜像





































