---
id: mongo
title: Mongo DB
sidebar_label: Mongo
---

### Example docker-compose file



```yaml
# docker-compose.yaml
version: '3.1'

services:
  mongo:
    image: mongo
    restart: always
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: example
    volumes:
     - ./mongo-volume:/data/db
    ports:
      - 27017:27017

  mongo-express:
    image: mongo-express
    restart: always
    ports:
      - 8081:8081
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: example
```
- mounted at `mongo-volume` in host system
- Use root/example as user/password credentials

run following to bring mongo db and mongo-express client

```bash
docker-compose up -d
```
