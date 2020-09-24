# Docker

### describe the running docker

```
docker inspect {docker id}
```

### restart docker running containers always

```
docker update --restart unless-stopped $(docker ps -a -q)
```
