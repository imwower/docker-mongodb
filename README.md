# MongoDB Dockerfile in CentOS 7 image

This repository contains a Dockerfile to build a Docker Image for MongoDB in CentOS 7.

## Base Docker Image

* [zokeber/centos](https://registry.hub.docker.com/u/zokeber/centos/)

## Usage


### Installation

1. Install [Docker](https://www.docker.com/).

2. You can download automated build from public Docker Hub Registry:

```
docker pull zokeber/mongodb:latest
```

**Another way: build from Github**

To create the image zokeber/mongodb, clone this repository and execute the following command on the docker-mongodb folder:

`docker build -t zokeber/mongodb:latest .`

Another alternatively, you can build an image directly from Github:

`docker build -t="zokeber/mongodb:latest" github.com/zokeber/docker-mongodb`


### Create and running a container

**Create container:**

```
docker create -it -p 27017:27017 --name mongodb zokeber/mongodb
```

**Start container:**

```
docker start mongodb
```


### Connection methods:

**Mongo interactive shell:**

`docker exec -it mongodb mongo`

**Bash:**

`docker exec -it mongodb bash`


### Upgrading

Stop the currently running image:

```
docker stop mongodb
```


Update the docker image:

```
docker pull zokeber/mongodb:latest
```