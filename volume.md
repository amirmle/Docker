
create a volume 

    docker volume create mydata

volume list

      docker volume ls

set to store /app/data in volume

      docker run -it -v mydata:/app/data myimage bash
- every thing in /app/data will be stored in selected volume even you delete the container 


volume path

      docker volume inspect mydata

default path 
  - /var/lib/docker/volumes/mydata/_data

bind mount 

      docker run -v /home/user/custom_data:/app/data myimage 
