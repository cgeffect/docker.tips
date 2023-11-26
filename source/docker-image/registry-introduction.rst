Docker Image Registry
========================

拉取镜像
docker image pull nginx
指定版本
docker image pull nginx:1.20.0

查看镜像
docker image ls

查看镜像详细信息
docker image inspect imageid

删除镜像
docker image rm imageid

注意: 只要是被容器运行过的镜像, 一定是要先删除容器之后, 才能删除镜像, 即使是容器已经停止