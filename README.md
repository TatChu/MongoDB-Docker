# Info MongoDB-Docker
Source build docker images to using MongoDB
Basic way
# Using:
- $ docker pull tatchu/bizzon
- $ docker run -p 27017:27017 tatchu/bizzon
- -- or Read more at https://hub.docker.com/r/tatchu/bizzon
- Usage: docker run --name <name for container> -d <user-name>/<repository> $ docker run -p 27017:27017 --name mongo_instance_001 -d my/repo
- Dockerized MongoDB, lean and mean!

- Usage: docker run --name <name for container> -d <user-name>/<repository> --noprealloc --smallfiles $ docker run -p 27017:27017 --name mongo_instance_001 -d my/repo --smallfiles
Checking out the logs of a MongoDB container

- Usage: docker logs <name for container> $ docker logs mongo_instance_001
Playing with MongoDB

- Usage: mongo --port <port you get from `docker ps`> $ mongo --port 27017
If using docker-machine

- Usage: mongo --port <port you get from `docker ps`> --host <ip address from `docker-machine ip VM_NAME`> $ mongo --port 27017 --host 192.168.59.103

- Tip: If you want to run two containers on the same engine, then you will need to map the exposed port to two different ports on the host

- Start two containers and map the ports

$ docker run -p 28001:27017 --name mongo_instance_001 -d my/repo

$ docker run -p 28002:27017 --name mongo_instance_002 -d my/repo

- Now you can connect to each MongoDB instance on the two ports

$ mongo --port 28001

$ mongo --port 28002

# Build:
- $ git clone https://github.com/TatChu/MongoDB-Docker.git
- CMD: 
  docker build - > -t <name>
- Power Shell
to be continue!
-----
# Lincese:
PUBLIC

# Author:
  The Boss (https://facebook.com/TatChu.IT)
  tatchu.it@gmail.com
# Reference:
https://docs.docker.com/engine/tutorials/dockerimages/
https://docs.docker.com/engine/examples/mongodb/


# My history command:
docker build - < Dockerfile -t tatchu/bizzon:v1
docker run -i -t -p 27017:27017 tatchu/bizzon:v1
docker commit -m "Upload image mongodb" -a "The Boss" d63e8147d158 tatchu/bizzon:v1
docker push tatchu/bizzon
