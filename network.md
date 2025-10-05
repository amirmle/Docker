# NETWORK

- network : virtual env that containers can connect with each other
- bridge : default nerwork in a machine
- host : network on localhost
- None : a network without any connections (isolated container)
- overlay : for connections between containers on diffrent hosts

## commands

list of all networks

    docker network ls
details of a network

    docker network inspect <network>
create network - default : bridge 

    docker network create <name>
create manual network 

    docker network create --driver bridge <name>
Building a network between multiple nodes (in a swarm)

    docker network create --driver overlay <name>
remove a network

    docker network rm <name>
Delete all unused networks

    docker network prune

### container

run a container in a network

    docker run --network <network_name> <image>
add an existing container to a network 

    docker network connect <network_name> <container_name>
remove a container from a network

    docker network disconnect <network_name> <container_name>
