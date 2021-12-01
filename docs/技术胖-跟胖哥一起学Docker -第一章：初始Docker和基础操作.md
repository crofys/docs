# 技术胖-跟胖哥一起学Docker -第一章：初始Docker和基础操作
如果你在一个 IT 公司，并且是一个技术人员，就一定要学 Docker。注意我这里用到了技术人员，也就是说无论是前后端开发还是运维测试，Docker 都是必学的技术。

![](https://newimg.jspang.com/Docker_logo_new_old.jpg)

因为截至到 2020 年，容器技术（Container）技术在国内一线互联网公司的生产环境中使用比例已经占到了 50%。现在是 2021 年，这个比例一定会有所上升。也就是说容器技术得到了快速的普及。

\[

## 01.\[导语] 为什么要学习 Docker 技术

](#toc21)

**现阶段去大厂面试，几乎任何技术岗位，都希望你有容器技术的使用经验。就跟你去面试程序员，必须要面试算法和数据结构一样了。** 

这也是我为什么要出一套免费 Docker 视频教程的原因, 教大家现实工作中使用的技术，面向工资学习。

\[

### 一. 自我介绍和教程简介

](#toc32)

我相信看文章的大多数都是我的老朋友了，但按惯例，新课开始还是要来个自我介绍。

![](https://newimg.jspang.com/Docker_self_Introduction.jpg)

**本套视频完全免费，每周会更新 3-5 集左右，总更新时间会超过 2 个月。** 

所以我们一起学习 Docker 技术，建议扫码加一下我的微信公众号。这样每次更新你都可以收到提醒信息，保证不落课。我也会在公众号文章的下方回答小伙伴的问题和互动。

本视频讲解的是 Docker20.x 的版本，也就是说 Docker 的最新版本。本套课程会专注于容器技术本身，从基础开始到原理的深入都会讲到。

视频正确的观看方法，就是你先看视频，不用作任何的笔记，所有的课程内容，我都会在公众号和博客里进行更新。

**需要的前置知识**

-   需要会一门编程语言，可以是 Python、JavaScript、Java、C++..........
-   熟悉基本的 Linux 命令，因为课程还是面向工作的，所以会以 Linux 系统为主, 进行学习。

\[

### 二. 简述软件基础架构的发展史

](#toc33)

为了先来看一段简单的基础架构历史。

-   90 年代是传统服务器，在一些公司都会买小型机、塔式服务器、刀片式服务器，一个服务器上跑一个服务（一种应用），缺点是大量服务器资源被浪费；
-   2000 年开始流行虚拟化技术，代表是 VMware 和 VirtualBox 软件，在一个服务器上可以模拟出多台虚拟服务器，缺点是占有服务器资源较多，需要虚拟内存和 CPU，占有服务器大量资源；
-   2005 年 - 2015 年云技术 Cloud 开始流行，这个时候产生了很多大型云服务商，国际的有亚马逊、国内的阿里云，都是这个时期成长起来的公司。云技术也为容器技术提供了良好的生长土壤。
-   2015 年以后 Container（容器）时代，现在无论是国际还是国内大厂，无一例外的都在使用容器技术。那最为出名的就是 Docker。

通过这段历史，你可以了解到软件基础架构的变革。所以现在无论时开发人员、还是运维测试人员，都需要会使用容器技术，就像我们会使用基本的操作系统一样重要。

\[

### 三. Container（容器技术）的概念

](#toc34)

我们通过百度查询，可以得到对容器技术的概念。

> Linux Container 容器技术的诞生 (2008 年) 就解决了 IT 世界里 “集装箱运输” 的问题。Linux Container（简称 LXC），它是一种内核轻量级的操作系统层虚拟化技术。Linux Container 主要由 Namespace 和 Cgroup 两大机制保证实现。

这段鬼话非常难理解，我用我的话解释一下，其实**容器就想一个打包工具，打包的不仅是你的程序，也包括运行环境。** 就好比你把你的开发主机和开发程序完全复制了一份，别人拿到后就不需要搭建环境，也不需要根据环境进行调试，直接就可以运行了。

这节算是一个导学内容，简单总结一下：无论你是开发、测试或是运维，都需要学习 Docker 技术。因为截至 2020 年 Docker 在生产环境的使用已经超过 50%，并且还在迅速发展。我们还介绍了一下软件基础 架构的发展史。并对 Container 的概念作了一个基本的介绍。

下节课我们将安装 Docker 软件，真正开启 Docker 的大门。

\[

## 02.\[安装] 在 Windos11 系统下安装 Docker

](#toc25)

上节课基本都是理论，作为程序员，我不喜欢理论，能动手尽量不吵吵，这是基本原则。这节我们就在 Windows11 下安装 Docker 系统（Docker Desktop for windows）。当然 Windows10 下的安装方法基本类似，这里选用最新的操作系统 Win11。

\[

### 一. 在安装 Docker 之前的配置

](#toc36)

在 Windows 系统上安装 Dcoker 之前需要作几项必要的配置，否则就会安装失败。

**1. 开启 BIOS 中的虚拟化 - BIOS virtualization**

这一步每个主版的型号不同，所以开启方法也不太一样。你要根据你的主板型号去网上搜索开启方法。

![](https://newimg.jspang.com/Docker2_1_BIOS.jpg)

我这里给出几种主板的开启方式图片，这些图片是不同主板的 BIOS 和开启`BIOS virtualization`方法，可以帮助你快速开启。但具体如何开启你的 BIOS 虚拟化选项，最好的办法还是百度或者 Google 去根据主板的型号，进行开启。

> 我的主板是 UEFI BIOS 的，重启电脑后狂按 Del 键，进入 BIOS 后。按 F7 进入高级模式，打开 advanced 高级选项中 cpu congiguration 处理器配置中 intel vitualization technology 虚拟化支持选项，设置为 enabled 开启，F10 保存退出即可解决。

这样就开启了主板的 BIOS 虚拟化 (BIOS virtualization) 。

**2. 在 windows10 上开启 Hyper-V**

Hyper-V 是微软的一款虚拟化产品，能够实现桌面虚拟化。所以如果是 windows10 系统，上面是自带 Hyper-V 的，你只要开启就好。安装 Docker 需要开启 Windows 上的 Hyper-V 功能。

【此处配图 - 用 PowerShell 安装 Hyper-V】

![](https://newimg.jspang.com/Docker2.3_PowerShell-Hyper-v.png)

1.  通过管理员身份打开 PowerShell 控制台。
2.  运行以下命令:

```jsx
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```

如果无法找到此命令，请确保你以管理员身份运行 PowerShell。

安装完成后，需要重启电脑。

**3. 设置 Hyper-V 角色和容器**

启用 Hyper-V 之后，需要设置一下 Hyper-V 的角色，步骤如下。

【此处配图 - 设置 Hyper-V 角色】

Win10 下的步骤

1\. 右键单击 windows 按钮并选择” 应用和功能 “。

2\. 选择相关设置下右侧的” 程序和功能 “。

3\. 选择” 打开或关闭 Windows 功能 “。

4\. 选择”Hyper-V“和 “容器”，然后单机” 确定“。

![](https://newimg.jspang.com/Docker2_2_Hyper-v.png)

Win11 下的步骤：

1.  点击开始按钮，在搜索框里搜索控制面板
2.  打开控制面板，又上角的查看方式，改为 “小图标”
3.  选择左侧的 “程序和功能” 选项
4.  选择 “启用或关闭 Windows 功能”
5.  找到 “容器” 和“Hyper-V”选项，把钩打上。

![](https://newimg.jspang.com/Docker2_5_Container.jpg)

上面 三个事情做好后，就可以正式开启安装 Docker 软件了。

\[

### 二. 安装 Docker 到 Windows 上

](#toc37)

直接去 Docker 官网进行下载。

> Dokcer 的官网是 - [https://docker.com](https://docker.com/)

进入官网后，选择`Products(产品)`，然后选择`Docker Desktop`，进入下载页面，点击进行下载。这个软件大概有 520M 左右，所以可能要下载一会（根据网速不同，）。

![](https://newimg.jspang.com/Docker2_4_website_download.png)

下载完成后，双击进行安装。这里直接默认选项安装就好。安装完成后重启电脑。

![](https://newimg.jspang.com/Docker2_6_setup_over.png)

\[

### 三. 测试安装是否成功

](#toc38)

重启之后，Dokcer 会随系统启动。可以通过命令行输入 `docker version` 命令来判断是否已经安装成功。如果可以同时出现`client`和`Server` 两项，说明已经安装成功了。

类似下面的命令

```jsx
PS C:\Users\Administrator> docker version
Client:
 Cloud integration: 1.0.17
 Version:           20.10.7
 API version:       1.41
 Go version:        go1.16.4
 Git commit:        f0df350
 Built:             Wed Jun  2 12:00:56 2021
 OS/Arch:           windows/amd64
 Context:           default
 Experimental:      true

Server: Docker Engine - Community
 Engine:
  Version:          20.10.7
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.13.15
  Git commit:       b0f5bc3
  Built:            Wed Jun  2 11:54:58 2021
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.4.6
  GitCommit:        d71fcd7d8303cbf684402823e425e9dd2e99285d
 runc:
  Version:          1.0.0-rc95
  GitCommit:        b9ee9c6314599f1b4a7f497e1f1f856fe433d3b7
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
```

总结：这节主要学习了 Docker 在 windows 下的安装，简单讲就三步。

> 1.  开启 BIOS 虚拟化设置；
> 2.  开启 windows 的 Hyper-V 和容器;
> 3.  去官网下载 Docker 桌面版并安装;

好，下节我们再来看看在 Linux 上如何安装 Docker。

\[

## 03.\[安装] Linux 下安装 Docker

](#toc29)

这节我们将在 Linux 系统下安装 Docker，至于如何你能有 Linux 系统，需要自己想想办法，可以买，可以自己作系统，也可以直接上虚拟机，方法很多。我这里买了一台特价的 99 元一年的低配置云服务器，用来瞎折腾用的。

\[

### 操作系统说明

](#toc310)

我这里使用 Xshell 来远程连接主机。我的系统是 CentOS7 的版本，算是一个比较老的版本。没有用 CentOS 8 的主要原因是服务器配置太低，达不到安装 CentOS 8 的要求。

如果你使用的是 Ubuntu 系统或者其他版本的 LInux 系统，不用担心，安装方法几乎是一样的。因为这种安装方法是相对简单快速。

\[

### 开始安装 Docker

](#toc311)

安装我们直接使用`shell`脚本来进行安装，安装脚本的地址如下。

> get.docker.com

可以直接使用 curl 命令下载这个 shell 脚本

```jsx
curl -fsSL get.docker.com -o get-docker.sh
```

这个下载命令并没有成功提示，所以下载完成后，可以使用`ls`命令查看一下。如果已经存在了，就可以使用`sh`命令，直接执行这个脚本了。

```jsx
sh get-docker.sh
```

回车后就开始安装 Docker 了。这里需要注意，如果你不是`root`用户，是需要使用`sudo`命令或者给用户 sudo 权限。

安装过程大概要 3-4 分钟左右，也是主要看网速和服务器性能。

\[

### 检测是否安装成功

](#toc312)

安装完成后，依然通过`docker version`命令检查是否安装成功。

如果只显示下面的这些信息，也就是只启动了客户端`Client`。

```jsx
Client: Docker Engine - Community
 Version:           20.10.7
 API version:       1.41
 Go version:        go1.13.15
 Git commit:        f0df350
 Built:             Wed Jun  2 11:58:10 2021
 OS/Arch:           linux/amd64
 Context:           default
 Experimental:      true
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
```

这时候要使用`systemctl start`命令，开启 Docker 服务端。

```jsx
sudo systemctl start docker
```

开启后，再使用`sudo docker version`来看一下，如果有类似下面的信息，说明已经安装成功了。

```jsx
Client: Docker Engine - Community
 Version:           20.10.7
 API version:       1.41
 Go version:        go1.13.15
 Git commit:        f0df350
 Built:             Wed Jun  2 11:58:10 2021
 OS/Arch:           linux/amd64
 Context:           default
 Experimental:      true

Server: Docker Engine - Community
 Engine:
  Version:          20.10.7
  API version:      1.41 (minimum version 1.12)
  Go version:       go1.13.15
  Git commit:       b0f5bc3
  Built:            Wed Jun  2 11:56:35 2021
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          1.4.8
  GitCommit:        7eba5930496d9bbe375fdf71603e610ad737d2b2
 runc:
  Version:          1.0.0
  GitCommit:        v1.0.0-0-g84113ee
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
```

总结：在 Linux 下安装 Docker 比 Windows 安装要简单，主要是官方贴心的准备好了对应的`shell`脚本文件，我们执行就好。但需要注意的是必须要有 sudo 权限。

本来还应该演示一下 Mac 系统下的安装，无奈家中贫寒，实在没有 Mac 电脑。所以如果你是 Mac 电脑，就自己搜索一下百度，一定也可以安装成功的。

\[

## 04.\[容器] 创建容器相关命令

](#toc213)\[

### 镜像和容器的区别

](#toc314)

在讲如何创建容器前，我们要对 Docker 中的镜像和容器有个简单的理解。其实这两个东西有类似的地方，也有不同。所以很多时候新手容易把这两个概念弄混淆。这里我用最简单的比喻来讲。

> 镜像像是一个包含了 OS 文件系统和应用的对象，类似虚拟机的模板（比如 Window10 镜像）。如果你是一个开发 者，可以把镜像看成面向对象编程中的只读类 (read-only Class)。

> 容器和镜像几乎一模一样，唯一的区别是镜像是只读的，而容器上面有一个可读写层。所以容器 = 镜像 + 读写层。

这里用一张图让你更清楚的了解容器和镜像的区别。

![](https://newimg.jspang.com/Docker4_ContainerAndImages.jpg)

\[

### 创建一个新容器

](#toc315)

当你明白了什么是镜像和容器后，我们一起试着来创建一个容器。创建容器的命令是。

```jsx
docker container run < image name >
```

`image`代表一个镜像的名称，如果你想使用的镜像名称是 nginx，就可以写成下面的样子。

```jsx
docker container run nginx
```

如果是使用 ubuntu 镜像，命令就变成了下面的写法。

```jsx
docker container run ubuntu
```

输入完成后，直接回车。如果系统中没有这个镜像，Docker 会自动去`Docker Hub`上拉取对应的镜像到本地，然后执行对应的`Shell`脚本，脚本会把镜像自动安装到 Doker 容器里，并最终启动对于的镜像服务。

> Docker Hub 是 Docker 官方的镜像和社区，里边有很多开发者制作好的镜像，我们可以直接使用这些镜像。如果你有能力，也可以制作镜像，并上传到 Docker Hub。

注意，这时候容器是在前台运行的。

\[

### 查看容器的相关命令

](#toc316)

创建万容器后，如果查看这个容器的信息和状态那？这时候你可以使用下面的命令。

```jsx
docker container ls
```

（ps：注意你这时候需要新打开一个 PowerShell 窗口，再执行命令）

输入命令后，就会显示出当前已经存在的容器，并且会列出对应的信息。

-   CONTAINER ID : 容器对应的 ID，这个是唯一的
-   IMAGE : 使用的镜像名称，显示不同
-   COMMAND : 执行的相关命令
-   CREATED: 创建的时间
-   STATUS: 目前镜像的状态，一般会有两种状态 Up 和 Exited.
-   PORTS: 协议和端口
-   NAMES: 容器的名称，名字是 Docker 随机生成的

还有一种查看容器的命令，不过这是以前的命令，不建议使用

```jsx
docker container ps  (不建议使用)
```

\[

### 停止容器的相关命令

](#toc317)

如果你想停止掉一个正在运行的容器，可以使用下面的命令：

```jsx
docker container stop <name or ID>
```

当容器停止后，再使用查看命令进行查看，你会发现没有任何容器。

```jsx
docker container ls
```

这时候你要查看你所有容器，包含已经停止的容器，可以加一个`-a`, 参数。

```jsx
docker container ls -a
```

\[

### 删除容器

](#toc318)

当我们停止容器之后，容器并没有删除，而只是停止掉了。这时候你可以使用下面的命令删除容器。

```jsx
docker container rm <name or ID>
```

\[

### 相关命令简写方法

](#toc319)

-   容器的创建：docker container run nginx 简写方法 docker run nginx
-   容器的列出 (up): docker container ls 简写方法 docker ps
-   容器的列出（up 和 exit）：docker container ls -a 简写方法 docker ps -a
-   容器的停止 ： docker container stop 简写方法 docker stop
-   容器的删除：docker container rm 简写方法 docker rm

![](https://newimg.jspang.com/Docker4_Container_shell.png)

个人建议尽量不要使用简写方法，写全更语义化，减少出错机会。

\[

## 05.\[容器] 多容器操作和强制删除容器的方法

](#toc220)

相信通过上节的学习，小伙伴们已经对容器的创建、查看和删除命令有了认识。这节我们讲一下对于多个容器的操作。因为在实际工作中，我们往往管理的都是多个容器，这也是容器的主要特点之一。

\[

### 创建多个容器

](#toc321)

在 WIndows 环境下我们来作这个，先打开三个 PowerShell 窗口，然后在每个窗口中输入创建容器的命令，这里以`Nginx`镜像为例。

```jsx
docker container run nginx
```

然后再重新打开一个`PowerShell`窗口，输入查看命令，查看已经开启的容器。

```jsx
docker container ls
```

可以看到现在已经有 3 个开启的容器了。

```jsx
PS C:\Users\Administrator> docker container ls
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS     NAMES
91cc350cc044   nginx     "/docker-entrypoint.…"   6 minutes ago   Up 6 minutes   80/tcp    optimistic_kalam
24f7f578deff   nginx     "/docker-entrypoint.…"   6 minutes ago   Up 6 minutes   80/tcp    focused_lovelace
06fbdca5b9fb   nginx     "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes   80/tcp    epic_wright
```

\[

### 停止多个容器

](#toc322)

现在要把三个容器用一个命令停掉，笨的方法是直接加上 ID 或名字。

```jsx
docker container stop  <ID1  ID2  ID3>
```

但如果你想想，比如这时候有 100 个容器，我们用这种方法就会非常麻烦。

这时候我们需要学一个新的查看命令，比如只查看现在所有容器的 ID, 命令如下。

```jsx
docker container ps -aq
```

这样就打印出了所有容器的 ID，这时候包括没有开启的。

```jsx
91cc350cc044
24f7f578deff
06fbdca5b9fb
6fcbf0e96849
```

有了这个命令之后，我们就可以作一个命令组合。

```jsx
docker container stop $(docker container ps -qa)
```

命令执行后，会返回给我们容器的编号，说明已经停止了。可以使用下面的命令再次查看。

```jsx
docker container ls -a 
```

这时候就可以看到，所有容器不在是`up`状态了，而是`exited`状态。

```jsx
**PS C:\Users\Administrator> docker container ls -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
91cc350cc044   nginx     "/docker-entrypoint.…"   36 minutes ago   Exited (0) 10 seconds ago             optimistic_kalam
24f7f578deff   nginx     "/docker-entrypoint.…"   37 minutes ago   Exited (0) 10 seconds ago             focused_lovelace
06fbdca5b9fb   nginx     "/docker-entrypoint.…"   38 minutes ago   Exited (0) 10 seconds ago             epic_wright
6fcbf0e96849   nginx     "/docker-entrypoint.…"   46 hours ago     Exited (0) 46 hours ago               great_raman**
```

\[

### 删除多个容器

](#toc323)

会了停止多个容器，那删除多个容器就很简单了。

```jsx
docker container rm $(docker container ps -aq)
```

\[

### 强制删除容器

](#toc324)

正在运行的容器，是不可以直接删除的，会报错。我们来做个实验。新建一个容器.

```jsx
docker container run nginx
```

然后新开一个`PowerShell`，直接使用 rm 命令删除。

```jsx
docker container rm <ID or Image Name >
```

这时候会直接报错。报错内容如下。

```jsx
Error response from daemon: You cannot remove a running container 21d0ec08e126efe73482264a588a3169c9d5b2253e7d53657ab8ddcf0f8302ba. Stop the container before attempting removal or force remove
```

报错信息大体就是不能删除没有`stop`的容器。但这时候就是要删除，你可以使用强制删除命令进行删除。

```jsx
docker container rm <ID or Image Name > -f
```

输入完成就删除成功了。

这节课就到这里了，我们学习了如何批量停止和删除多个容器的方法。然后又讲了如何强制删除正在运行的容器。

\[

## 06.\[容器] attached 和 detached 模式

](#toc225)

这节学习一下 Docker 的端口映射和两种运行模式 - attached 和 detached 模式。先来看如何把一个容器的端口映射到主机的 80 端口上。

\[

### Docker 端口映射

](#toc326)

在开启端口映射之前，你首先要之道 Docker 对应的容器端口是多少。比如 Nginx 镜像的端口诗`80`。知道这个端口后，就可以在启动容器的时候，用`-p <port:port>` 的形式，启用映射了。

用 Nginx 举例:

```jsx
docker container run -p 80:80 nginx
```

等待项目启动后，打开浏览器窗口，在地址栏输入`127.0.0.1`，就可以打开 nginx 的默认网址。

![](https://newimg.jspang.com/Docker6-1NginxToCompoer.png)

第一个端口是映射到服务器本机的端口; 第二个端口是 Docker 容器使用的端口。 比如你想把 Docker 的 80 端口，映射到服务器的 90 端口。

```jsx
docker container run -p 90:80 nginx
```

\[

### attached 模式

](#toc327)

两种模式最简单的对比理解就是：attached 模式在前台运行，detached 模式在后台运行。

当你打开`127.0.0.1`网址的时候，`PowerShell`上打印出了相关的日志（log），平且每访问一次，都会增加一条日志。也就是说 Docker 容器的日志会实时的展现到窗口并且占用此端口。这种模式叫做`attached`模式。

![](https://newimg.jspang.com/Docker6-2Nginx-log.png)

在 windows 系统下并不是一个完整的 attached 模式，只是帮我们打印出了 Log。现在到 Linux 服务器上，这时候你按`Ctrl+C`, 就会停止掉`Docker`服务。而现实中我们工作的环境恰恰是这种 Linux 环境。

也就是在 Linux 上你的操作命令，会直接传递个`Docker 容器`。这个缺点就是很容易误操作，比如在公司的生产环境中，你直接一个`Ctrl+C`，整个服务就崩掉了，你这个月的绩效也就没有了。

所以我们需要一个更好的，更稳定的模式。也就是 detached 模式。attached 模式更适用于容器和程序的调试阶段。

\[

### detached 模式

](#toc328)

`detached 模式`的开启方法，就是加一个参数`-d`或者`--detach`。

```jsx
docker run -d -p 80:80 nginx
```

这次你会看到，和`attached`模式不同的是，这次输入完命令后，只显示出了容器的编号，并且可以再输入任何命令。就算我们关掉窗口，容器依然运行，也就是他是在系统后台进行运行的。

这种就比较适合在生产环境中运行，停掉和删除容器都需要使用`Shell 脚本`的形式。减少了很多误操作。

\[

### detached 模式转换 attached 模式

](#toc329)

在运行之后，也有需要调试的时候，Docker 提供了两个模式间的转换。比如现在要把`detached`模式的容器，改为`attched`模式。

```jsx
docker  attach <ID or Image Name>
```

总结一下，本节课共学习了三个知识点，

1.  如何映射端口，让 Docker 可以被访问到；
2.  attached 模式和 detached 的使用和优缺点介绍；
3.  如用把 detached 模式转换为 attached 模式

下节课我们学习 detached 模式下的具体操作。

\[

## 07.\[容器] detached 模式下查看 logs

](#toc230)

这节算是对上节课的一个小补充，所以知识比较少，因为视频不是一次录制，所以就分开了。希望小伙伴们谅解。

\[

### detached 模式下查看日志

](#toc331)

先复习一下上节课的内容，用`detached`模式开启一个`nginx`服务，并映射服务器的`80 端口`。

```jsx
docker container run -d -p 80:80 nginx
```

容器被运行起来了，是`detached`模式，也就是 Docker 的后台运行模式。这时候想要查看后台日志，可以使用下面的命令查看。

```jsx
docker container logs <ID or Image name>
```

虽然日志在窗口中出现了，但只打印一次`logs`, 如果想动态一直跟踪日志，可以在命令上加入一个`-f`。

```jsx
docker container logs -f <ID or Image name>
```

输入完上面的命令，打开浏览器，在地址栏输入`127.0.0.1`，也就是访问本地的 nginx 服务。你会看到日志窗口就会跟踪到最新的日志。

如果想关闭日志跟踪模式，直接用快捷键`Ctrl+C`就可以结束掉了。

\[

## 08.\[容器] Docker 的交互式模式

](#toc232)

有时候容器的镜像不是简单的一个服务，而是需要交互的操作系统。例如创建一个 Ubuntu 系统，然后需要到系统里输入各种 Shell 命令和系统进行交互。这时候`attached 模式`和`detached 模式`就不能满足要求了。需要使用交互模式。

\[

### 使用 Ubuntu 镜像并开启交互模式

](#toc333)

```jsx
docker container run -it ubuntu sh
```

`-it`代表启用交互模式，`sh`代表可以使用 Shell 脚本。当你输入玩这个脚本后，Docker 就会进入到交互模式。可以使用`ls`来得到目录下的文件，也可以使用`hostname`来查看计算机名称。

这时候你想退出容器和交互模式可以输入`exit`命令。需要重点说明的是，随着命令退出后，容器也会跟着退出，变成`Exited`模式。

\[

### detached 模式下的交互

](#toc334)

如果我们想退出交互，但是并不想停止容器。可以先开启`detached 模式`，然后通过命令进入交互模式。我们来操作一下, 先删除所有的容器。

```jsx
docker container rm -f $(docker container ls -aq)
```

然后再用`detached 模式`创建一个`nginx 镜像`的容器。

```jsx
docker container run -d -p 80:80 nginx
```

直接通过下面的命令就可以进入到交互模式下了。(这是我们以后要经常使用的一个命令)

```jsx
docker exec -it <ID or Image name> sh 
```

`exec`是执行的意思，`-it`交互模式 ， `sh`交互的方式，用 shell 脚本进行交互

> 整个命令的意思是：用 shell 脚本的方式执行交互模式。

进入后可以使用`ls`来查看容器的文件系统。

这种模式的优点是，再使用`exit`退出后，服务并不会停止，而只是退出了交互模式。可以自己尝试一下退出，然后使用`docker container ls -a`来查看一下容器的状态，你会发现依然是 `up 状态`。

这个视频主要学习了 Docker 容器的交互式模式。

-   一种是创建并直接进入交互模式
-   另一种是先创建进入 detached 模式，然后再进入交互模式

两种模式用处不一样，根据自己需要，选择就好。

\[

## 09.\[镜像] 镜像获取和 Image Registry

](#toc235)

容器（Container）相关的基础知识先暂停一下学习，接下来把精力放在镜像（Image）上。镜像是 Docker 里最重要的一个知识点，如果你只会创建容器和使用官方的镜像，并不能算是 Docker 的高手或者是专业选手，只能说会使用 Docker。而制作镜像文件，并让广大网友使用，才是每个 Docker 人的追求。

\[

### 获取镜像的三个基本途径

](#toc336)

-   从网络社区直接拉取，在 Docker 里这种社区叫做`Registry`(登记处) 的意思。（pull from registry）
-   从 Dockerfile 构建一个镜像，这种像是 DIY 一个镜像，但是整个构建过程是需要联网，因为需要西在基础镜像，然后根据基础镜像进行构建（build from Dockerfile）。
-   自有文件的导入，可以从本地导入已经构建好的镜像文件，在没有网络的时候可以用。这个文件是通过 已有的镜像导出来的压缩包，然后就可以进行使用了。

总结：三种方法中最简单的是第一种，一条命令就可以完成。最复杂的是用 Dockerfile 进行构建，因为要写很多批处理命令`Shell`，但这正式 Docker 的魅力所在，也是我们必须要掌握的。

\[

### 镜像社区的介绍

](#toc337)

镜像社区也叫做 Image registry（镜像登记处），是拉取和下载镜像的网站，你也可以通过 Dockerfile 制作镜像，让所有人使用，类似 Docker Image 专属的简单版 GitHub。我经常使用的是两个社区，一个是官方自己的另一个是红帽旗下的 Quay.io。

![](https://newimg.jspang.com/Docker9-1dockeryhub.png)

-   dockerhub：网址 - [https://hub.docker.com/](https://hub.docker.com/) ,Docker 官方社区，在使用 Docker 时默认的拉取网站。
-   Quay：网址 -[https://quay.io/](https://quay.io/) ，这个是 Liunx Red Hat （红帽）的旗下一个第三方 Docker 社区。

![](https://newimg.jspang.com/Docker9-2quayio.png)

这两个网站算是最常用的镜像下载社区了，建议你现在停下视频，去把这两个网站都注册一下。注册很简单，我就不作过多的介绍了。注册好后，可以简单了解一下这两个网站。

需要说的`dockerhub`对于免费用户是有一些限制的，但是完全不影响学习使用。主要的简直是，现在个人用户或者没注册用户，每天只能拉取 100 次，最早是 6 小时 100 次。

其实就算每天 100 次，作为学习者也是够用了。但是最为一个使用容器技术的大型机房肯定是不够用的。

\[

## 10.\[镜像] Image 镜像的拉取和删除

](#toc238)

这节学习一下在 Registry 上拉取进行到本地、拉取后如何查看镜像列表、相信的镜像信息和删除镜像。

\[

### 从 dockerhub 上拉取镜像

](#toc339)

当在`PowerShell`里输入`docker image` 命令后，会出现对于 Image 操作的所有命令和提示（算帮助信息吧）。

```jsx
PS C:\Users\Administrator> docker image

Usage:  docker image COMMAND

Manage images

Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
  prune       Remove unused images
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rm          Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
Run 'docker image COMMAND --help' for more information on a command.
```

这些命令中可以看到`pull`的使用方法是用于拉取镜像。比如去拉取一个 wordpress 的镜像来试试。打开`hub.docker.com`，进入`explore`后，搜索`wordpress`. 点击进入主页，右侧会告诉你拉取的方法。

![](https://newimg.jspang.com/Docker10_1wordPress.png)

这条命令是`docker pull wordpress`, 细心的小伙伴一定可以发现，正常应该是`docker image pull wordpress`，不写`image`是老版本的写法，你也可以理解为简写，但我依然建议大家把命令写全，也就是带上`image`。

```jsx
docker image pull wordpress
```

如果是第一次拉取镜像是需要下载过程的，需要下载很多依赖的基础镜像。具体快慢会和网速有关。这里给出第一次拉取`wordpress`的日志信息。

```jsx
PS C:\Users\Administrator> docker image pull wordpress
Using default tag: latest
latest: Pulling from library/wordpress
33847f680f63: Already exists
ba03c99d34ed: Pull complete
5f637ed06e1a: Pull complete
ecfd84713df3: Pull complete
75835d9b84b3: Pull complete
8514983ec064: Pull complete
ec742b42e20a: Pull complete
eec0037df356: Pull complete
12533b9aae46: Pull complete
35321669eeaa: Pull complete
e1b13b2730b4: Pull complete
39fbc18466a3: Pull complete
d1db32813f92: Pull complete
469c3aba411c: Pull complete
5f4ce430d448: Pull complete
282de0644b41: Pull complete
5734bf68e8bd: Pull complete
6c4ac5841412: Pull complete
4e734c3119eb: Pull complete
531c1cccc50d: Pull complete
68155d3faebf: Pull complete
Digest: sha256:b590a25a358650cb91233ef9e058b2785a121f3a9e622d9dfc03a2749004013e
Status: Downloaded newer image for wordpress:latest
docker.io/library/wordpress:latest
```

上面命令的第二行`tag`的意思就是版本,`latest`代表的是最新版。因为这里并没有给版本号，你可以加入版本号进行下载的。到`dockerhub`上可以找到对应的版本号。比如我们要下载 wordpress7.3 版本，就可以输入下面的命令。

```jsx
docker pull wordpress:php7.3-fpm-alpine
```

\[

### 从 Quay.io 上拉取进行

](#toc340)

再演示一下如何从`Quay.io`上拉取镜像，打开 Quay 的网址`https://quay.io`。然后搜索`node`的相关镜像, 进入详细页，在右边也是可以看到相关的拉取`pull`命令的。

![](https://newimg.jspang.com/Docker10_2quayio.png)

输出的日志结果：

```jsx
PS C:\Users\Administrator> docker pull quay.io/calico/node
Using default tag: latest
latest: Pulling from calico/node
8127ea9172da: Pull complete
3d02a8db9907: Pull complete
Digest: sha256:0a02d75339eaca89fcca3a8f39b69afba2cff13964c6d3a6a470e508ab4b43e4
Status: Downloaded newer image for quay.io/calico/node:latest
quay.io/calico/node:latest
```

\[

### 查看现有镜像

](#toc341)

**查看镜像列表的方法**

```jsx
docker image ls
```

通过这条命令就可以查看 Docker 中有的镜像和相关信息。

**查看具体镜像信息**

```jsx
docker image  inspect <IMAGE ID>
```

这里的`inspect- [ɪnˈspekt]`是`检查`的意思。执行这条命令后就会显示很多关于这个镜像的详细信息。你现在可能还看不懂这些信息，但是会随着不断深入学习，对这些信息有更深刻的了解。

\[

### 删除镜像

](#toc342)

```jsx
docker image rm <Image ID>
```

需要注意的是，当有容器在使用镜像时，是没有办法被删除的。即使容器是停止掉的，依然是没办法删除的。

总结: 这节我们讲解了如何从 Registry 拉取镜像、查看镜像和删除镜像的方法。命令看起来挺简单，但是里边注意的事情还是挺多的，小伙伴们可以练习一下。

\[

## 11.\[镜像] Docker 镜像的导入导出

](#toc243)

这节学一下镜像的导入和导出，在工作中经常使用。比如公司来了一个新同事，也会 Docker，你正好自己制作了一个公司内部的镜像，就可以把你机器上的镜像导出给他。他拿到镜像之后直接导入，就可以进行开发了，好处是你们的开发环境基本统一了。

还有一种情况，就是生产环境中的服务器是不允许随便上网的，这时候你就需要在一台能上网的电脑上，做好镜像后，直接把镜像导出，供服务器使用。

\[

### 导出镜像

](#toc344)

```jsx
docker image save
```

在导出之前，你最好到一个好找的路径下面，比如我这里就选择了`D 盘`，使用`mkdir`命令创建一个文件夹，进入文件后输入下面的命令。比如现在要导出镜像中的`busybox`镜像，可以这样写命令。

```jsx
docker image save busybox:latest -o mybusybox.image
```

解读上面的命令，`save`是导出 / 保存的意思，`busybox:latest`是镜像名称 + 版本号， `-o`代表输出，`mybusybox.image`是导出后镜像的名字。

命令执行完成后，可以看到在执行命令所在的目录下就会多出一个`mybusybox.image`的文件，这就是刚才导出的镜像了。

\[

### 导入镜像

](#toc345)

先删除掉本机已有的`busybox`镜像。

```jsx
docker image rm busybox
```

删除后直接导入镜像。

```jsx
docker image load -i .\mybusybox.image
```

执行完命令之后，再使用`docker image ls`命令查看，`busybox`镜像已经回来了。

这节主要讲解了 Docker 镜像的导入和导出，这种操作是完全可以离线的。虽然个人使用的并不多，但是在工作中还是经常使用的。

\[

## 12.\[镜像] 初识 Dockerfile

](#toc246)

已经讲了两种获取 Docker 镜像的方式，第一种是直接从 Registry 中拉去，第二种是自己导入导出镜像。今天会学习第三种获得镜像的方法，通过`Dockerfile`来 DIY 制作镜像。

通过 Dockerfile 构建镜像虽然比较麻烦，这是最常使用的一种方式，必须掌握。它的知识点非常多，后期准备专门出一篇文章来讲解这个 Dockerfile 的使用、语法和注意问题。

\[

### 什么是 Dockerfile

](#toc347)

> Dockerfile 是一个包含用于组合映像的命令的文本文档。可以使用在命令行中调用任何命令。 Docker 通过读取 Dockerfile 中的指令自动生成映像。

可以简单总结为下面三点：

-   Dockerfile 是用于构建 docker 镜像的文件
-   Dockerfile 里包含了构建镜像所需的” 指令 “
-   Dockerfile 有其特定的语法规则（重要学习）

\[

### Demo - 执行 Python 程序

](#toc348)

有这样一个需求，制作一个镜像。镜像的操作系统是`Ubuntu`最新版，然后在系统上运行`jspang.py`程序。Python 程序的内容非常简单，只要打印出`Hello JSPang`，就可以了。

第一步，安装一个 Ubuntu 系统。

第二步，下载安装 Python 环境

```jsx
apt-get update && \
DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y python3.9 python3-pip python3.9-dev
```

第三步，准备`jspang.py`文件。这个可以在`D 盘`新建一个`DockerTest 文件夹`，然后在文件夹中新建一个`jspang.py`文件，然后编写下面的文件。

```jsx
print("Hello JSPang")
```

第四步，运行 jspang.py

```jsx
$ python3 hello.py
hello docker
```

这是我们拆解的步骤，有步骤之后，我们看看如何写一个 Dockerfile 文件（建议把 Dockerfile 文件和 jspang.py 文件放在一起个文件夹下）

```jsx
FROM ubuntu:latest
RUN  apt-get update && \
         DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y python3.9 python3-pip python3.9-dev
ADD jspang.py /
CMD ["python3","jspang.py"]
```

这算是最简单的一个 Dockerfile 文件的编写，有了这个文件之后，下节就可以动过 Dockerfile 来构建一个镜像了。这节你只要对镜像的构建有所了解就可以了。

\[

## 13.\[镜像] 通过 Dockerfile 构建镜像

](#toc249)

上节课算是对 Dockerfile 的一个初识，这节我们就通过上节课的 Dockerfile 文件进行 构建。

\[

### Dockerfile 构建镜像

](#toc350)

当有了`Dockerfile`和`jspang.py`文件以后，通过`PowerShell`进入到两个文件的文件夹。通过 Docker 命令就可以完成构建。

```jsx
docker image build -t <Name:tag> <file path>
```

例如现在要通过已经写好的 Dockerfile，构建一个`jspang`的镜像，就可以使用下面的命令构建。

```jsx
docker image build -t jspang .
```

（注意命令最后是有一个`.`的），如果你是第一次执行打包，这个过程还是需要 2-3 分钟的，当出现`FINISHED`后，说明打包完成了。

打包完成后，可以通过`docker image ls`命令来查看现在拥有的镜像列表。如果一切正常，你应该可以看到名字为`jspang`的镜像已经存在了。

可以执行容器，验证一下自己 DIY 的镜像是否可用。

```jsx
docker  run jspang
```

镜像如果正常，应该正确现实出`Hello JSPang`字样，然后就直接退出容器了。这是跟我们写的 Dockerfile 有关的。

我尽量把课程分的颗粒度细一点，这样你在工作中遇到问题，通过目录就可以快速定位到知识点，快速学会。

\[

## 14.\[镜像] 把镜像分享到 Dockerhub

](#toc251)

上节课通过`docker image build`镜像，已经构建了镜像。这节我们要把镜像`push`到 dockerhub 上去，这样就可以让所有人进行使用了。

\[

### 符合 Dockerhub 的命名规则

](#toc352)

这里我新申请了一个账号，账号名为`jspangcom`，所以在点开`Profile`时是没有任何镜像的。

![](https://newimg.jspang.com/Docker14_1.png)

如果你想上传属于自己的镜像，需要遵守社区规则，就是`用户 ID / 镜像名称`。可以最简单的方法，就是重新`build`一个镜像，镜像名称符合社区规则就可以了。

```jsx
docker image build -t jspangcom/jspang .
```

这时候就会生成一下新的镜像，但是 Image ID 是一摸一样的。

也可以通过`docker image tag`命令，具体语法如下：

```jsx
docker image tag <old image name > <new iamge name>
```

例如把`jspang`这个镜像，改为`jspangcom/jspang`镜像, 命令可以如下：

```jsx
docker image tag jspang jspangcom/jspang
```

\[

### 推送到 Dockerhub 上

](#toc353)

在推送前，需要先登录 Dockerhub 账号, 登录命令如下：

```jsx
docker login
```

执行命令好，会要求输入`Username`，也就你`Dockerhub ID`，还需要输入密码。如果输入正确，并出现`Login Succeeded`就证明登录成功了。

```jsx
docker image push Name[:TAG]
```

比如就是把刚才的`jspangcom/jspang`镜像 push 到社区，就可以使用下面的命令。

```jsx
docker image push jspangcom/jspang
```

输入完命令，就会给我们进行 push 到 Dockerhub 上了。这时候你可以到 Dockerhub 的 profile 页面，刷新一下，就可以看到刚刚 push 上去的镜像。

![](https://newimg.jspang.com/Docker14_2PushImage.png)

这样全世界的 Docker 爱好者都可以使用你自己 DIY 的镜像了。

\[

## 15.\[Dockerfile] FROM 语法和镜像选择

](#toc254)\[

### FROM 语法的使用

](#toc355)

看上节课视频，咱们一起写的 Dockerfile 文件.

```jsx
FROM ubuntu:latest
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y python3.9 python3-pip python3.9-dev
ADD jspang.py  /
CMD ["python3","/jspang.py"]
```

第一句就是`FROM ubuntu:latest` , 它的意思是选择一个基础镜像，我这里选择的是`ubuntu`系统的最新版。

几乎所有的 Dockerfile 文件，要做的第一件事就是要选择一个基础镜像。但可能出乎意料，上面的这句`FROM ubuntu:latest`并不是一个最优写法。

\[

### 选择基础镜像的三个原则

](#toc356)

为什么说`FROM ubuntu:latest`不是最优写法？先来看有选择镜像的三个基本原则。

1.  官方镜像优于非官方的镜像；
2.  固定版本的 Tag，而不是每次都使用 latest;
3.  功能满足，选择体积小的镜像；

**原则一、官方镜像优于非官方的镜像**

我们以 Dockerhub 社区为例，现在要找 wordpress 的镜像。搜索之后，可以看到第一个是官方认证的（Official Image）。三个基本原则的第一个，有官方认证的，直接选择官方认证的。

![](https://newimg.jspang.com/Docker15-1OfficialImage.png)

选择官方镜像至少可以保证没有木马和侵入程序。特别是你如果已经在公司上班，保证容器的安全非常重要。

**原则二、固定版本的 Tag，而不是每次都使用 latest**

进入到 wordpress 镜像详细页面，选择`Tags`选项卡，会看到很多版本的镜像。有`php8.0`, 也有`php7.4`的。你需要根据项目需求进行选择，而不是不负责任的每次都选择最新版本。

有些镜像的前后版本是不兼容的，这会给你的工作带来很多麻烦，比如镜像的维护性和稳定性都会存在问题。所以在写 Dockfile 第一步时，就需要我们做好这些事情。选择固定的版本，而不是每次都使用 latest。

![](https://newimg.jspang.com/Docker15-2dockerfiletag.png)

**原则三、功能满足的前提下，选择体积小的镜像**

这个原则不好把握，需要些经验。前提是满足你需求的情况下，所以这就要对镜像有充分的了解，然后再根据需求选择小的。

还是拿`wordpress`镜像为例，有些是带`alpine`环境的，有些是不带的。他们的镜像体积大小相差 一半。

> alpine （Alpine Linux）是一款独立的非商业性的通用 Linux 发行版、关注安全性、简单性和资源效率。它小巧的特点受广大 IT 人士的喜爱。

在工作中尽量选择自己需要的，如果你不需要 alpine 环境，你完全可以放弃 alpine 的环境版本，而是固定的 php 版本。

![](https://newimg.jspang.com/Docker15-3alpineTag.png)

注意这是基础镜像，在这个基础上，你还会加入很多自己的东西和应用。当你再次 build 时，镜像体积就会很大，越大的镜像，代表复杂度越高。所以让自己的镜像变的简洁，是我们的责任。

好了，这节课我们学习了 FROM 语法和选择镜像时的三个基本原则。虽然没有作任何的操作，但是这三个基本原则还是非常重要的。

\[

## 16.\[Dockerfile] RUN 执行指令使用技巧

](#toc257)

`RUN`是 Dockerfile 中一个重要的指令，它可以执行 Shell 指令，包括下载文件、安装软件、配置环境..... 都是可以的。这节课就是学习一下如何使用 RUN 指令，以及使用 RUN 指令时的一些小技巧。

\[

### 在 Ubuntu 系统下安装 ipinfo

](#toc358)

纯净的 Ubuntu 系统是没有 ipinfo 命令的，在安装完系统后，都会安装 ipinfo 命令。步骤如下：

```jsx
$ apt-get update
$ apt-get install wget
$ wget https://github.com/ipinfo/cli/releases/download/ipinfo-2.0.1/ipinfo_2.0.1_linux_amd64.tar.gz
$ tar zxf ipinfo_2.0.1_linux_amd64.tar.gz
$ mv ipinfo_2.0.1_linux_amd64 /usr/bin/ipinfo
$ rm -rf ipinfo_2.0.1_linux_amd64.tar.gz
```

上面这段代码需要你会一些 Linux 的基本操作，其实就是安装，解压和删除下载文件 的一个过程。

\[

### 不建议的 Dockerfile 写法

](#toc359)

如果用 RUN 命令来编写，直接可以写成下面的样子。

```jsx
FROM ubuntu:latest
RUN apt-get update
RUN apt-get install -y wget
RUN wget https://github.com/ipinfo/cli/releases/download/ipinfo-2.0.1/ipinfo_2.0.1_linux_amd64.tar.gz
RUN tar zxf ipinfo_2.0.1_linux_amd64.tar.gz
RUN mv ipinfo_2.0.1_linux_amd64 /usr/bin/ipinfo
RUN rm -rf ipinfo_2.0.1_linux_amd64.tar.gz
```

但这样写的问题是，镜像的分层会变的很多，每一个 RUN 都是一个分层，打出来的镜像包也会变大。

这是一般新手会犯的错误。

把上面的文件写到 Dockerfile 里，并个文件命名为`Dockerfile.bad`。执行下面的命令进行打包。

```jsx
docker image build -f Dockerfile.bad -t ipinfo-bad .
```

`-f`为指定打包的名称。 这个过程会很长。打包完成后，可以用查看命令，看一下包的基本信息。

```jsx
docker image ls
```

在列表里，看到`ininfo-bad`镜像的大小 134MB。再来看一下具体的分层情况，使用下面的命令查看。

```jsx
docker image history <Image ID>
```

查看结果如下：

```jsx
PS D:\TestDocker> docker image histroy e9c

Usage:  docker image COMMAND

Manage images

Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
e9c79d165e5c   4 minutes ago   RUN /bin/sh -c rm -rf ipinfo_2.0.1_linux_amd…   0B        buildkit.dockerfile.v0
<missing>      4 minutes ago   RUN /bin/sh -c mv ipinfo_2.0.1_linux_amd64 /…   9.36MB    buildkit.dockerfile.v0
<missing>      4 minutes ago   RUN /bin/sh -c tar zxf ipinfo_2.0.1_linux_am…   9.36MB    buildkit.dockerfile.v0
<missing>      4 minutes ago   RUN /bin/sh -c wget https://github.com/ipinf…   4.85MB    buildkit.dockerfile.v0
<missing>      6 minutes ago   RUN /bin/sh -c apt-get install -y wget # bui…   7.6MB     buildkit.dockerfile.v0
<missing>      6 minutes ago   RUN /bin/sh -c apt-get update # buildkit        29.7MB    buildkit.dockerfile.v0
<missing>      3 weeks ago     /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      3 weeks ago     /bin/sh -c #(nop) ADD file:5c3d9d2597e01d1ce…   72.8MB
```

\[

### 正确的 Dockerfile 写法

](#toc360)

把所有执行命令放到一个 RUN 里，并用`&& \`进行连接。就可以把很多命令写到一个 RUN 里边了。

```jsx
FROM ubuntu:latest
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://github.com/ipinfo/cli/releases/download/ipinfo-2.0.1/ipinfo_2.0.1_linux_amd64.tar.gz && \
    tar zxf ipinfo_2.0.1_linux_amd64.tar.gz && \
    mv ipinfo_2.0.1_linux_amd64 /usr/bin/ipinfo && \
    rm -rf ipinfo_2.0.1_linux_amd64.tar.gz
```

这样所有的 RUN 命令只生成一层`image layer`。打包出来的镜像也没有那么大了。我们把这个文件写到`Dockerfile.good`文件里，然后用命令进行打包。

```jsx
docker image build -f dockerfile.good -t ipinfo-good .
```

这时候再用`docker image histroy <Image ID>` 查看分层，就会看到分层少了很多。

```jsx
PS D:\TestDocker> docker image history e89
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
e893cd98aa4e   2 minutes ago   RUN /bin/sh -c apt-get update &&     apt-get…   46.7MB    buildkit.dockerfile.v0
<missing>      3 weeks ago     /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      3 weeks ago     /bin/sh -c #(nop) ADD file:5c3d9d2597e01d1ce…   72.8MB
```

两个包的体积也会有所变化, good 镜像是`119MB`,bad 镜像是`134MB`。

```jsx
PS D:\TestDocker> docker image ls
REPOSITORY            TAG       IMAGE ID       CREATED          SIZE
ipinfo-good           latest    e893cd98aa4e   3 minutes ago    119MB
ipinfo-bad            latest    e9c79d165e5c   14 minutes ago   134MB
```

总结：文章讲解了 Dockerfile 语法中 RUN 的用法和使用技巧。

\[

## 17.\[Dockerfile] Dockerfile 中的文件操作

](#toc261)

制作镜像的时候，经常需要向镜像里添加文件。在 Dockerfile 中有两个命令可以向镜像中添加文件`COPY`和`ADD`。这节我们就学习一下这两个命令，并重点了解一下两个命令的不同。

\[

### 用 COPY 命令构建镜像

](#toc362)

`COPY`和`ADD`命令，在复制普通文件的时候，并没有什么太大的不同，两个命令都可以把本地文件，复制到镜像里。（如果复制的路径不存在，则会自动创建）

现在我们写一个 Dockerfile，里边的内容是用基础 Node 镜像，然后拷贝一个`index.js`文件进去。

Dockerfile.copy 内容如下.

```jsx
FROM node:alpine3.14
COPY index.js  /app/index.js
```

引用 node3.13 版本，然后把`index.js`文件，拷贝到`app`目录下面。

index.js 文件如下。代码是我们在 3000 端口上，开启了一个最简单 web 服务，然后返回了`Hello Nodejs`两个单词。

```jsx
  
    const http = require('http');
    
    const server = http.createServer();
    
    server.listen(3000, () => {
        console.log('Server is running...');
    });
    
    server.on('request', (req, res) => {
        
        res.end('Hello Nodejs');
    });
```

两个文件准备好以后，用`build`命令进行构建。

```jsx
docker image build -f Dockerfile.copy -t hello-copy .
```

构建完成后，可以使用`docerk image ls`命令进行查询。生成成功后，可以启用交互模式，再加上映射端口的形式，运行容器。

```jsx
docker container run -it -p 3000:3000 hello-copy sh
```

这里映射了 3000 端口，这样我们就可以用`127.0.0.1:3000`进行访问了。

\[

### 用 ADD 构建镜像

](#toc363)

`ADD` 构建镜像和`COPY`最直观的一点不同，是 ADD 命令可以直接解压`gzip`压缩文件，这当我们有很多文件要上传操作的时候，就会变的简单很多。

Dockerfile.add 文件内容

```jsx
FROM node:alpine3.14
ADD index.tar  /app/
```

用`ADD`命令进行打包镜像

```jsx
docker image build -f Dockerfile.add -t hello-gzip .
```

打包好以后使用交互模式，开启容器。

```jsx
docker container run -it -p 3000:3000 hello-gzip sh
```

再进入`app`路径下面，可以看到下面自动给我们解压了`index.tar`文件。

\[

### 切换工作目录 WORKDIR

](#toc364)

在写 Dockerfile 文件时，默认的操作目录，是镜像的根目录。但有时候需要拷贝很多内容到镜像里是二级目录，就可以使用 WORKDIR 命令。把工作目录切换到二级，`WORKDIR`命令像我们操作 linux 下的`cd`命令。

比如还是刚才的`Dockerfile.add`文件，我们可以使用`WORKDIR`命令，改成下面的形式。

```jsx
FROM node:alpine3.14
WORKDIR /app
ADD index.tar  index.js
```

这时候进入系统后的工作目录，就是在`/app`下面了。

总结：这节主要讲了`COPY`和`ADD`命令的区别，也讲了 `WORKDIR`命令的用法。主要关注他们的用途，根据自己的需求进行使用。

\[

## 18.\[Dockerfile] Dockerfile 中的 ARG 和 ENV

](#toc265)

`ARG` 和`ENV` 是经常容易被混淆的两个 Dockerfile 语法，它们都可以用来设置一个 “变量”。但其实两个语法在细节上有很多不同，所以我们放在一节上，对比来讲。

如果你会一门编程语言，这两个语法和定义变量是一样的。这节课学起来也会容易很多。

\[

### ENV 定义变量

](#toc366)

在 16 节的时候，我们写了一个`Docerkfile.good`的文件，文件内容如下。

```jsx
FROM ubuntu:latest
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://github.com/ipinfo/cli/releases/download/ipinfo-2.0.1/ipinfo_2.0.1_linux_amd64.tar.gz && \
    tar zxf ipinfo_2.0.1_linux_amd64.tar.gz && \
    mv ipinfo_2.0.1_linux_amd64 /usr/bin/ipinfo && \
    rm -rf ipinfo_2.0.1_linux_amd64.tar.gz
```

这段文件里有 ipinfo 的版本是`ipinfo-2.0.1`, 这个版本是有可能改变的。文件里一共出现了 5 次`2.0.1`，修改起来已经比较麻烦了，如果出现更多次，几乎变的不可维护。所以这时候就需要定义一个变量，方便日后的维护。

先用`ENV`的形式来修改变量，把上面的 Dockerfile.good 文件修改为下面的形式

新建一个`Dockerfile.ENV`的文件，拷贝`Dockerfile.good`的代码。

这里有个小坑需要给大家说一下，就是注意在写变量时，值不要有任何的空格，否则在打包时会失败。

```jsx
FROM ubuntu:latest
ENV VERSION=2.0.1
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://github.com/ipinfo/cli/releases/download/ipinfo-${VERSION}/ipinfo_${VERSION}_linux_amd64.tar.gz && \
    tar zxf ipinfo_${VERSION}_linux_amd64.tar.gz && \
    mv ipinfo_${VERSION}_linux_amd64 /usr/bin/ipinfo && \
    rm -rf ipinfo_${VERSION}_linux_amd64.tar.gz
```

这样写之后，如果以后版本改变了，我们只要修改一处，就可以完成所有的修改了。

我们现在来构建一下这个 ENV 的镜像。

```jsx
docker image build -f Dockerfile.ENV -t ipinfo-env .
```

打包后，先把打包的镜像放在那里，再来看一下 ARG 的用法和打包。

\[

### ARG 定义变量

](#toc367)

跟上面的方法一样用 ARG 定义变量效果是一样。只是把`ENV`换成了`ARG`。

这个文件是`Dockerfile.ARG`，内容如下。

```jsx
FROM ubuntu:latest
ARG VERSION=2.0.1
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://github.com/ipinfo/cli/releases/download/ipinfo-${VERSION}/ipinfo_${VERSION}_linux_amd64.tar.gz && \
    tar zxf ipinfo_${VERSION}_linux_amd64.tar.gz && \
    mv ipinfo_${VERSION}_linux_amd64 /usr/bin/ipinfo && \
    rm -rf ipinfo_${VERSION}_linux_amd64.tar.gz
```

我们可以通过命令来构建一下 ARG 的镜像。

```jsx
docker image build -f Dockerfile.ARG -t ipinfo-arg .
```

两个打包完成后，用`docker image ls` 查看一下两个镜像，可以看到两个镜像的大小是一样的。都是`119M`。

那我们再来看看`ARG`和`ENV`有什么不同。

\[

### ARG 和 ENV 的不同点

](#toc368)

总的来说`ARG`和`ENV`有两点不同，第一点是声明变量的作用域不同，第二点是 ARG 声明后，可以在构建时修改变量。

**1.ARG 是构建环境 ， ENV 可带到镜像中**

用交互模式进入到`ipconfig-env`镜像中，然后输入`env`可以看到当前镜像的信息。

```jsx
docker container run -it ipinfo-env
```

然后输入`env`，可以看到里边是会有`VERSION`变量的。

**2.ARG 可以在构建镜像时改变变量值**

在构建时，可以使用`—build-arg` 参数来更改变量的值，比如现在要把变量 VERSION 的值进行修改, 就可以使用下面的命令。

```jsx
docker image build -f Dockerfile.ARG -t ipinfo-arg-2.0.0 --build-arg VERSION=2.0.0 .
```

这时候我们再使用交互模式，开启`ipinfo-arg-2.0.0`容器。

```jsx
docker container run -it ipinfo-arg-2.0.0 
```

然后再通过 shell 命令，`ipinfo verison`查看 ipinfo 的版本，可以看到版本已经变成了 2.0.0 了。

总结：`ARG`和`ENV`都用于声明变量，但是两者也是有区别的，我个人更喜欢 ARG 来声明，因为信息更多一点。

\[

## 19.\[Dockerfile] CMD 容器启动命令

](#toc269)

当设置好基础环境，安装完对应软件，处理完文件后。有时候需要启动某个默认命令。`CMD`用来设置容器启动时默认会执行的命令。

\[

### 批量清理容器和镜像

](#toc370)

在开始学习之前，我们先来学两个批量处理命令。随着我们学习，容器和镜像也越来越多。这时候需要一些批量操作命令。

批量删除不再使用的容器 , 注意这个是批量删除已经退出的容器（Exited state）。

```jsx
docker system prune -f
```

同样可以使用下面的命令，删除没有使用的所有镜像。

```jsx
docker image prune -a
```

这个命令输入之后，会提示确认，确认后才会真正删除。当我们把所有的容器和镜像都删除后，再继续向下学习。

\[

### CMD 命令的三个基本特性：

](#toc371)

`CMD`命令在使用时，有三个基本原则需要我们遵守。

-   容器启动时默认执行的命令
-   如果`docker container run`启动容器时指定了其它命令，则 CMD 命令会被忽略
-   如果定义多个 CMD，只有最后一个 CMD 执行

新建一个文件`Dockerfile.base`文件，拷贝上节课的`Dockerfile.ENV`文件到新文件中，进行构建镜像。

```jsx
FROM ubuntu:latest
ENV VERSION=2.0.1
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://github.com/ipinfo/cli/releases/download/ipinfo-${VERSION}/ipinfo_${VERSION}_linux_amd64.tar.gz && \
    tar zxf ipinfo_${VERSION}_linux_amd64.tar.gz && \
    mv ipinfo_${VERSION}_linux_amd64 /usr/bin/ipinfo && \
    rm -rf ipinfo_${VERSION}_linux_amd64.tar.gz
```

有了文件以后，我们再构建这个镜像。

```jsx
docker image build -f Dockerfile.base -t ipinfo-base .
```

构建完成以后，用交互模式启动镜像，

```jsx
docker container run -it ipinfo-base
```

启动后，就进入了 Shell 模式，这是因为 ubunt 进行里有定义 CMD 命令。它为我们作了这个事情。

通过查看分层信息，可以看到 ubuntu 镜像里已经使用了 CMD 命令。

```jsx
PS D:\DockerTest> docker image history ipinfo-base
IMAGE          CREATED        CREATED BY                                      SIZE      COMMENT
11217f4813e6   24 hours ago   RUN /bin/sh -c apt-get update &&     apt-get…   46.7MB    buildkit.dockerfile.v0
<missing>      24 hours ago   ENV VERSION=2.0.1                               0B        buildkit.dockerfile.v0
<missing>      2 weeks ago    /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      2 weeks ago    /bin/sh -c #(nop) ADD file:524e8d93ad65f08a0…   72.8MB
```

\[

### 启动容器时指定命令

](#toc372)

在用 shell 命令启动容器的时候，是可以指定相关的 CMD 命令的。比如我们在创建容器的时候，就启动`ipinfo`命令。

```jsx
docker container run -it ipinfo-base ipinfo version
```

输入完上面的命令，可以看到控制台打印出来了`2.0.1`, 就是 ipinfo 版本号。

\[

### CMD 的写法

](#toc373)

现在我们向 Dockerfile.base 文件里，加入一个 CMD 命令。

```jsx
FROM ubuntu:latest
ENV VERSION=2.0.1
RUN apt-get update && \
    apt-get install -y wget && \
    wget https://github.com/ipinfo/cli/releases/download/ipinfo-${VERSION}/ipinfo_${VERSION}_linux_amd64.tar.gz && \
    tar zxf ipinfo_${VERSION}_linux_amd64.tar.gz && \
    mv ipinfo_${VERSION}_linux_amd64 /usr/bin/ipinfo && \
    rm -rf ipinfo_${VERSION}_linux_amd64.tar.gz
CMD ["ipinfo","version"]
```

CMD 的写法。

```jsx
CMD ["ipinfo","version"]
```

先删除已经有的镜像，然后从新构建镜像。

```jsx
docker image build -f Dockerfile.base -t ipinfo-base .
```

然后开启交互模式，启动容器。

```jsx
docker container run -it ipinfo-base
```

总结：这节讲了 CMD 命令使用的三个基本原则，然后简单讲解了 CMD 命令的编写方法。

\[

## 20.\[Dockerfile] ENTRYPOINT 命令的使用

](#toc274)

`ENTRYPOINT` 命令很容易和 `CMD`命令混淆。`ENTRYPOINT`也可以设置容器启动时要执行的命令。使用起来的语法很简单，这节主要学习目的是理解`ENTYPOINT`和`CMD`命令的区别。

\[

### ENTRYPOINT 和 CMD 的区别

](#toc375)

-   `CMD`设置的命令，可以在 `docker container run` 时传入其它命令，覆盖掉 `CMD` 的命令，但是`ENTRYPOINT`所设置的命令时一定会被执行的。
-   `ENTRYPOINT` 和 `CMD` 可以联合使用， `ENTRYPOINT` 设置执行的命令，CMD 传递参数。

\[

### 三种镜像 Dockerfile 说明

](#toc376)

编写三个 Dockerfile 文件，`Dockerfile-cmd`、`Dockerfile-entrypoint`和`Dockerfile`.

Dockerfile-cmd 内容

```jsx
FROM ubuntu:21.04
CMD ["echo","hello docker"]
```

Dockerfile-entrypoint 内容

```jsx
FROM ubuntu:21.04
ENTRYPOINT ["echo","hello docker"]
```

`Dockerfile`内容

```jsx
FROM ubuntu:21.04
ENTRYPOINT [ "echo"]
CMD []
```

对三个`Dockerfile`文件分别打包，打包成了下面三个镜像包。

```jsx
demo-cmd          latest    25bb1dee8c29   2 weeks ago   80.3MB
demo-entrypoint   latest    214b876fc74c   2 weeks ago   80.3MB
demo-both         latest    6c64ebc22c19   2 weeks ago   80.3MB
```

\[

### 使用的区别和方法

](#toc377)

**demo-cmd 镜像的使用**

我们先来看第一个镜像的使用。

```jsx
$docker container run --rm -it demo-cmd
hello docker
```

容器开启后，会直接输出`hello docker`。这时候如果我们在`docker container run`里直接加入命令，就会覆盖掉现在显示出的`hello docker`。

```jsx
$docker container run --rm -it demo-cmd echo "hello world"
hello world
```

从输出结果可以看出，`hello docker`这个输出被覆盖掉了，只执行了`docker container run`中后输入的命令。

**demo-entrypoint 镜像的使用**

启用 demo-entrypoint 镜像的容器，会直接输出`hello docker`。说明`entrypoint`定义的命令也被执行了。

```jsx
$ docker container run 
hello docker
```

在`docker container run` 命令后面，加入一个`echo "jspang.com"`, 来看一下结果。

```jsx
$ docker container run --rm -t demo-entrypoint echo "jspang.com"
hello docker echo jspang.com
```

注意，这里在`hello docker`后面，打印出了`echo jspang.com`，而不是`jspan.com`。说明了它不是执行了两条命令，而是把`docker container run`后面的命令作为了参数，进行传递了过去。

**demo-both 镜像的使用**

当我们看到了`demo-entrypoint`镜像的使用后，再回头来看`Dockerfile`的内容，就能理解他的用途了。

```jsx
FROM ubuntu:21.04
ENTRYPOINT [ "echo"]
CMD []
```

意思是用`ENTRYPOINT`执行`echo`命令，但最终打印出的结果，`CMD`来作决定。实现了`ENTRYPOINT`和`CMD`的配合使用。

现在可以使用`docker container run`，传递参数，最终输出你想要的结果

```jsx
$ docker container run --rm -t demo-both "hello jspang"         
hello jspang
```

总结：这节课主要学习了`ENTRYPOINT`和`CMD`命令区别，还学习了两个命令的联合使用方法。

\[

## 21.\[数据持久化] VOLUME 让数据持久化 - 1

](#toc278)

容器删除掉后，里边的数据也会跟着删除。数据的保存和重复可用这是最基本的要求，也就是常说的数据持久化。在写 Dockerfile 的时候可以用`VOLUME`命令，指定数据持久化。这节课就一起学习一下。

\[

### 不能持久化的案例演示

](#toc379)

对比的学习效果最好，所以这里先操作一个不能持久化的案例。当我们了解问题后，再学习持久化就更容易理解和重视。先运行一个官方的 Ngix 的容器。

```jsx
docker container run -d nginx
```

`-d`是服务运行模式，这个在之前的课程中已经讲过了。

服务运行后，用下面的命令进入交互模式.

```jsx
docker container exec  -it <Container ID> sh
```

进入到交互模式后，为了体现数据持久化，安装一下 Vim 编辑器。安装 vim 编辑器的命令如下。。

```jsx
apt-get update
apt-get install vim
```

安装好 Vim 后，进入 app 目录。

```jsx
vim test.txt
```

在`test.txt`文件里，写入`Hello JSPang.com`，然后用`:wq`，进行保存。但是如果这时候删除了容器，我们写的文件就消失了。

照顾一下没什么经验的小伙伴，简单说一下 vim 编辑的使用。按`i+Enter`是进入插入模式，按`ESC`是退出当前模式，输入`:wq`是保存并退出。

\[

### VOLUME 命令实现持久化操作

](#toc380)

当知道了容器中的数据不能持久化后，可以在编写`Dockerfile`时用`VOLUME`命令设置持久化的目录。

**新建一个`Dockerfile`文件**

在`CentOS`下，新建一个`test`目录，然后在`test`目录下，新建一个`Dockerfile`文件，使用`vim`编辑文件，写入下面的命令。

```jsx
FROM NGINX
VOLUME ["/app"]
```

有了`Dockerfile`文件后，开始构建镜像，

```jsx
docker image build -t my-image .
```

构建好镜像，启动镜像容器。

```jsx
docker container run -d my-image
```

启动后查看容器 ID。

```jsx
docker container ls
```

进入交互模式

```jsx
docker container exec -it <ContainerID> sh
```

再安装 vim.

```jsx
apt-get update
apt-get install vim
```

这时候再新建一个`app`目录，然后编写`test.txt`文件。

```jsx
Hello JSPang.com
```

这时候，再删除镜像，就可以找到我们持久化的数据了。那这些持久化的数据被保存到了那里哪？这就需要我们再学习一下`docker volume`的相关命令了。

\[

### docker volume 相关命令

](#toc381)

现在退出容器，来到`CentOS`当中，可以输入下面的命令, 就可以看到`docker volume`相关的命令了。

```jsx
# docker volume

Usage:  docker volume COMMAND

Manage volumes

Commands:
  create      Create a volume
  inspect     Display detailed information on one or more volumes
  ls          List volumes
  prune       Remove all unused local volumes
  rm          Remove one or more volumes

Run 'docker volume COMMAND --help' for more information on a command.
```

可以用`docker volume ls` 查看所有的持久化空间，最主要的是可以看到`存储空间的 ID`。

有了 ID 之后，使用下面的命令，可以查看到持久化的具体地址。

```jsx
# docker volume ls
DRIVER    VOLUME NAME
local     c9fe0c3841af7d052034df6c1bc0b6092c75d9fb9a83d6d7a849ce465981a4d8
# docker volume inspect c9fe0c3841af7d052034df6c1bc0b6092c75d9fb9a83d6d7a849ce465981a4d8
[
    {
        "CreatedAt": "2021-08-16T10:07:52+08:00",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/c9fe0c3841af7d052034df6c1bc0b6092c75d9fb9a83d6d7a849ce465981a4d8/_data",
        "Name": "c9fe0c3841af7d052034df6c1bc0b6092c75d9fb9a83d6d7a849ce465981a4d8",
        "Options": null,
        "Scope": "local"
    }
]
```

其中的`Mountpoint`就是持久化的地址，复制这个地址，然后用`cd`命令进入。

```jsx
cd /var/lib/docker/volumes/c9fe0c3841af7d052034df6c1bc0b6092c75d9fb9a83d6d7a849ce465981a4d8/_data
```

然后输入`ls`，就可以看到在进行中我们编辑的`test,.txt`文件了。这时候再删除容器，这个文件也是存在的。

这节课先到这里，下节课继续学习 Volume，把持久化的数据，用到新的容器中。

\[

## 22.\[数据持久化] Volume 让数据持久化 - 2

](#toc282)

通过上节课的学习，你已经会把容器（container）中的数据和文件，保存在操作系统上了。现在的需求是，再创建一个容器，新容器如何用我们之前用 volume 保存下来的的持久化数据？

这节课就学习一下，如何在新容器中使用已经存在的持久化数据。

\[

### 给 volume 起名字, 实现复用

](#toc383)

想要复用持久化数据很简单，就是给 volume 起个名字。

在启动一个容器的时候，可以使用`-v`，给容器中的 volume 起一个名字。比如还使用我们之前自己创建的镜像`my-image`。

```jsx
docker container run -d -v <Volume name:Dockerfile VOLUME path>   my-image
```

例如启动容器的时候给 volume 起个名字叫`my-data`, 然后指定 Dockerfile 中的 VOLUME 命令路径。因为一个 Dockerfile 中可能有多个`VOLUME`命令，所以这里一定要准确指定路径。（注意是 Dockerfile 中 VOLUME 命令下的路径）。

```jsx
docker container run -d -v my-data:/app my-image
```

这时候再查看`volume`，这时候的`VOLUME NAME`就不是一大串类似 ID 的东西了，而是我们起的名字。

```jsx
# docker volume ls
DRIVER    VOLUME NAME
local     my-data
```

再通过下面的命令，查看一下持久化的详细地址。

```jsx
# docker volume inspect my-data
[
    {
        "CreatedAt": "2021-08-18T15:12:51+08:00",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/my-data/_data",
        "Name": "my-data",
        "Options": null,
        "Scope": "local"
    }
]
```

\[

### 进入容器，修改数据

](#toc384)

为了证明数据可以复用，现在我们进入容器，然后新建一个 test.txt 文件，写点内容。

进入容器的交互模式

```jsx
docker container exec -it <Docker ID> sh
```

再进入到`/app`目录下面，然后用`echo`向`test.txt`文件里写入内容。

```jsx
echo "Hello mybaby!" > test.txt
```

\[

### 删除容器后，重新开启容器

](#toc385)

现在强制删除刚才的容器。

```jsx
docker container rm -f <Container ID>

```

删除以后看一下 volume 是否还在，答案是肯定的，一定是在的。

```jsx
# docker volume ls
DRIVER    VOLUME NAME
local     my-data
```

现在我们用这个镜像，再启动一个容器。

```jsx
docker container exec -it <Container ID>  sh
```

然后再查看`test.txt`内容，可以看到内容已经回到了容器中，可以继续修改并使用了。

\[

## 23.\[数据持久化] Bind Mount 实现数据持久化

](#toc286)

数据持久化除了`Data Volume`外，还有一种叫做`Bind Mount`，从中文翻译来讲，就是`挂载绑定`。简单讲就是把容器中持久化的数据，绑定到本机的一个自定义位置。这节就学习一下这个知识。

\[

### 我喜欢用 Bind Mount 的两个理由

](#toc387)

个人很喜欢这种`Bind Mount`的形式，主要有两个原因。

1.  `Data Volume`在 WIndows 环境中很难使用，因为路径是虚拟机的路径，不容易找到。
2.  `Bind Mount` 设置更简单，可以和开发环境更好的融合。

所以如果你是一个开发者，建议你在开发时，更多的使用 Bind Mount 实现数据持久化。

\[

### Bind Mount 命令的使用

](#toc388)

使用`Bind Mount`进行数据持久化的方法，和`Data Volume`类似，也需要在启动容器的时候用到`-v`参数，只是参数的编写结构不同。

比如在 windos11 下进入`PowerShell`，运行一个 Node 的容器，然后把`/app`目录作为，把本机的当前目录作为绑定目录，意思是容器中的 app 目录和本机的当前目录绑定到了一起。命令如下：

```jsx
docker container run -it -v ${pwd}:/app node
```

上面命令具体的意思是，用`Bind Mount`的形式，开启一个 node 容器。然后进入交互模式。

其实这时候就实现了`Bind Mount`的数据持久化。而且你可以在本机新建和操作内容，然后在容器中运行。

\[

### 本机编写 index.js 插件

](#toc389)

比如在本机的绑定目录新建一个`index.js`文件，然后每秒钟显示一下时间。

```jsx
console.log('show Time')
setInterval(()=>{
    console.log(Date())
},1000)
```

写完这个文件后，到`PowerShell`里也是可以看到这个文件的。这样就算本机没有`Node`环境，可以在容器中进行使用。

进入容器的`/app` 目录，运行`node index.js`命令，就可以显示时间了。

总结：本节你需要学会`Bind Mount`的用法，主要是明白和`Data Volume`的区别，然后根据自己的喜好进行使用。

\[

## 24.\[网络] 容器的端口转发

](#toc290)

如果你在外网的 Linux 服务器上启动了一个 Wordpress 的容器，然后想通过本机访问，这时候就需要使用端口映射了。如果不进行端口映射，容器相当于一个私域 IP，外网是访问不到的，所以要使用端口转发的形式，才可以正常访问。

这节课我们学习的目标就是在腾讯的云主机上安装一下 Wordpress 容器，然后映射端口，最后在本地机器上可以访问。

\[

### Linux 主机安装 Wordpress

](#toc391)

现在我用 XShell 连接到了腾讯的云服务器（你可以理解为一台真实的云服务器，其实也是用的云容器技术）。在服务器上，我们先安装和启动容器，并映射 80 端口。

```jsx
docker container run -d -p 80:80 wordpress
```

安装的过程也非常简单，大概 1 分钟就可以启动好。注意这里的`-p 80:80` , 这里第一个`80`, 是你要映射的端口好，后边的`80`，是镜像提供的端口号。

等待完成后，直接在本地浏览器里查看，我的服务器网址是`http://110.40.130.171` ，这就就可以访问到 Docker 容器提供的 Wordpress 服务了。

\[

### 如何查看容器提供的端口

](#toc392)

上面的操作看似很简单，是因为我们直接知道了一个关键性因素，就是容器提供的端口`80`。如果不知道容器提供的端口就需要用下面的命令查看容器提供的端口。

```jsx
# docker container inspect --format '{{.Config.ExposedPorts}}' <ContainerID>
map
```

`--format` 是格式化过滤的意思，后边`{{...}}`里边的是要查看的选项。

如果镜像提供了这样的端口配置就可以查看到了。如果你不知道有什么具体项，可以使用下面的命令查看所有详细信息。

```jsx
# docker container inspect <Contaienr ID>
```

这里边有很多信息，如果你有时间，可以详细的一个个看一下。一定会对你的学习有所帮助的。

总结：这节我们主要详解了容器的端口转发的操作方法，顺便讲了讲如何查看容器的详细信息。

\[

## 25.\[docker-compose ]介绍和安装

](#toc293)\[

### 什么是 Docker-compose？

](#toc394)

熟悉 Linux 都知道，我们可以把很多相关的命令写成一个`xxx.sh`文件，而且这些步骤也是相对固定的。

这样直接运行 sh 文件，就可以逐一执行很多相关的 Docker 命令。这种形式可以减少出错和解决复用问题。Docker 很贴心的为我们准备了一个专门的工具`docker-compose`，实现类似`sh`文件的功能。让我们更加轻松的实现多 Docker 命令的操作。

你也可以把`docker-compose`就是把很多 Docker 命令写入一个专属的文件`docker-compose.yml`，然后执行这个文件，就可以直接启动我们想要的容器。`docker-compose`也为我们提供了对应的操作命令。

> -   docker-compose up

-   docker-compose stop

也就是说，操作 docker-compose 会有两个大的部分需要操作:

-   第一部分是`docker-compose.yam`文件
-   输入命令执行构建容器

\[

### docker-compose 的安装

](#toc395)

对 docker-compose 了解后，讲一下 docker-compose 如何安装。

**Windows & Mac 安装**

如果你是 Windows 或者 Mac 安装了 docker 桌面版本（desktop）以后，就默认安装了 docker-compose 工具了。可以直接进行使用。

查看安装的版本方法：打开`PowerShell`后输入下面的命令。

```jsx
# docker-compose --version
docker-compose version 1.29.2, build 5becea4c
```

从上面的信息可以看到，我当前的版本是`1.29.2`。出现这个信息也证明你安装好了。

**Linux 官方推荐方法安装**

Linux 系统默认是没有安装`docker-compose`工具的，可以进入下面的网址。

> [https://docs.docker.com/desktop/](https://docs.docker.com/desktop/)

进入亡之后，选择`Product Manuals` —>`Docker compose`—>`Liunx`后，可以看到三条命令，依次执行就可以安装`docker-compose`工具了。

第一条命令：

```jsx
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

如果一次安装不成功，可以多安装几次。一般是网络问题。

第二条命令：

```jsx
sudo chmod +x /usr/local/bin/docker-compose
```

第三条命令：

```jsx
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

安装好以后，用`docker-compose —version` 进行检查，如果能出现版本，说明安装成功了。

**Linux 用 pip 命令安装**

如果你对 Python 很熟悉，使用 pip 进行安装是明智的选择。它是 python 用于安装和维护 Python 包的。

如果 Linux 系统上没有 pip 工具，可以通过下面四个命令进行安装`pip`和`docker-conpose`（由于安装时间比较长，我就不演示了，可以自行安装测试）。以下方法适合 centos 系统。

1\. 查看是否安装依赖包

```jsx
sudo yum install epel-release
```

2\. 更新文件库 (如果不更改 yum 源此过程消耗时间很长)

```jsx
sudo yum -y update
```

3\. 安装 pip

```jsx
sudo yum -y install python-pip
```

4\. 安装 docker-compose

```jsx
sudo pip install -U docker-compose
```

这个教程就先提供这两种安装方式，你可以自行选择适合自己的安装方式。下节课我们来熟悉一下

compse 文件的结构和版本。

\[

## 26.\[docker-compose]文件的结构和版本

](#toc296)\[

### yaml 文件的基础结构讲解

](#toc397)

`yaml`文件里是对启动镜像相关设置的所有描述，下面就逐一讲解一下。

基本的 yaml 格式`docker-compose.yml`

```jsx
version: "3.8"

services: # 容器
  servicename: # 服务名字，这个名字也是内部 bridge网络可以使用的 DNS name
    image: # 镜像的名字
    command: # 可选，如果设置，则会覆盖默认镜像里的 CMD命令
    environment: # 可选，相当于 docker run里的 --env
    volumes: # 可选，相当于docker run里的 -v
    networks: # 可选，相当于 docker run里的 --network
    ports: # 可选，相当于 docker run里的 -p
  servicename2:

volumes: # 可选，相当于 docker volume create

networks: # 可选，相当于 docker network create
```

只是简单的看这些解释，你不可能学会 yml 文件的写法的，下面我们就以一个 wordpress 的镜像为例，制作 yaml 文件。

\[

### wordpress 的 yaml 文件写法

](#toc398)

用命令的写法：

```jsx
docker container run -d -p 80:80 wordpress
```

yaml 文件的写法：

```jsx
version: "3.8"

services:
  my-wordpress:
    image: wordpress:latest
    ports:
      - 80:80
```

\[

### docker-compose 版本说明

](#toc399)

> docker-compose 语法版本：[https://docs.docker.com/compose/compose-file/](https://docs.docker.com/compose/compose-file/)

打开这个网址，就会看到`compose`和`Docker`版本的兼容关系表。比如`3.8`版本，要求`Docker Engine`的版本是`19.03.0+`。

我们可以使用下面的命令查看当前电脑的版本。

```jsx

Docker version 20.10.7, build f0df350
```

可以看到，我们现在的 Docker 版本是完全符合`compose`的，所以在`yaml`文件的最开始写`version：”3.8“`是没有问题的。

这里需要说的是 :`Compose`现在有两个主要版本`Version3`和`Version2`。这两个版本的 yaml 写法也略有不同，但是基础语法是相同的。

\[

## 27.\[docker-compose]基础命令使用

](#toc2100)

有了`yaml`文件后，我们如何能启动一个容器，包括`docker compose`的一些基础命令需要我们学习一下。这节就讲解一下 docker compose 的基础命令学习。

\[

### docker compose 的 yaml 文件

](#toc3101)

上节课简单学习了`yaml`文件的简单编写，我们启动了一个 wordpress 的容器，并进行了端口的映射。`yaml`文件如下.

```jsx
version: "3.8"

services:
  my-wordpress:
    image: wordpress:latest
    ports:
      - 80:80
```

有这个文件后，可以打开`VSCode`，然后打开`VSCode`中的`终端`。就可以输入`docker compose`命令了。

\[

### 开启容器的命令

](#toc3102)

要学的第一个命令是用来开启容器的`docker compose up`, 当然`docker compose`有很多命令。

可以直接输入`docker compose`然后回车，就可以看到相关的一系列命令了。

```jsx
uild       Build or rebuild services  convert     Converts the compose file to platform's canonical format  cp          Copy files/folders between a service container and the local filesystem  create      Creates containers for a service.  down        Stop and remove containers, networks  events      Receive real time events from containers.  exec        Execute a command in a running container.  images      List images used by the created containers  kill        Force stop service containers.  logs        View output from containers
  ls          List running compose projects
  pause       pause services
  port        Print the public port for a port binding.
  ps          List containers
  pull        Pull service images
  push        Push service images
  restart     Restart containers
  rm          Removes stopped service containers
  run         Run a one-off command on a service.
  start       Start services
  stop        Stop services
  top         Display the running processes
  unpause     unpause services
  up          Create and start containers
```

在`终端`里输入下面的命令，就可以开启`wordpress`容器了。

```jsx
docker compose up
```

但这时候的容器开启方式是有日志输出的，并且窗口被占用了。没办法进行其它操作了。可以加入`-d`参数，解决这个问题。

```jsx
docker compose up -d
```

这样就是后台运行模式了，我们就可以继续操作这个终端了。如果你想查看`service`运行情况，可以使用下面的命令。

```jsx
# docker-compose ps
       Name                      Command               State                Ports
-----------------------------------------------------------------------------------------------
test_my-wordpress_1   docker-entrypoint.sh apach ...   Up      0.0.0.0:80->80/tcp,:::80->80/tcp
```

注意这里是`ps`，而不是`ls`。要和普通的 docker 命令进行一个区分。

\[

### Docker compose 的停止和清理

](#toc3103)

当你不在使用这个`service`的时候，就可以使用`stop`命令停止。

```jsx
docker compose stop
```

停止以后，容器就处于`Exited`模式了。容器已经停止，就可以进行清理了。

```jsx
docker compose rm
```

命令会删除掉由`docker compose`所建立的容器，但用 docker 命令创建的容器不会被删除，对应的网络也不会被删除。

\[

### 命名规则

](#toc3104)

用`docker compose`创建的容器，名字都会加入一个对应文件夹的名字，比如我在的文件夹叫做`test`, 而我在`yaml`文件中起的名字是`my-wordpress`。最终容器的名字就是`test_my-wordpress_1`

。

这个前缀其实是可以改的，比如我们希望前缀加上`jspang`。就可以使用`-p`参数。

```jsx
docker-compose -p jspang up -d
```

你也可以在`yaml`文件里指定这个名字, 方法是使用`contaner_name: xxx`但是这样作就会完全省略前缀和后缀。

```jsx
version: "3.8"

services:
  my-wordpress:
        container_name: jspang
    image: wordpress:latest
    ports:
      - 80:80
```

再重新启动，你会发现容器的前缀和默认的数字后坠都没有了。其实这样也不是很好，对以后的操作会造成一定的影响。我在工作中一般会先写好文件夹的名字，然后直接使用`docker compose`启动容器。

\[

## 28.\[docker-compose]镜像构建和拉取

](#toc2105)

上节我们学习了`docker compose`的创建、停止和删除。但上节课我们使用的`wordpress`镜像，是官方已经存在的镜像，所以可直接到`https://hub.docker.com`网站拉取就可以了。但是 如果镜像是我们自定义的`Dockerfile`，我们要如何设置那？

\[

### docker compose 自定义镜像构建

](#toc3106)

我们用 Dockerfile 拉去一个`node`的镜像，构建一个新的镜像。这里是学习，所以就不作其他的 Dockerfile 的复杂定义了，就用最简单的来进行模拟。

Dockerfile 文件

```jsx
FROM node:latest
CMD []
```

这时候我们的`docker-compose.yml`文件如下。

```jsx
version: "3.8"

services:
  my-node:
    image: my-node:latest

```

这里的`image: my-node:latest`，是我们自己构建的镜像，但是目前还没有。如果用`docker compose up` 构建会直接报错。我们运行一下，可以看到下面的错误。

```jsx
docker compose up
[+] Running 0/1
 - my-node Error                                                                                              4.6s
Error response from daemon: pull access denied for my-node, repository does not exist or may require 'docker login': denied: requested access to the resource is denied
```

意思就是这个`my-node`镜像在网上找不到，仓库里没有。

可以修改`docker-compose.yml`文件，让 docker 先构建镜像，然后再启动容器。

修改后的`docker-compose.yml`文件

```jsx
version: "3.8"

services:
  my-node:
    build: ./file
```

修改后，这时候再使用`docker compose up`命令，这时候就会先进行构建镜像，然后再开启容器。

\[

### 给自定义镜像命名

](#toc3107)

这时候就不会报错了，也可以正常启动容器了。但是还是有问题的，用下面的命令查看镜像的名字。

```jsx

REPOSITORY     TAG       IMAGE ID       CREATED      SIZE
test_my-node   latest    edf569856ed9   2 days ago   907MB
```

镜像的名字是`test_my-node`，这并不是我们想的叫做`my-node`。继续修改`docker-compose.yml`文件，增加`image`属性。

```jsx
version: "3.8"

services:
  my-node:
    build: ./file
    image: my-node:latest
```

在执行`docker compose up` 命令之前，可以执行下面的命令删除无用信息。

```jsx
docker system prune -f  # 删除没有使用的容器
dockers image prune  -a  # 删除不使用的镜像 
```

然后再次输入下面的命令，启动容器

```jsx
docker compose up
```

容器启动之后，你再使用`docker image ls` 会看到镜像的名字已经变成了设置的名字。

```jsx

REPOSITORY   TAG       IMAGE ID       CREATED      SIZE
my-node      latest    edf569856ed9   2 days ago   907MB
```

这样就实现了用`docker compose`自动逸镜像的名字。

\[

### 启动镜像前拉去镜像

](#toc3108)

上节课在`docker compose`中使用了`wordpress`的镜像。这个容器启动的时间是很长的，因为如果本地没有`wordpress`镜像，就要去官网上进行拉去，这个占用了 95% 以上的时间。这时候可以先使用下面的命令进行拉去镜像。

```jsx
docker compose pull
```

拉去 wordpress 镜像的时间比较长，这里就演示拉去 node 的了。修改`docker-compose.yml`文件。

```jsx
version: "3.8"

services:
  my-node:
    image: node:latest
```

再使用`docker image ls`查看镜像列表，可以看到镜像已经被拉去到本地了。

总结：这节主要学习了自定义镜像`Dockerfile`和`docker compose`的结合操作，包括镜像构建、命名和拉取操作。

\[

## 29:\[网络]Docker 的三种网络模式和 Bridge 网络模式讲解

](#toc2109)

这节课开始，学习一下 Docker 的网络模式。如果想要学好 Docker，对网络的操作是绕不过去的。只有网络学好了，才能更深入的学习。比如 Redis 集群的搭建、Swarm 的使用.....，都需要对网络模式有深刻的了解。

\[

### 多容器的网络默认设置

](#toc3110)

一台服务器上可以跑很多容器，容器间是相互配合运行的。有配合就需要有网络通讯，就需要设置网络。

比如现在我们启动一个`nginx`的容器，用`detached 模式`启动，并映射端口到`80`上。

```jsx
docekr container run -d -p 80:80 nginx
```

容器启动后，可以用查看容器的具体信息。命令如下。

```jsx
docker inspect <Container ID >
```

输入完成后，你可以看到有很多信息。其中有一项是`Networks`，这个就是容器的网路设置了。

```jsx
"Networks": {
    "bridge": {
       "IPAMConfig": null,
       "Links": null,
       "Aliases": null,
       "NetworkID": "bd2fe52b4c98ec5c5a11131a0bec714035ae25c791a518f7302d7f02c0aa8a75",
       "EndpointID": "2b8e1ff95d9f0f56be7a9f3737a1a695f523c290aefcd8c5f08130b9fb4535df",
       "Gateway": "172.17.0.1",
       "IPAddress": "172.17.0.2",
        "IPPrefixLen": 16,
       "IPv6Gateway": "",
       "GlobalIPv6Address": "",
       "GlobalIPv6PrefixLen": 0,
       "MacAddress": "02:42:ac:11:00:02",
       "DriverOpts": null
         }
    }
```

信息中是可以看出很多东西的，比如这个网络的连接方式是`bridge`，也就是桥接。然后 IP 地址`IPAddress`是`172.17.0.2`这个就是它的内网 IP 地址。

为了看的更清晰，我们可以再启动一个`nginx`容器.

```jsx
docker container run -d -p 8080:80 nginx
```

这时候再使用`docker inspect <Container ID>`可以看到网络信息是下面这样的。

```jsx
"Networks": {
    "bridge": {
        "IPAMConfig": null,
        "Links": null,
        "Aliases": null,
        "NetworkID": "bd2fe52b4c98ec5c5a11131a0bec714035ae25c791a518f7302d7f02c0aa8a75",
        "EndpointID": "4686cd198f9e6bbc22b25d1ce2b8e58dbadb60c6b20158a5afaf1bf2856bcdb3",
        "Gateway": "172.17.0.1",
        "IPAddress": "172.17.0.3",
        "IPPrefixLen": 16,
        "IPv6Gateway": "",
        "GlobalIPv6Address": "",
        "GlobalIPv6PrefixLen": 0,
        "MacAddress": "02:42:ac:11:00:03",
        "DriverOpts": null
    }
}
```

可以看到这个网络依然是桥接，IP 地址变成了`172.0.0.3`.

> 也就是说每一个容器启动后都会有一个 IP，并且每个 IP 是不同，自动变化的。这就是 Docker 为我们作的默认网络配置。并且虽然容器的启动顺畅，给的 IP 地址也是递增的。

这种默认的问题就是，如果每次启动的顺序不一样，IP 地址就会不同，这样每次都要重新进行配置。这肯定在工作中是行不通的。真实工作中，可能一台服务器就有几十个容器，如果每次修改通讯地址，这个工作将变的混乱不堪，无法继续。

那一般情况下，我们会通过`- -name`来置顶固定名称，然后再用名称进行通信。这种解决方案的前提就是需要了解网络模式和自定义网络后，才能实现可控状态。

\[

### 查看所有 Docker 的网络列表

](#toc3111)

可以使用下面的命令进行查看主机上已经有的网络配置列表.

```jsx
docker network ls
```

如果你的主机 刚装好 Docker，只有下面三种网络模式 名称：

-   bridge ： 这个是网桥，我习惯性的说成桥接模式。为每一个容器分配、设置 IP 等，并将容器连接到一个`docker0`虚拟网桥，默认为该模式。
-   host ：使用主机模式，容器没有 IP 和网关这些，都是用实体主机的。容器将不会虚拟出自己的网卡，配置自己的 IP 等，而是使用宿主机的 IP 和端口。
-   none ：就是不创建自己的 IP 网络。也就是常说的没有网，当然你可以自己进行定义网络模式。容器有独立的 Network namespace，但并没有对其继续任何网络设置，如分配 veth pair 和网桥连接，IP 等。
-   container : 就是利用其它容器的网络，别的容器有网络了，使用其它的容器网络。新创建的容器不会创建自己的网卡和配置自己的 IP，而是和一个指定的容器共享 IP、端口等。此种方式不是默认网络模式，它需要基于另一个容器。

这些网络模式都会在后面的课程中讲解，所以不要着急。这节课我们主要讲解第一种网络模式`Bridge 模式`.

\[

### bridge 网络模式

](#toc3112)

在该模式中，Docker 守护进程创建了一个虚拟以太网桥 `docker 0`, 新建的容器会自动桥接到这个接口，附加在其上的任何网卡之间都能自动转发数据包。

默认情况下，守护进程会创建一对 对等虚拟设备接口 `veth pair`, 将其中一个接口设置为容器的`eth0` 接口（也就是容器的网络 / 网卡接口），另一个接口放置在主机的命名空间中，以类似`vethxxx`这样的名字命名，从而将主机上的所有容器都连接到这个内部网络上。

![](https://newimg.jspang.com/docker_bridge.jpeg)

通过图可以清楚的看到桥接模式，`eth0`是主机网卡，`docker0`就是桥接网络，每个容器都有自己的`teh0`，然后通过`docker0`和主机进行通信，也形成了内部局域网。

\[

### 用 busybox 查看网络

](#toc3113)

为了更好的理解 Bridge 模式，我们启动一个`busybox`的镜像。 然后查看一下网络。

> busybox 被称为嵌入式 Linux 的瑞士军刀，整合了很多小的 unix 下的通用功能，并且只有一个很小的执行文件。

启动`busybox`的命令，这里使用了交互模式，并且给容器起了一个名字`bbox01`。

```jsx
docker run -it 
```

当这个容器启动后，新启动一个`CentOS`远程主机的会话，然后使用`shell`命令看一下现在主机网络会多出一个`vethxxxxx`的信息

```jsx
ip  addr
```

然后再到 busybox 中查看网络信息，可以看出他们形成了一组网络配置。

通过这个案例，你再回来看上面那段话，就会有深刻的了解。其实就是通过一对 `对等虚拟设备`实现网络通信，也就是桥接模式。

总结：这节课我们主要学习了 Docker 网络相关的知识，也讲述了 Docker 常见的四种网络模式 (bridge、host 、none、container)，最后通过`busybox`容器，详细演示了一下`bridge`模式。

\[

## 30.\[网络]host 和 none 网络模式讲解

](#toc2114)

这节课讲一下 host 模式和 none 模式。先来说 host 模式。

\[

### host 网络模式

](#toc3115)

> host 网络模式使用主机网络模式，容器没有 IP 和网关这些，都是用实体主机的。容器将不会虚拟出自己的网卡，配置自己的 IP 等，而是使用宿主机的 IP 和端口。

-   采用 host 网络模式的 Docker Container，可以直接使用主机的 IP 地址与外界进行通信，若主机的`eth0`是一个共有 IP，那么容器有用这个共有 IP。同时容器内服务的端口也可以使用端口，无需额外进行 NAT 转换。

启动一个 Nginx 容器，这个容器的特点是不再使用默认的`bridge`模式，而是使用`host`模式。使用 host 模式的关键字是`- - network host`或者`- - net host`都可以

```jsx
docker run -it 
```

启动后，可以打开浏览器，然后直接输入主机的 IP 地址，我的 IP 地址是`110.40.130.171`, 就可以看到`nginx`提供的默认页面了。这时候使用的是主机的网络设置，并没有映射`80 端口`。

再重新打开一个终端，利用`ip addr`查看网络情况。这时候是没有桥接网络的，进一步证明了我们使用的是 host 模式。

```jsx
[root@VM-0-12-centos ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 52:54:00:5d:20:c6 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.12/20 brd 172.17.15.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::5054:ff:fe5d:20c6/64 scope link 
       valid_lft forever preferred_lft forever
3: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:0b:ee:d6:93 brd ff:ff:ff:ff:ff:ff
    inet 172.18.0.1/16 brd 172.18.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:bff:feee:d693/64 scope link 
       valid_lft forever preferred_lft forever
```

看起来使用 host 模式挺好，但是由于 host 网络模式可以让容器共享主机网络，虽然可以直接通信，但是容器的网络同样缺少隔离性。

\[

### none 网络模式

](#toc3116)

> none 网络模式是指禁用网络功能，只有 lo 接口 local 的简写，代表`127.0.0.1`, 既 localhost 本地环回接口。在创建容器时通过 `- - net none`或者`--network none` 指定。

创建一个`busybox`的容器，使用`none`的网络模式

```jsx
docker run -it 
```

`bbox02`容器启动完成后，使用`ip addr`可以看到只有一个`lo`的网络。

```jsx
/ # ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    valid_lft forever preferred_lft forever
```

这里的`lo`就是`local`, 代表着只有本地地址，没有其他操作了。也就是没有网络状态，需要自己进行配置。

这时候有的小伙伴会问了。这种网络模式的用处是什么那？

> none 网络模式即不为 Docker Container 创建任何的网络环境，容器内部只能使用 loopback 网络设备，不会再有其他的网络资源。可以说 none 模式为 Docker Container 做了极少的网络设定，但是俗话说的好 “少即是多”。在没有网络配置的情况下，作为 Docker 开发者，才能在这基础做其他无限多的可能的网络定制开发。这也体现了 Docker 设计理念的开发。

好了，这节就到这里了，下节主要学习一下 Container 网络模式。

\[

## 31.\[网络]container 网络模式使用

](#toc2117)

这节我们主要学习一下 Container 网络模式的设置方法和使用场景。

\[

### container 网络模式

](#toc3118)

> Container 网络模式是 Docker 中一种较为特别的网络模式。在创建时通过参数`- - net container : 已运行的网络名称 | ID` 或者`- - network container : 已运行的容器名称 | ID` 指定。

处于这个模式下的 Docker 容器会共享一个网络栈，这样两个容器之间可以使用 localhost 高效通信。Container 网络模式即新创建的容器不会创建自己的网卡，配置自己的 IP，而是和一个指定的容器共享 IP、端口范围等。同样两个容器除了网络方面相同之外，其他的如文件系统、进程列表等还是隔离的。

为了更好的理解`container 网络模式`，我们创建 2 个`busybox`的容器。第一个使用默认的桥接模式`bridge`，第二个使用`container`模式。

先来开启第一个容器，使用`- -name`给容器命名为`bbox01`。

```jsx
docker run  - it 
```

第一个容器开启后，就会有一对 `对等虚拟网络`，也就是我们之前学到的桥接模式网络。可以新开一个窗口输入`ip addr`命令，查看这个虚拟网络。

第一个开启后，再用`- - network container:bbox01`开启第二个容器。

```jsx
docker run -it 
```

容器创建好以后，在容器的交互模式下，使用`ip addr`查看，你会发现和`bbox01`容器中的网络是一样的。以此证明了`bbox02`使用了`bbox01`的网络。

这时候使用`ping` 命令，查看一下百度的地址，是完全可以`ping`通的。

\[

### 主容器退出后，附容器无法联网

](#toc3119)

如果主容器退出以后，那么`附容器`将没办法联网, 这里的`附`的意思是依附于主容器。现在我们回到第一个`shell 窗口`，然后使用`exit`退出`bbox01`容器。再回到第二个`shell 窗口`，重新`ping www.baidu.com`，是没办法 ping 通的。

说明主容器退出后，附容器将没办法再继续使用。

再回到第一个`shell 窗口`，启动`bbox01`容器。

```jsx
docker container start bbox01
```

然后再回到第二个`shell 窗口`，网络依然不可以使用，这时候你要重新启动容器后，才能再次进行使用。

先用`exit`命令退出容器，然后使用下面的命令重启。

```jsx
docker container start bbox02
```

然后使用`exec`命令进入交互模式。

```jsx
docker exec -it bbox02 sh
```

这时候在 ping 我的博客`jspang.com`就可以 ping 通了。

相信通过讲解和练习，你已经对 docker 的 container 网络模式有了解啦。这种网络模式也经常使用。可以多练习一下。下节我们继续学习了。 
 [https://jspang.com/detailed?id=75#toc278](https://jspang.com/detailed?id=75#toc278)
