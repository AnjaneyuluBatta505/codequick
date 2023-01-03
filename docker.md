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

### docker compose config

```yml
version: "3"

services:
  db:
    image: postgres
    volumes:
      - postgres_data:/var/lib/postgresql/data/
    environment:
      - POSTGRES_USER=admin
      - POSTGRES_PASSWORD=secret
      - POSTGRES_DB=mydb
    ports:
      - 5432:5432
  web:
    build:
      context: .
      dockerfile: Dockerfile.prod
    command: gunicorn app.wsgi:application --bind 0.0.0.0:8000
    volumes:
      - static_volume:/app/staticfiles
    expose:
      - 8000
    env_file:
      - ./.env.prod
    depends_on:
      - db
  nginx:
    build: ./nginx
    volumes:
      - static_volume:/app/staticfiles
    ports:
      - 80:80
    depends_on:
      - web
volumes:
  postgres_data:
  static_volume:
# Ref: https://github.com/testdrivenio/django-docker-s3/blob/master/docker-compose.yml
```

### docker access host from container

```bash
docker.for.mac.localhost # for mac
host.docker.internal # for linux
```
