# docker
docker 三大核心概念： image 镜像 /  docker 容器  / repo 仓库

docker images  查看所有镜像

docker ps -a   查看所有容易

docker pull  仓库   从某仓库获取镜像   例： docker pull ubuntu 

  - 一般国外镜像下载比较慢，可以用国内仓库下载  例  docker pull daocloud.io/ubuntu 从daocloud 仓库下载

docker inspect image_id 查看镜像相关信息

docker run -it image_id /bin/bash   创建命令行交互式的docker

docker commit container_id  image_tag  生成新的镜像，保存修改,如果不保存，对docker的修改将无效
docker search 关键字  搜索镜像 例： docker search centos
