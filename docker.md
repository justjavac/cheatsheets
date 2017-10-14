---
title: Docker CLI
category: Devops
layout: default-ad
---

管理镜像
-------------

从 Dockerfile 创建一个 `镜像`:

```yml
docker build [options] .
  -t "app/container_name"    # name
```

在`镜像`中运行一条命令:

```yml
docker run [options] IMAGE
  # see `docker create` for options
```

管理容器
-----------------

从一个`镜像`创建一个`容器`:

```yml
docker create [options] IMAGE
  -a, --attach               # attach stdout/err
  -i, --interactive          # attach stdin (interactive)
  -t, --tty                  # pseudo-tty
      --name NAME            # name your image
  -p, --publish 5000:5000    # port map
      --expose 5432          # expose a port to linked containers
  -P, --publish-all          # publish all ports
      --link container:alias # linking
  -v, --volume `pwd`:/app    # mount (absolute paths needed)
  -e, --env NAME=hello       # env vars
```

```
$ docker create --name app_redis_1 \
  --expose 6379 \
  redis:3.0.2
```

在一个`容器`中运行:

```yml
docker exec [options] CONTAINER COMMAND
  -d, --detach        # run in background
  -i, --interactive   # stdin
  -t, --tty           # interactive
```

```
$ docker exec app_web_1 tail logs/development.log
$ docker exec -t -i app_web_1 rails c
```

启动/停止一个`容器`:

```yml
docker start [options] CONTAINER
  -a, --attach        # attach stdout/err
  -i, --interactive   # attach stdin

docker stop [options] CONTAINER
```

管理`容器`:

```
$ docker ps
$ docker ps -a
$ docker kill $ID
```

管理中
--------

管理`镜像`:

```sh
$ docker images
  REPOSITORY   TAG        ID
  ubuntu       12.10      b750fe78269d
  me/myapp     latest     7b2431a8d968

$ docker images -a   # also show intermediate
```

删除`镜像`:

```yml
docker rmi b750fe78269d
```

资源
---------

 * http://www.docker.io/gettingstarted/
