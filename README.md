# docker-tuts
My Experiments with docker and learnings


Docker Fundamentals
1. Docker is much efficient than traditional VM's due to
	1. Booting of container is much faster than VM due to installation of Guest OS
	2. Containers are lightweight as it GuestOS is not required. So number of containers that can be run on a given hardware is much more than VM's.
	3. Overhead in simulating underlying hardware is not required on docker.
	4. Storage cost is reduced due to docker images.
	
 
Installing Docker
1. https://store.docker.com/editions/community/docker-ce-desktop-mac?tab=description

Working With Images
1. Search docker images - https://hub.docker.com/
2. or command line - docker search "image name"
3. Pull Image - docker pull image:version
4. push image - docker push imagename

Starting Docker Containers
1. Start Container-  docker run -ti image:version /bin/bash
2. Come out of container- ctrl + p then ctrl +q
3. Go inside container- docker exec -ti containerId bash
4. List of Containers- docker ps -a
5. Stop Container - docker stop containerId


Persistent Storage for Docker
1. container is a read/write layer whose content is lost once container is stopped.
2. To persist the content of container, volumes are used. docker container path is mounted to host.
3. Volume creation while starting container - docker run -ti -v /data --name=duck2 ubuntu:latest /bin/bash
4. Above command will create a ubuntu container with data directory. the data inside this directory will be mounted.

Containers With Network Connection
1. Containers communicate to outside world by exposing port.
2. command to expose port - docker run -d -p 3306:3306 -ti mysql /bin/bash
3. Above command will start mysql docker container and exposes 3306 port.
4. To check the port mapping - docker ps 
5. To validate the port exposing - iptables -L -t nat





References:
1. https://www.youtube.com/watch?v=UV3cw4QLJLs
