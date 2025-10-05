# 📚 Important Docker Topics

## 1️⃣ Basics & Concepts

- What Docker is and why it’s lighter than virtual machines

- Image vs Container (differences, layers, immutability)

- Container filesystem and key Dockerfile instructions: COPY, WORKDIR, CMD, RUN

- Networking basics and container communication

- Volumes and Bind Mounts

- Difference between Container vs Host OS vs Kernel

## 2️⃣ Working with Images

- Writing a Dockerfile and syntax rules

- Key instructions: FROM, RUN, COPY, WORKDIR, CMD

- Image tagging and version management

- Commands: docker build, docker images, docker rmi

- Using cache and layers effectively

Pulling and pushing images from Docker Hub

## 3️⃣ Working with Containers

- Running containers: docker run, -it, -d, --name

- Managing containers: docker ps, docker stop, docker start, docker restart, docker exec

- Accessing container terminal: docker exec -it

- Viewing logs: docker logs, docker attach

- Commit and export/import containers

## 4️⃣ Networking

- Network types: bridge, host, none, overlay

- Connecting containers to networks: --network, docker network connect/disconnect

- Inspecting networks: docker network ls, docker network inspect

- Port mapping and host connectivity

- Internal Docker DNS and using container hostnames

## 5️⃣ Storage

- Volumes: create, attach, manage (docker volume create/inspect/rm)

- Bind mounts: map host folders into containers

- Data persistence and security considerations

- Differences between volume and bind mount

## 6️⃣ Docker Compose (multi-container)

- Defining docker-compose.yml

- Services, networks, volumes

- depends_on and startup order

- Commands: docker compose up/down/run/exec/logs

- Persisting data and network between services

- Using environment variables and secrets

## 7️⃣ Advanced Commands & Tips

- Multi-stage builds in Dockerfile

- ARG and ENV for parameterized images

- Health checks for services

- Inspecting container details: docker inspect

- System cleanup: docker system prune

## 8️⃣ Security & Optimization

- Running containers as non-root users

- Limiting resources: CPU, Memory

- Image size optimization

- Minimizing layers

- Scanning images for vulnerabilities

## 9️⃣ Integration & CI/CD

- Using Docker in real projects

- Pushing/pulling images to Docker Hub or private registry

- Docker in GitHub Actions or GitLab CI

- Multi-container application workflows
