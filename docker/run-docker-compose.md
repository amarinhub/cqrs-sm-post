# Install docker network
	docker network create --attachable -d bridge mydockernetwork 

## Inspect docker network
	docker network inspect 

# Run docker compose command
	docker-compose up -d

# View docker containers	
	docker ps
	
# Run MongoDb inside docker
docker run -it -d --name mongo-container -p 27017:27017 --network mydockernetwork --restart always -v mongodb_data_container:/data/db mongo:latest

# How to Do a Clean Restart of a Docker Instance
If you are using Docker-Machine, make sure your are talking to the right one. Execute the command docker-machine ls to find which one is currently active. It is also recommended to always redo the command:
eval "$(docker-machine env <docker machine name>)"
Note: Deleting volumes will wipe out their data. Back up any data that you need before deleting a container.

## Procedure
- Stop the container(s) using the following command:
	docker-compose down
- Restart the containers using the following command:
	docker-compose up -d
- Delete all containers using the following command:
	docker rm -f $(docker ps -a -q)
- Delete all volumes using the following command:
	docker volume rm $(docker volume ls -q)
- Delete all images list
  docker rmi $(docker images -a -q)
	
# Utils Kafka

- To create topics
docker exec -it kafka /opt/bitnami/kafka/bin/kafka-topics.sh \
    --create \
    --zookeeper zookeeper:2181 \
    --replication-factor 1 \
    --partitions 1 \
    --topic test

- To view messages pushed to a topic
docker exec -it kafka /opt/bitnami/kafka/bin/kafka-console-consumer.sh \
  --bootstrap-server localhost:9092 \
  --from-beginning \
  --topic test

- To push messages on a topic
docker exec -it kafka /opt/bitnami/kafka/bin/kafka-console-producer.sh \
    --broker-list localhost:9092 \
    --topic test
