# Introduction
  This compose file will install the zookeeper and start the zookeeper

# start the zookeeper cluster Foreground mode
docker-compose -f docker-compose.yml up

# start the zookeeper clusterBackground mode
docker-compose -f docker-compose.yml up -d

# stop the services
docker-compose down

# connect the zookeeper client/ go inside the docker container
docker exec -it zookeeper /bin/sh
    cd /bin and start the client
