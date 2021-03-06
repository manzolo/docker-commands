Comandi docker
=============

# Documentazione

### [Installazione](https://docs.docker.com/engine/installation/ubuntulinux/)

### [Bestpractices](https://docs.docker.com/engine/articles/dockerfile_best-practices)

### [Build images](https://docs.docker.com/engine/userguide/containers/dockerimages/)

### [Uso](https://docs.docker.com/engine/userguide/usingdocker/)

# Comandi
- Start docker
```
docker build -t manzolo/lamp .
docker run -d -p 8080:80 -p 3307:3306 manzolo/lamp
docker run -it manzolo/lamp /bin/bash
```

- Stop container_id
```
docker stop 223a0c9e805a
```

- Docker log conteiner
```
docker ps -a
```

- Container attivi
```
docker ps -l
```

- Remove unused images
```
docker rmi -f $(docker images | grep "<none>" | awk "{print \$3}")
```

- Stop/remove all
```
docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)
```
- Delete all images
```
docker rmi $(docker images -q)
```

- Clean all
```
docker rmi -f $(docker images | grep "<none>" | awk "{print \$3}")
docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)
docker rmi $(docker images -q)
```
