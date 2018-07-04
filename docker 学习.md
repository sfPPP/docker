# docker
docker 三大核心概念：
 -image 镜像   
 -docker 容器  
 -repository 仓库

docker images  查看所有镜像

docker ps -a   查看所有容易

docker pull  仓库   从某仓库获取镜像   例： docker pull ubuntu 

  - 一般国外镜像下载比较慢，可以用国内仓库下载  例  docker pull daocloud.io/ubuntu 从daocloud 仓库下载

docker inspect image_id 查看镜像相关信息

docker run -it image_id /bin/bash   创建命令行交互式的docker,如果不加it docker 启动之后会自动停止

docker commit container_id  image_tag  生成新的镜像，保存修改,如果不保存，对docker的修改将无效

docker search 关键字  搜索镜像 例： docker search centos

docker rmi iamge_id 删除镜像

docker   rm container_id 删除容器

[docker创建镜像的三种方法](http://www.cnblogs.com/zhangmingcheng/p/5720792.html)
   - 基于已有的镜像创建的容器创建   ----保存对镜像的修改
   - 基于本地模板导入
      ```
            下载模板镜像
           134  wget http://download.openvz.org/template/precreated/ubuntu-14.04-x86_64-minimal.tar.gz
            将模板镜像转为docker镜像
           136  cat  ubuntu-14.04-x86_64-minimal.tar.gz|docker import - ubuntu:14.04
            查看docker镜像
           138  docker images
             启动docker 镜像
           139  docker run -it  0a90991f0ed9  /bin/bash
       ```

   - 基于dockerfile创建
   
   
   镜像的导入导出
    -导出 --将docker iamges 保存到本地   docekr save -o  文件名   image_id 
    -导入 --将本地的镜像导入到images      docker load --input 本地文件名 或者 docker load < 本地文件名 
    
    docker create 和 docker run区别：
       - docker create 创建的docker是stopped状态，需要docker start 才能启动docker
       - docker run 是创建并启动docker
       
