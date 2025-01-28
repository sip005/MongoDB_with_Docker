# MongoDB_with_Docker

```bash
docker run -d -p 27017:27017 -v /path/on/host/docker_mongo/test:/data/db --name mongodb \
-e MONGO_INITDB_ROOT_USERNAME=polak -e MONGO_INITDB_ROOT_PASSWORD=1234 mongo:4.4

```

We can store environment variables containing sensitive information such as usernames and passwords in your system and pass them into your Docker container using the `-e` flag in the `docker run` command.

Here's an example of setting environment variables in AlmaLinux or RHEL based OS and passing them into the Docker command:

### Storing Environment Variables in AlmaLinux
1. **Set Environment Variables:**
   Open your terminal and export the variables. For instance:
   ```bash
   export MONGO_INITDB_ROOT_USERNAME=polak
   export MONGO_INITDB_ROOT_PASSWORD=1234
   ```

2. **Verify Environment Variables:**
   You can verify if these environment variables are set correctly by using:
   ```bash
   echo $MONGO_INITDB_ROOT_USERNAME
   echo $MONGO_INITDB_ROOT_PASSWORD
   ```

### Running Docker Container with Environment Variables
Use the `docker run` command with the `-e` flag to pass these variables to the container:

```bash
docker run -d -p 27017:27017 -v /path/on/host/docker_mongo/test:/data/db --name mongodb \
-e MONGO_INITDB_ROOT_USERNAME=$MONGO_INITDB_ROOT_USERNAME \
-e MONGO_INITDB_ROOT_PASSWORD=$MONGO_INITDB_ROOT_PASSWORD \
mongo:4.4
```


todo app

```bash
docker run -d -p 27017:27017 -v ./database:/data/db --name mongodb \
-e MONGO_INITDB_ROOT_USERNAME=$MONGO_INITDB_ROOT_USERNAME \
-e MONGO_INITDB_ROOT_PASSWORD=$MONGO_INITDB_ROOT_PASSWORD \
-e MONGO_INITDB_DATABASE: todo \
mongo:4.4
```

```bash
docker run -d -p 27017:27017 -v ./database:/data/db --name database \
-e MONGO_INITDB_ROOT_USERNAME= polak \
-e MONGO_INITDB_ROOT_PASSWORD= 1234 \
-e MONGO_INITDB_DATABASE: todo \
mongo:4.4
```

```sh
# MongoDB URI for connecting to the database
MONGODB_URI=mongodb://polak:1234@database:27017/todo?authSource=admin

# Add any additional environment variables you need
DEBUG=true

```

In the above command:
- `-e MONGO_INITDB_ROOT_USERNAME=$MONGO_INITDB_ROOT_USERNAME` passes the AlmaLinux environment variable `MONGO_INITDB_ROOT_USERNAME` to the Docker container as `MONGO_INITDB_ROOT_USERNAME`.
- `-e MONGO_INITDB_ROOT_PASSWORD=$MONGO_INITDB_ROOT_PASSWORD` passes the AlmaLinux environment variable `MONGO_INITDB_ROOT_PASSWORD` to the Docker container as `MONGO_INITDB_ROOT_PASSWORD`.
