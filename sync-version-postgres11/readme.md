## Docker postgres 10 - sync - replica


## docker composer
- docker-compose up


- sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
- hash -d docker-compose

docker logs -f my_postgres
$ docker exec -it my_postgres psql -U postgres

Create a database

$ docker exec -it my_postgres psql -U postgres -c "create database my_database"

- docker stack deploy --compose-file=./docker-compose.yml pg-stack

## Acesso ROOT
docker exec -u 0 -it container bash

## Stop
- docker stop $(docker ps -a -q)
- docker rm $(docker ps -a -q)

-     version: '3.5'
-     image: crunchydata/crunchy-postgres:centos7-11.1-2.3.0
-     image: crunchydata/crunchy-postgres:centos7-10.9-2.4.1
-     restart: always
- https://hub.docker.com/r/crunchydata/crunchy-postgres/
- https://github.com/lucenarenato/docker_postgres_sync/tree/master/sync

# Renato Lucena - 2019
