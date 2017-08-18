# docker
command line for docker


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
    docker login             # Log in this CLI session using your Docker credentials
  

##### docker tag
    docker tag <image> username/repository:tag    # Tag <image> for upload to registry


##### docker push
    docker push username/repository:tag            # Upload tagged image to registry
