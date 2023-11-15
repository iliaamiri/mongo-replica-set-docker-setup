# MongoDB Replica Set - Docker Setup
I'm using Prisma and I want to use MongoDB. Prisma only connects to a MongoDB replica set and it took me quite a while to figure out how to setup locally. I don't want to use MongoDB Atlas cloud database anymore. I want to have my own local version.



## Setup 💩
Place the suitable info in `docker-compose.yml` file:
```yaml
MONGO_INITDB_ROOT_USERNAME: {{ root_username }}
MONGO_INITDB_ROOT_PASSWORD: {{ password }}
MONGO_INITDB_DATABASE: db
MONGO_REPLICA_HOST: {{ host }}
MONGO_REPLICA_PORT: "27017"
```
📝 Note: If you wish to connect to your container in a bridged network, make sure to give the IP given to you by your DHCP (router). 

Example: I wanted to connect to this contianer from a Virtual Machine which is connected to the same network as my host computer. I put my host computer's local IP Address given by my home router.

## Run that sh*t 💨
`docker compose up`

## Credits 💳
- `Dockerfile` was taken from: https://github.com/prisma/prisma/blob/main/docker/mongodb_replica/Dockerfile
- The article that saved my a$$: https://haneenmahdin.medium.com/set-up-mongodb-prisma-with-docker-c8c2f28e85de
