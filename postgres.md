    docker run -d \
        --name mypostgres \
        --network mynetwork \
        -e POSTGRES_USER=myuser \
        -e POSTGRES_PASSWORD=mypassword \
        -e POSTGRES_DB=mydb \
        postgres:latest
