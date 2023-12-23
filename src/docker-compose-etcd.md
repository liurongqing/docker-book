# docker compose 配置 etcd

`docker-compose.yaml` 文件中
```yaml
etcd:
    container_name: etcd
    image: "bitnami/etcd:${ETCD_VERSION}"
    environment:
      - ETCD_ROOT_PASSWORD=${ETCD_ROOT_PASSWORD}
      - ETCD_ADVERTISE_CLIENT_URLS=${ETCD_ADVERTISE_CLIENT_URLS}
    ports:
      - 2379:2379
      - 2380:2380
    volumes:
      - ${DATA_DIR}/etcd:/bitnami/etcd
      - ${DATA_DIR}/etcd/etcd.conf.yml:/opt/bitnami/etcd/conf/etcd.conf.yml
```

`.env` 文件中
```yaml
#
# Runtime data directory
#
DATA_DIR=./data

#
# Etcd 管理
#
ETCD_VERSION=latest
ETCD_ADVERTISE_CLIENT_URLS=http://0.0.0.0:2379
ETCD_ROOT_PASSWORD=YrAuenXttHmcAo/ibRACBdT4NbPUwbKQEJ6A6oiUZMY=
```