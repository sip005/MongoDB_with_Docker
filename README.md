# MongoDB_with_Docker

```bash
docker run -d -p 27017:27017 -v /path/on/host/docker_mongo/test:/data/db --name mongodb \
-e MONGO_INITDB_ROOT_USERNAME=polak -e MONGO_INITDB_ROOT_PASSWORD=1234 mongo:4.4

```
