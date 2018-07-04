docker之间的通信（节点互联）是通过--link来实现的

例：我想让docker_n 连到docker_a上
  - 首先启动容器docker_a   docker  run -it ubuntu:16 --name docker_a  /bin/bash， --name 是给容器起别名
  - 然后启动容器docker_b并管理容器docker_a  docker run  --link docker_a  --name docker_b ubuntu:16 /bin/bash
