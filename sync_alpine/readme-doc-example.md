

## docker composer
- docker-compose up


- sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
- hash -d docker-compose

*****************************************************************************************************************************************************
version: "3"
services:
  db:
    image: "postgres:11"
    container_name: "my_postgres"
    ports:
      - "54320:5432"
    volumes:
      - my_dbdata:/var/lib/postgresql/data
volumes:
  my_dbdata:


docker logs -f my_postgres
$ docker exec -it my_postgres psql -U postgres

Create a database

$ docker exec -it my_postgres psql -U postgres -c "create database my_database"

*****************************************************************************************************************************************************

- apk add --no-cache \
      bash \
      vim

- https://github.com/lucenarenato/docker_postgres_sync/tree/master/sync_alpine

# Renato Lucena - 2019