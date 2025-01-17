---
title: Docker入门
date: 2018-08-27 23:41:17
categories: Tools
tags: Docker
---

> Docker 是一个开源的应用容器引擎，让开发者可以打包他们的应用以及依赖包到一个可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。容器是完全使用沙箱机制，相互之间不会有任何接口。

![docker](https://ws2.sinaimg.cn/large/006tNc79gy1fzgc19tnhaj30ku0bqmy1.jpg)

<!-- more -->

# Docker入门

## 初识Docker

### 什么是Docker

#### Docker开源项目

Docker是基于Go语言实现的云开源项目，诞生于2013年初，最初发起者为dotCloud公司。Docker项目目前已加入Linux基金会，遵循Apache2.0协议，全部开源代码均在[https://github.com/docker/docker](https://github.com/docker/docker)上进行维护。

Docker的主要目标是”Build,ship and Run Any App,Anywhere“，即通过对应用组件的封装、分发、部署、运行等生命周期的管理，达到应用级别的”一次封装，到处运行“。这里的应用组件，可以是一个Web应用，也可以是一套数据库服务，甚至是一个操作系统或编译器。

#### Linux容器技术

Docker引擎的基础是Linux容器(Linux Containers,LXC)技术（容器有效第将由单个操作系统管理的资源划分到孤立的组中，以便更好第在孤立的组之间平衡有冲突的资源使用需求。与虚拟化相比，这样既不需要指令级模拟，也不需要即时编译。容器可以在核心CPU本地运行指令，儿不需要任何专门的解释机制。此外，也避免了准虚拟化和系统调用替换中的复杂性。）

#### 从Linux容器到Docker

在Linux容器的基础上，Docker进一步优化了容器的使用体验。Docker提供了各种容器管理工具（如分发、版本、移植等)让用户无需关注底层的操作，可以简单明了地管理和使用容器。

可以简单地将Docker容器理解为一种沙盒。每个容器内运行一个应用，不同的容器相互隔离，容器之间也可以建立通信机制。容器的创建和停止都十分快速，容器自身对资源的需求也十分有限，远远低于虚拟机。很多时候，甚至直接把容器当作应用本身也没有任何问题。

### 为什么使用Docke

#### Docker容器虚拟化的好处

高效地构建应用

#### Docker在开发和运维中的优势

* 更快的交付和部署。使用Docker，开发人员可以使用镜像来快速构建一套标准的开发环境；测试和运维人员可以直接使用相同的开发环境来部署代码。Docker可以快速创建和删除容器，实现快速迭代，大量节约开发、测试、部署的时间。并且各个步骤都有明确的配置和操作，整个过程全程课件，使团队更容易理解应用的创建和工作过程。
* 更高效的资源利用。Docker容器的运行不需要额外的虚拟化管理程序支持，它是内核级的虚拟化，可以实现更高的性能，同时对资源的额外需求很低。
* 更轻松的迁移和扩展。Docker容器几乎可以在任意的平台上运行，包括物理机、虚拟机、公有云、私有云、个人电脑、服务器等。
* 更简单的更新管理。使用Dockerfile，只需要小小的配置修改，就可以替代以往大量的更新工作。并且所有修改都可以以增量的方式进行分发和更新，从而实现自动化并且高效的容器管理。

#### Dcoker与虚拟机比较

* Docker容器很快，启动和停止可以在秒级实现。
* Docker容器对系统资源需求很少，一台主机可以同时运行数千个Docker容器。
* Docker通过类似Git的操作来方便用户获取、分发和更新应用镜像，指令简明，学习成本较低。
* Docker通过Dockerfile配置文件来支持灵活的自动化创建和部署机制，提高工作效率。

| 特性 | 容器 | 虚拟机 |
| --- | --- | --- |
| 启动速度 | 秒级 | 分钟级 |
| 硬盘使用 | 一般为MB | 一般为GB |
| 性能 | 接近原生 | 弱于 |
| 系统支持量 | 单机支持上千个容器 | 一般几十个 |
| 隔离性 | 安全隔离 | 完全隔离 |

#### 虚拟化与Docker

在计算领域，一般指的是计算虚拟化，或通常说的服务器虚拟化。（维基百科：在计算机技术中，虚拟化是一种资源管理技术，是将计算机的各种实体资源，如服务器、网络、内存及存储等，予以抽象、转换后呈现出来，打破实体结构间的不可切割的障碍，使用户可以用比原本的组态更好的方式来应用这些资源。）

虚拟化技术分类

* 基于硬件的虚拟化（不常见）
* 基于软件的虚拟化
    * 应用虚拟化
    * 平台虚拟化
        * 完全虚拟化。虚拟机模拟完整的底层硬件环境和特权指令的执行过程，客户操作系统无需进行修改。
        * 硬件辅助虚拟化：利用硬件辅助支持处理敏感指令来实现完全虚拟化的功能，客户操作系统无需进行修改。
        * 部分虚拟化：只针对部分硬件资源进行虚拟化，客户操作系统需要进行修改。
        * 超虚拟化：部分硬件接口以软件的形式提供给客户机操作系统，客户操作系统需要进行修改。
        * 操作系统及虚拟化：内核通过创建多个虚拟的操作系统实例来隔离不同的进行。容器相关技术属于这个范畴。

Docker和传统虚拟机方式的不同之处
![38b79a7fd4361f03533adffa283d13bc.png](https://ws2.sinaimg.cn/large/0069RVTdgy1fuooutd18sj30lp096wey.jpg)

## Docker的核心概念和安装

> 三大核心概念：镜像、容器、仓库

### 核心概念

#### Docker镜像

Docker镜像类似于虚拟机镜像，可以理解为一个面向Docker引擎的只读模板，包含了文件系统。

镜像是创建Docker容器的基础。通过版本管理和增量的文件系统，Docker提供了一套简单的机制来创建和更新现有的镜像，用户设置可以从网上下载一个已经做好的应用镜像，并通过简单的命令就可以直接使用。

#### Docker容器

Docker容器类似于一个轻量级的沙箱，Docker利用容器来运行和隔离应用。容器是从镜像创建的应用运行实例，可以将其启动、开始、停止、删除，而这些容器都是互相隔离、不可见的。

容器可以看做一个简易版的Linux系统环境（包括root用户权限、进程空间、用户空间和网络空间等），以及运行在其中的应用程序打包成应用盒子。

镜像自身是只读的。容器从镜像启动的时候，Docker会在镜像的最上层创建一个可写层，镜像本身保持不变。

#### Docker仓库

注册服务器是存放仓库的地方，不能将Docker仓库和注册服务器(Registry)混为一谈。

Docker仓库类似于代码仓库，是Docker集中存放镜像文件的场所。每个仓库放着某一类镜像，往往包括多个镜像文件，通过不同的标签(tag)来区分。
根据所存储的镜像公开与否，Docker仓库可以分为公开仓库和私有仓库两种形式。目前最大的公开仓库是Docker Hub，存放了数量庞大的镜像供用户下载。国内的公开仓库包括Docker Pool等，可以提供稳定的国内访问。Docker也支持用户在本地网络创建一个只能自己访问的私有仓库。

### 安装Docker

* Ubuntu
* CentOS
* Windows
* Mac OS

```bash
brew install docker
```

## 镜像

> 镜像是Docker的三大核心概念之一。Docker运行容器前需要本地存在对应的镜像，如果镜像不存在本地，Docker会尝试先从默认镜像仓库下载，用户也可以通过配置，使用自定义的镜像仓库。

### 获取镜像

镜像是Docker运行容器的前提。使用`docker pull`命令从网络上下载镜像。

```bash
docker pull NAME[:TAG]
```

若不显式地指定TAG，则默认会选择latest标签，即下载仓库的最新版本的镜像。

```bash
docker pull ubuntu
# 指定TAG
docker pull ubuntu:14.04
# 已下载
Using default tag: latest
latest: Pulling from library/ubuntu
c64513b74145: Already exists
01b8b12bad90: Already exists
c5d85cf7a05f: Already exists
b6b268720157: Already exists
e12192999ff1: Already exists
Digest: sha256:aade50db36e1ed96716662cfe748789e154c213a711931c66746c42ce34aa296
Status: Downloaded newer image for ubuntu:latest
```

下载过程可以看出，镜像文件一般由若干层组成，行首的c64513b74145代表了各层的ID。下载过程中会获取病输出镜像的各层信息。层其实是AUFS(Advanced Union File System，一种联合文件系统)中的重要概念，是实现增量保存与更新的基础。

两条安装命令相当于：`docker pull registry.hub.docker.com/ubuntu:latest`，即从默认的注册服务器registry.hub.docker.com中的ubuntu仓库下载标记为latest的镜像。

指定完整的仓库注册服务器地址。例如从DockerPool社区的镜像源下载

```bash
docker pull dl.dockerpool.com:5000/ubuntu
```

使用镜像创建容器并运行bash应用

```bash
docker run -t -i ubuntu /bin/bash
```

### 查看镜像信息

```bash
# 列出本地主机上已有的镜像
docker images
# 来源仓库     标签  镜像的ID号  创建时间  大小
# REPOSITORY  TAG  IMAGE ID  CREATED  SIZE
```

TAG信息用来标记来自同一个仓库的不同镜像。仓库中有多个镜像，通过TAG信息来区分发行版本。

```bash
# 使用docker tag为本地镜像添加新的标签
docker tag dl.dockerpool.com:5000/ubuntu:latest ubuntu:latest
```

![a44f587ebdbb248faa256709056b4f7f.png](https://ws4.sinaimg.cn/large/0069RVTdgy1fuoovlxlhxj30jm010745.jpg)
不同标签的镜像的ID完全一致的，说明它们实际上指向了同一个镜像文件，只是别名不同。标签起到了引用或快捷方式的作用。

`docker inspect`可以获取镜像的详细信息，`docker inspect`命令返回的是一个JSON格式的消息，若只要其中一项内容，可以使用-f参数指定。

```bash
docker inspect 2cb0d9787c4d

# 指定镜像ID时，通常使用该ID的前若干个字符组成的可区分字串来替代完整ID
docker inspect -f {{".Architecture"}} 550
```

### 搜寻镜像

使用`docker search`命令可以搜索远端仓库中的共享的镜像，默认搜索Docker Hub官方仓库中的镜像。

支持的参数：

* --automated=false 仅显示自动创建的镜像
* --no-trunc=false 输出信息不截断显示
* -s,--starts=0 指定仅显示评价为指定星级以上的镜像

### 删除镜像

使用`docker rmi`可以删除镜像

```bash
# IMAGE可以为标签或ID
docker rmi IMAGE
# -f 参数强制执行
docker rmi -f ubuntu
```

当一个镜像拥有多个标签时，`docker rmi`只是删除了该镜像多个标签中的指定标签而已，并不影响镜像文件。但当只剩下一个标签时，执行`docker rmi`命令会删除这个镜像文件的所有AUFS层。

当使用`docker rmi`命令后面跟上镜像ID(也可以是ID能进行区分的部分前缀串)时，会先尝试删除所有指定该镜像的标签，然后删除镜像文件本身。

当有镜像创建的容器存在时，镜像文件默认是无法被删除的
```bash
# 删除依赖该镜像的所有容器
docker rm ubuntu
# 然后再删除镜像
docker rmi ubuntu
```

### 创建镜像

> 三种方法：基于已有镜像的容器创建、基于本地模板导入、基于Dockerfile创建

#### 基于已有镜像的容器创建

使用`docker commit`命令，格式：

```bash
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

主要选项包括：

* -a，--author=""作者信息
* -m，--message=""提交信息
* -p，--pause=true提交时暂停容器运行

```bash
# 演示
docker run -ti ubuntu /bin/bash
root@32fe63d85c53:/# touch test
root@32fe63d85c53:/# exit

docker commit -m "add a new file " 32fe63d85c53 test
sha256:4ff6ec596961a2c5f25bcd31e912abd40cc108b7e7e35d53d239b1ef4ff13233

# 使用docker images查看本地镜像列表
docker images
REPOSITORY           TAG                 IMAGE ID            CREATED             SIZE
test                 latest              4ff6ec596961        6 seconds ago       83.5MB
```

#### 基于本地模板导入

使用OpenVZ提供的模板创建。OPENVZ模板的下载地址为[https://download.openvz.org/template/precreated/](https://download.openvz.org/template/precreated/)
导入命令

```bash
cat ubuntu-14.04-x86_64-minimal.tar.gz | docker import - ubuntu:14.04
```

### 存出和载入镜像

可以使用`docker save`和`docker load`命令来存出和载入镜像

#### 存出镜像

```bash
docker save -o ubuntu_14.04.tar ubuntu:14.04
```

#### 载入镜像

```bash
docker load --input ubuntu_14.04.tar

docker load < ubuntu_14.04.tar
```

### 上传镜像

使用`docker push`命令上传镜像到仓库，默认上传到DockerHub官方仓库（需要登录），命令格式为`docker push NAME[:NAME]`，第一次使用时，会提示输入登录信息或进行注册。

## 容器

> 容器时Docker的另一个核心概念，容器就是镜像的一个运行实例，不同的是，它带有额外的可写文件层。

### 创建容器

#### 新建容器

使用`docker create`命令新建一个容器

```bash
docker create -it ubuntu:latest
fb461fbaa2ffe5ebab82548feb5898a1b35b7a3d678b52e1085d94db0f08c6e5
docker ps -a
fb461fbaa2ff        ubuntu:latest       "/bin/bash"         23 seconds ago      Up 5 seconds                            heuristic_lamport
```

使用`docker create`新建的容器处于停止状态，可以使用`docker start`启动。

#### 新建并启动容器

启动容器的方式有两种

* 基于镜像新建一个容器并启动
* 将在终止状态的容器重新启动

`docker run` = `docker create` + `docker start`

```bash
# 使用如下命令输出一个‘hello world’，之后容器自动终止
docker run ubuntu /bin/echo 'hello world'
```

当利用`docker run`创建并启动容器时，Docker在后台运行的标准操作：

1. 检查本地是否存在指定的镜像，不存在就从共有仓库下载。
2. 利用镜像创建并启动一个容器。
3. 分配一个文件系统，并在只读的镜像层外挂载一层可读写层。
4. 从宿主主机配置的网桥接口中桥接一个虚拟接口道容器中去。
5. 从地址池配置一个IP地址给容器。
6. 执行用户指定的应用程序。
7. 执行完毕后容器被终止。

下面命令启动一个bash终端，允许用户进行交互

```bash
docker run -t -i ubuntu:latest /bin/bash
```

> -t：让Docker分配一个伪终端并绑定到容器的标准输出上
> -i：让容器的标准输入保持打开

```bash
docker run -ti ubuntu /bin/bash
root@d3df425445cf:/# ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
root@d3df425445cf:/# pwd
/
root@d3df425445cf:/# ps
  PID TTY          TIME CMD
    1 pts/0    00:00:00 bash
   11 pts/0    00:00:00 ps
root@d3df425445cf:/# exit
exit
# 使用exit退出后，容器自动处于终止状态
```

#### 守护态运行

`-d`参数可以让Docker容器在后台以守护态形式运行

```bash
➜  ~ docker run -d ubuntu /bin/bash -c "while true;do echo hello world;sleep 1;done"
9c9db4515c703021cd2fc3e4583291cb62007ecafa28709f898cf2183eb914c1
➜  ~ docker logs 9c9db4515c703
hello world
hello world
➜  ~ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
9c9db4515c70        ubuntu              "/bin/bash -c 'while…"   41 seconds ago      Up 40 seconds                           elastic_brattain
```

### 终止容器

`docker stop`可以用来终止一个运行中的容器，命令格式`docker stop [-t|--time[=10]]`它会首先向容器发送SIGTERM信号，等待一段时间后（默认为10s），再发送SIGKILL信号终止容器，当Docker容器中指定的应用终结时，容器也自动终止。

处于终止状态的容器，可以通过`docker start`重新启动

`docker restart`可以重启一个运行中的容器。

### 进入容器

#### attach命令

```bash
➜  ~ docker run -idt ubuntu
a9e625b70f57ec70c242e5baf5c9a4431515e0e4d239b81a4729fcc4c08a0eef
➜  ~ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
a9e625b70f57        ubuntu              "/bin/bash"              5 seconds ago       Up 4 seconds                            hungry_brown
➜  ~ docker attach hungry_brown
root@a9e625b70f57:/# ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
```

但是使用attach命令有时候并不方便。当多个窗口同时attach到同一个容器时，所有的窗口都会同步显示。当某个命令因命令阻塞时，其他窗口也无法执行操作。

#### exec命令

Docker自1.3版本起，提供了exec工具，可以直接在容器内运行命令。

```bash
docker exec -ti a9e625 /bin/bash
```

#### nsenter工具

nsenter工具在util-linux包2.33版本后包含。

### 删除容器

`docker rm`可以删除处于终止状态的容器，命令格式为`docker rm [OPTION] CONTAINER [CONTAINER...]`支持的选项包括：

* -f，--force=false强行终止并删除一个运行中的容器
* -l，--link=false删除容器的连接，但保留容器
* -v，--volume=false删除容器挂载的数据卷

### 导入和导出容器

#### 导出容器

导出容器是指导出一个已经创建的容器到一个文件，不管此时这个容器是否处于运行状态，可以使用`docker export`命令，命令格式为`docker export CONTAINER`。

```bash
docker export ce4 > test_for_run.tar
```

#### 导入容器

`docker import`可以导入文件成为镜像

```bash
cat test_for_run.tar | docker import - test/ubuntu:v1.0
```

> 与docker load的区别：
> docker load命令导入镜像存储文件到本地的镜像库
> docker import命令导入一个容器快照到本地镜像库
> 容器快照文件将丢弃所有的历史记录和元数据信息（仅保留容器当时的快照状态），而镜像存储文件保留完整记录，体积也更大。此外，从容器快照文件导入可以重新指定标签等元数据信息。

## 仓库

> 仓库是集中存放镜像的地方，注册服务器是存放仓库的具体服务器，每个服务器上可以有多个仓库，每个仓库下面有多个镜像。仓库地址dl.dockerpool.com/ubuntu，dl.dockerpool.com是注册服务器，ubuntu是仓库名。

### Docker Hub

基础操作

* docker pull 下载镜像到本地
* docker search 搜索公共仓库镜像
* docker push 将本地奖项推动到Docker Hub

镜像资源分为两类

1. 类似ubuntu这样的基础镜像，成为基础或根镜像。这些镜像由Docker公司创建、验证、支持、提供，这样的镜像往往使用单个单词作为名字
2. 类似user/ubuntu这样的镜像，它是由DockerHub的用户user闯将并维护的，带有用户名称前缀，

> 查找时可以通过-s N参数指定仅显示评价为N星以上的镜像。

#### 自动创建

自动创建使用户通过Docker Hub指定跟踪一个目标网站（目前支持GitHub或BitBucket）上的项目，一旦项目发现新的提交，则自动执行创建。
步骤：

1. 创建并登陆Docker Hub，以及目标网站；\*在目标网站中连接账户到Docker Hub
2. 在Docker Hub中配置一个自动创建
3. 选取一个目标网站中的项目（需要含Dockerfile）和分支
4. 指定Dockerfile的位置，并提交创建。

之后可以在Docker Hub的“自动创建”页面中跟踪每次创建的动态。

### 创建和使用私有仓库

#### 使用registry镜像创建私有仓库

通过官方的registry镜像简单搭建一套本地私有仓库环境：

```bash
docker run -d -p 5000:5000 registry
```

## 数据管理

> 用户在使用Docker的过程中，需要能查看容器内应用产生的数据，或者需要把容器内的数据进行备份，甚至多个容器之间进行数据共享，必然涉及到容器内的数据管理操作。容器中管理数据的方式主要有两种方式：1.数据卷 2.数据卷容器

### 数据卷

数据卷是一个可供容器使用的特殊目录，它绕过文件系统，提供很多有用的特性：

1. 数据卷可以在容器之间共享和重用
2. 对数据卷的修改会立马生效
3. 对数据卷的更新，不会影响镜像
4. 卷会一致存在，知道没有容器使用

数据卷的使用用，类似于Linux下对目录或文件进行mmount操作。

#### 在容器内创建一个数据卷

使用`docker run`命令的时候，使用-v编辑可以在容器内创建一个数据卷。多次会用-v标记可以创建多个数据卷。

使用training/webapp镜像创建一个Web容器，并创建一个数据卷挂载到容器的/web目录：

```bash
docker run -d -P --name web -v /webapp training/webapp python app.py
```

> -P是允许外部访问容器需要暴露的端口

#### 挂载一个本地主机文件作为数据卷

-v标记也可以从主机上挂载单个文件到容器中作为数据卷：

```bash
docker run --rm -it -v ~/.zshrc ubuntu /bin/bash
```

## 网络基础配置

### 端口映射实现访问

### 从外部访问容器应用

可以通过`-P`或`-p`参数来指定端口映射。当使用`-P`标记时，Docker会随机映射一个49000~49900的端口至容器内部开放的网络端口。`-p`则可以指定要映射的端口，并且在一个指定端口上只可以绑定一个容器。支持的格式有：`ip:hostport:containerPort | ip::containerPort | hostPort:containerPort`

```bash
docker run -d -P training/webapp python app.py
docker ps -l
d5c545dc020f        training/webapp     "python app.py"     7 seconds ago       Up 6 seconds        0.0.0.0:32774->5000/tcp   infallible_varahamihira
```

#### 映射所有的接口地址

将本地的5000端口映射到容器的5000端口

```bash
docker run -d -p 5000:5000 training/webapp python app.py
```

亦可以多次使用`-p`标记绑定多个端口

```bash
docker run -d -p 5000:5000 -p 3000:80 training/webapp python app.py
```

#### 映射到指定地址的指定端口

```bash
docker run -d -p 127.0.0.1:5000:5000 training/webapp python app.py
```

#### 映射到指定地址的任意端口

使用`ip::containerPort`绑定localhost的任意端口到容器的5000端口，本地主机会自动分配一个端口：

```bash
docker run -d -p 127.0.0.1::5000 training/webapp python app.py
# 使用ud标记来指定udp端口
docker run -d -p 127.0.0.1:5000:5000/udp training/webapp python app.py
```

#### 查看映射端口配置

使用`docker port`查看当前映射的端口配置，也可以查看到绑定的地址

```bash
docker port DOCKERNAME containerPort
```

> 容器有自己的内部网络和IP地址(`docker inspert + 容器ID`可以获取所有的变量值)。

### 容器互联实现容器间通信

> 容器的连接系统是除了端口映射外另一种可以与容器中应用进行交互的方式。它会在源和接收容器之间创建一个隧道，接收容器可以看到源容器指定的信息。

连接系统根据容器的名称来执行，因此需要先自定义一个好记的容器命名。使用`--name`标记可以为容器自定义命名

```bash
docker run -d -P --name web training/webapp python app.py
```

## 八、使用Dockerfile创建镜像

> Dockerfile是一个文本格式的配置文件，用户可以使用Dockerfile快速创建自定义的镜像。

### 基本结构

Docker由一行行命令语句组成，并且支持以#开头的注释行。一般分为四部分：基础镜像信息、维护者信息、镜像操作指令和容器启动执行指令。

```bash
# This dockerfile uses the ubuntu image
# VERSION 2 - EDITION 1
# Author:docker_user
# Command format: Instruction [arguments / command]...

# 第一行必须指定基于的基础镜像
From ubuntu

# 维护者信息
MAINTAINER entercoder entercoder1993@gmail.com

# 镜像的操作指令
RUN echo "deb http://archive.ubuntu.com/ubuntu/ raring main universe" >> /etc/apt/sources.list
RUN apt-get update && apt-get install -y nginx
Run echo "\nadaemon off;;" >> /etc/nginx/nginx.conf

# 容器启动时执行指令
CMD /usr/sbin/nginx
```

* Example1

```bash
From ubuntu
MAINTAINER entercoder entercoder1993@gmail.com

RUN apt-get update && apt-get install -y inotify-tools nginx apache2 openssh-server%
```

* Example2

基于ubuntu，安装firfox和vnc软件，启动后，用户可以通过5900端口通过vnc方式使用firefox

```bash
FROM ubuntu

RUN apt-get update && apt-get install -y xllvnc xvfb firefox
RUN mkdir /.vnc
RUN xllvnc -storepasswd 1234 ~/.vnc/passwd
RUN bash -c 'echo "firefox" >> /.bashrc'

EXPOSE 5900
CMD ["xllvnc,"-forever","-usepw","-create"]
```

### 指令

指令的一般格式为INSTRUCTION arguments，指令包括FROM、MAINTAINER、RUN等

#### FROM

第一条必须为FROM指令。并且，如果在同一个Dockerfile中创建多个镜像时，可以使用多个FROM指令。
格式：`FROM <image>或FROM <image>:<tag>`

#### MAINTAINER

指定维护者的信息
格式：`MAINTAINER <name>`

#### RUN

在shell终端中运行命令，即`/bin/sh -c`
格式：`RUN <command>`
使用exec执行命令，指定其他终端可以用这种方式实现
格式：`RUN ["/bin/bash","-c","echo hello"]`
每条RUN指令将在当前镜像基础上执行指定命令，并提交为新的镜像。当命令较长时可以用\来换行。

#### CMD

支持三种形式

1. `CMD [”executable","param1","param2"]`使用exec执行，推荐方式
2. `CMD command param1 param2`在`/bin/bash`中执行，
3. `CMD ["param1","param2"]`提供给ENTRYPOINT的默认参数

指定启动容器时执行的命令，每个Dockerfile只能有一条CMD命令。如果指定了多条命令，只有最后一条会被执行。如果用户启动容器时制定了运行的命令，则会覆盖掉CMD指定的命令。

#### EXPOSE

告诉Docker服务端容器暴露的端口号，供互联网使用。在启动容器时需要通过-P，Docker主机会自动分配一个端口转发到指定的端口；使用-p，则可以指定哪个本地端口映射过来。
格式：`EXPOSE <port> [<port>...]`

#### ENV

指定一个环境变量，会被后续RUN指令使用，并在容器运行时保持。
格式：`ENV <key> <value>`
```bash
ENV PG_MAJOR 9.3
ENV PG_VERSIOIN 9.3.4
RUN curl -SL http://example.com/postgres-$PG_VERSION.tar.xz | tar -xJC /usr/src/postgress && ...
ENV PATH /usr/local/postgress-$PG_MAJOR/bin:$PATH
```

#### ADD

将复制指定的`<src>`到容器中的`<dest>`。其中`<src>`可以是Dockerfile所在目录的一个相对露冷静(文件或目录)；也可以是一个URL；还可以是一个tar文件(自动解压为目录)。
格式：`ADD <src> <dest>`

#### COPY

复制指定的`<src>`(为Dockerfile所在目录的相对路径，文件或目录)为容器中的`<dest>`。目标路径不存在，会自动创建。使用本地目录为源目录时，推荐使用COPY
格式：`COPY <src> <dest>`

#### ENTRYPOINT

配置容器启动后执行的命令，并且不可被docker run提供的参数覆盖。每个Dockerfile中只能有一个ENTRYPOINT，当指定多个ENTRYPOINT时，只有最后一个生效。
格式：
`ENTRYPOINT ["executable","param1","param2"]`
`ENTRYPOINT command param1 param2(shell中执行)`

#### VOLUME

创建一个可以从本地主机或其他容器挂载的挂载点，一般用来存放数据库和需要保持的数据等。
格式：`VOLUME ["/data"]`

#### USER

指定运行容器时的用户名或UID，后续的RUN也会使用指定用户。当服务不需要管理员权限时，可以通过该命令指定运行用户，并且可以在之前创建所需要的用户，例如：`RUN groupadd -r postgres && useradd -r -g postgres postgres`。要临时获取管理员权限可以使用gosu，而不推荐sudo。
格式：`USER daemon`

#### WORKDIR

为后续的RUN、CMD、ENTRYPOINT指令配置工作目录。可以使用多个WORKDIR指令，后续命令如果参数是相对路径，则会基于之前命令指定的路径。
格式：`WORKDIR /path/to/workdir`

```bash
WORDDIR /a
WORKDIR b
WORKDIR c
RUN pwd
# 则最终路径为/a/b/c
```

#### ONBUILD

配置当所创建的镜像作为其他新创建镜像的基础镜像时所操作的指令。
格式：`ONBUILD [INSTRUCTION]`

### Dockerfile创建镜像

编写完成Dockerfile后，通过`docker build`命令来创建镜像。
格式：`docker build [option] path`
该命令将读取指定路径下(包括子目录)的Dockerfile，并将该路径下所有内容发给Docker服务端，由服务端来创建镜像。因此一般建议放置Dockerfile的目录为空目录。

通过.dockerignore文件(每行添加一条匹配模式)来让Docker忽略路径下的目录和文件。

通过`-t`选项可以指定镜像的标签信息。