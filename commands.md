      docker version
      docker run hello-world


  
list of avalable images in local

    docker images
    

pulling image

    docker pull ubuntu:20.04

Run image

    docker run image-name

    docker run --name container-name image-name 

- run container then echo run!


      docker run ubuntu:20.04 echo "run!"
    
run intractive image and open bash

    docker run -it ubuntu:20.04 bash
      -i : having open STDIN - being intractive
      -t : open a terminal 
      -p 8000:8000 : connect container port to pc port
      -d : run in background

create infinit loop that makes container never stop

    docker run -dit --name myubuntu ubuntu tail -f /dev/null
    
    tail -f /dev/null : infinit loop that makes container never stop

running container 
    
    docker ps
all container even stopped one

    docker ps -a 
  
enter container

    docker exec -it container-name bash 
  
start stopped container

    docker start -i [container id]
    
stop a container

    docker stop [container id]
    
remove container

    docker rm [container id]
       
prune diactive containers

    docker container prune 
      
remove image

    docker rmi ubuntu:20.04

remove deactive images

    docker rmi prune 
      

logs

    docker logs [id] 



