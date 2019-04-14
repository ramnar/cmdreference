
#Start docker service

sudo service docker start

#search image in docker registry

docker search <image-name>:<tag-name>

#Find running containers

docker ps

#More details on the container

docker inspect <friendlyname | container-id>

docker logs <friendlyname | container-id>

#Run a docker image

sudo docker run -p <host-port:container-port> <image-name>

-d - to run in background
-v <path-in-container:/opt/docker/data/<name> - to bind docker volume with host directory path

#Certain images allow to run given command on starting the container

docker run ubuntu ps

#create docker image of an app using dockerfile

docker build -t <image-name .

#Docker registry operations

docker login

docker tag movieservice ramnar/movieservice:server

docker push ramnar/microservices:server

//connect to a container

docker exec -it <container-id> sh

//kill container
sudo docker ps
sudo docker kill <container_id>

//delete image
sudo docker rmi <image_id>

//container ip address
sudo docker inspect ca88d5224417 | grep "IPAddress"

//docker compose
docker-compose build
docker-compose up

//network commands
sudo docker network create --driver bridge mynet


References 

https://docs.docker.com/engine/reference/commandline/docker/#child-commands
