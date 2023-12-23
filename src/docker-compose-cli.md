# docker compose 常用命令

返回镜像
```bash
docker compose images
```

返回运行的容器
```bash
# -a 为所有容器
docker compose ps
```

启动所有任务
```bash
# -d 在后台执行
docker compose up -d
```

停止运行的容器并删除
```bash
# 加上 -rmi all  连镜像也一起删除
docker compose down
```

编译镜像
```bash
docker compose build
```

暂停容器
```bash
docker compose pause [container]
```

恢复容器
```bash
docker compose unpause [container]
```

启动暂停中的容器
```bash
docker compose start
```

暂停运行中的容器
```bash
docker compose stop
```

重启容器
```bash
docker compose restart
```

删除容器
```bash
# 只能删除暂停的容器
docker compose rm [container]
```

查看所有容器进程
```bash
docker compose top
```

## 进入 Terminal
```bash
# -i 是 terminal 交互的方式运行
# -t 是 tty 终端类型
# 容器 id，可以通过 docker ps 查看
docker compose exec -it [容器id/容器名称] /bin/bash
```

## 查看 Logs
```bash
# 容器 id，可以通过 docker ps 查看
docker compose logs [容器id/容器名称]
```

## 查看 Inspect
```bash
# 容器 id，可以通过 docker ps 查看
docker compose inspect [容器id/容器名称]
```

## 查看 Volumes
```bash
docker volume ls
```
