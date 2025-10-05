default storge for images

      /var/lib/docker

images list in local 

      docker images

remove images without tag

      docker image prune

create new tag for image

      docker tag <IMAGE_ID> <repository>:<tag>

      
remove image

    docker rmi ubuntu:20.04

remove deactive images

    docker rmi prune 

pulling image

    docker pull ubuntu:20.04
    
push image to docker hub

      docker push yourname/image-name:lastest
      docker tag image-name yourname/image-name:lastest

save/load image to tar

      docker save image-name > name.tar

load image from tar

      docker load < image-name.tar


