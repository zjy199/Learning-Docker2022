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





##	1.4 容器命令A

1、新建 + 启动容器

​	1)	docker run [OPTIONS] IMAGES [COMMAND] [ARG...]

​	2)	OPTIONS 说明

			1.	--name：”容器新名字“ 		为容器指定一个名称
   			2.	-d：后台运行容器并返回容器 ID，也即启动守护式容器（后台运行）
   			3.	-i：以交互模式运行容器，通常与 -t 同时使用
   			4.	-t：为容器重新分配一个伪输入终端，通常与 -i 同时使用
   			5.	-P：随机端口映射，大写P
   			6.	-p：指定端口映射，小写p



2、列出当前所有正在运行的容器

​	1）docker ps[OPTIONS]





##	1.5 容器命令B





##	1.6 容器命令C

1、退出容器：

​	1）exit：容器停止

​	2）Ctrl + p + q：容器不停止

2、启动已停止运行的容器：docker start 容器ID或者容器名

3、重启容器：docker restart 容器ID或者容器名

4、停止容器：docker stop 容器ID或者容器名

5、强制停止容器：docker kill 容器ID或者容器名

6、删除已停止的容器：docker rm 容器ID





##	1.7 容器命令D

1、启动守护式容器

​	1）docker run -d 镜像名

​		1> 前台交互式启动：docker run -it redis:6.0.8

​		2> 后台守护式启动：docker run -d redis:6.0.8

2、查看容器日志：docker logs 容器ID

3、查看容器内运行的进程：docker top 容器ID

4、查看容器内部的细节：docker inspect 容器ID

5、进入正在运行的容器并以命令行交互

​	1）docker exec -it 容器ID bashShell

​	2）重新进入 docker attach 容器ID

​	3）区别

​		1> attach：直接进入容器启动命令的终端，不会启动新的进程，用 exit 退出，会导致容器的停止

​		2> exec：是在容器中打开新的终端，并且可以启动新的进程，用 exit 退出，不会导致容器的停止

6、导入和导出容器





##	1.8 容器命令E

1、从容器内拷贝文件到主机上

​	docker cp 容器ID：容器内路径 目的主机路径

2、导入和导出容器

​	1）export：导出容器的内容留作为一个 tar 归档文件[对应 import 命令]

​	2）import：从 tar 包中的内容创建一个新的文件系统再导入为镜像[对应 export]

​		案例：docker export 容器ID > 文件名.tar

​					cat 文件名.tar | docker import -镜像用户/镜像名:镜像版本号