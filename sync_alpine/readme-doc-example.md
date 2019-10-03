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
