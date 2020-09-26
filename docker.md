# Docker

### describe the running docker

```
docker inspect {docker id}
```

### restart docker running containers always

```
docker update --restart unless-stopped $(docker ps -a -q)
```

### docker run postgres with postgis

```
docker run --name "postgis" -e POSTGRES_USER=postgres -e POSTGRES_PASS=root  -p 5432:5432 -d -t kartoza/postgis
```
