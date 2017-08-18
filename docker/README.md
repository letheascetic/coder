# docker
command line for docker

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

