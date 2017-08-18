# docker
concept & command line for docker

[documentation](https://docs.docker.com/get-started/)

### concept

##### container

##### image

##### service

##### swarm

    A swarm is a group of machines that are running Docker and joined into a cluster. After that has happened, you continue to run the Docker commands you’re used to, but now they are executed on a cluster by a swarm manager. The machines in a swarm can be physical or virtual. After joining a swarm, they are referred to as nodes.

##### node

    A swarm is made up of multiple nodes, which can be either physical or virtual machines. The basic concept is simple enough: run docker swarm init to enable swarm mode and make your current machine a swarm manager, then run docker swarm join on other machines to have them join the swarm as workers. 


### common command line

##### docker images
    docker images                           # Show images
    docker image ls                         # == docker images
    
##### docker stop
    docker stop <hash>                     # Gracefully stop the specified container


##### docker kill
    docker kill <hash>                     # Force shutdown of the specified container


##### docker rm
    docker rm <hash>                       # Remove the specified container from this machine
    docker rm $(docker ps -a -q)           # Remove all containers from this machine


##### docker rmi
    docker rmi <imagename>                     # Remove the specified image from this machine
    docker rmi $(docker images -q)             # Remove all images from this machine


###### docker ps
    docker ps                                 # See a list of all running containers
    docker ps -a                              # See a list of all containers, even the ones not running
  
  
##### docker build
    docker build -t friendlyname .            # Create image using this directory's Dockerfile


###### docker run
    docker run -p 4000:80 friendlyname        # Run "friendlyname" mapping port 4000 to 80
    docker run -d -p 4000:80 friendlyname     # Same thing, but in detached mode
    docker run username/repository:tag        # Run image from a registry
  
  
##### docker login
    docker login                              # Log in this CLI session using your Docker credentials
  

##### docker tag
    docker tag <image> username/repository:tag                  # Tag <image> for upload to registry
    docker tag friendlyhello letheascetic/get-started:part1


##### docker push
    docker push username/repository:tag            # Upload tagged image to registry


##### docker stack
    docker swarm init
    docker stack deploy -c docker-compose.yml getstartedlab
    docker stack ps getstartedlab
    docker stack rm getstartedlab
    
    docker stack ls                                     # List all running applications on this Docker host
    docker stack deploy -c <composefile> <appname>      # Run the specified Compose file
    docker stack services <appname>                     # List the services associated with an app
    docker stack ps <appname>                           # List the running containers associated with an app
    docker stack rm <appname>                           # Tear down an application

