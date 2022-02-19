#	一、Docker 常用命令

##	1.1 帮助启动类命令

1、启动 docker：systemctl start docker

2、停止 docker：systemctl stop docker

3、重启 docker：systemctl restart docker

4、查看 docker 状态：systemctl status docker

5、开机启动：systemctl enable docker

6、查看 docker 概要信息：docker  info

7、查看 docker 总体帮助文档：docker --help

8、查看 docker 命令帮助文档：docker 具体命令 --help





##	1.2 镜像命令

1、docker images：列出本地主机上的镜像

2、docker search 某个镜像的名字：查询镜像

3、docker pull 某个镜像的名字：下载某个镜像

​	1）docker pull 镜像名字:TAG

​	2）docker pull 镜像名字（下载的是最新版）

4、docker system df ：查看镜像/容器/数据卷所占的空间

5、docker rmi 某个 XXX 镜像名字的 ID：删除某个镜像





##	1.3 虚悬镜像

1、是什么

​	仓库名、标签都是 <none> 的镜像，俗称 虚悬镜像 dangling image

