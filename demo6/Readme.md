# Demo 6

## Running multi-container application using docker-compose

> With latest version of docker, command 'docker-compose' could also be written as 'docker compose'

1. Validate the 'docker-compose.yaml' file

$ docker-compose config

2. Create and Run all containers

$ docker-compose up -d 
$ docker-compose ps
$ docker-compose down

3. Create and run all containers with "scale"

$ docker-compose up -d  --scale w1=2 --scale w2=3
$ docker-compose ps
$ docker-compose up -d  --scale w1=1 --scale w2=0
$ docker-compose down

## For MySQL Demo

1. To deploy custom YAML file

$ docker compose -f mysql-app.yaml up -d 
$ docker compose ps 

Use any web browser to visit http://localhost:8080, db credentials:
```ini
Server=db
Username=mahendra
Password=pass@1234
Database=sakila
```

