# Docker Getting Started


## Run postgres data base

```sh
docker run -d --name demo-postgres \
 -p 5400:5432 \
 -e POSTGRES_USER=user \
 -e PGUSER=user \
 -e POSTGRES_PASSWORD=pw \
 postgres:latest
```

## Connect to postgres for cli inside container terminal

```sh
PGPASSWORD=pw psql -U user -h 127.0.0.1.local -p 5400 user
```

## To see the container id
```sh
docker inspect -f   '{{.Id}}' <container-name>
```

## Copy files to docker container from host

```sh
docker cp <file_name> <container_id>:/<folder_name>/
```

## Create tables from sql in container

```sh
cat <sql_filename> | PGPASSWORD=pw psql -U user -h <machine>.local -p 5400 user
```