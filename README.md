### Build mongodb image
```
docker build -t docker_mongo .
```

### Run docker_mongo image
```
docker run --name mongo-dev -d -v /opt/mongodb:/data/db -p 27017 docker_mongo
```

### Add data to mongodb

#### Connect to docker_mongo
```
docker ps
mongo localhost:<local port for docker_mongo>
```
#### Add data to the container
```
use newdb
db.testData.insert({user:test, pwd:test})
db.testData.find()
quit()
```

### Restart docker_mongo
```
docker ps
docker restart <container_id>
```
