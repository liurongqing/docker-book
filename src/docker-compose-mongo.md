# docker compose 配置 mongo

`docker-compose.yaml` 文件中
```yaml
mongo:
   image: mongo:${MONGODB_VERSION}
   container_name: mongo
   environment:
       MONGO_INITDB_ROOT_USERNAME: "${MONGODB_INITDB_ROOT_USERNAME}"
       MONGO_INITDB_ROOT_PASSWORD: "${MONGODB_INITDB_ROOT_PASSWORD}"
       TZ: "$TZ"
   volumes:
     - ${DATA_DIR}/mongo:/data/db:rw
     - ${DATA_DIR}/mongo_key:/mongo:rw
   ports:
      - "${MONGODB_HOST_PORT}:27017"
   networks:
      - default
   command:
      --auth
```

`.env` 文件中
```yaml
#
# MONGO
#
MONGODB_VERSION=latest
MONGODB_HOST_PORT=27017
MONGODB_INITDB_ROOT_USERNAME=root
MONGODB_INITDB_ROOT_PASSWORD=ePAB8sGRaKpK1UsQsSRWvO2FqzHSKSIx47CYvHszVRo
```