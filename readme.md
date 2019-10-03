# Creating a PostgreSQL Cluster with Docker Swarm

This example only works on a Docker Swarm of version 1.12 or
greater. Please see link:https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm 
for details on setting up a test Docker Swarm cluster.

This *run.sh* script is run on the Swarm Manager node.


- docker swarm init

- docker swarm join --token SWMTKN-1-2tlc5e5giqf78blvh0gdg3apclemct4tly9hvm6m14726nwdxb-3wiezilvzghrvqekjwc9r0z1j 10.1.1.20:2377


- docker swarm join-token manager

- docker stack deploy --compose-file=./docker-compose.yml pg-stack

## To check if services are running, run the following commands:
- docker service ls
- docker service ps pg-stack_primary
- docker service ps pg-stack_replica

## To increase the number of replicas, run the following:
- docker service scale pg-stack_replica=2
- docker service ps pg-stack_replica

## Para verificar se as réplicas estão fluindo, consulte o PostgreSQL primário no host worker1 usando o seguinte comando:
- docker exec -it $(docker ps -q) psql -U postgres -x -c 'table pg_stat_replication' postgres

- docker-compose up

## Stop
- docker stop $(docker ps -a -q)
- sudo service docker stop

- docker-compose --version
- grep version docker-compose.yml

## docker composer

- sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
- hash -d docker-compose

