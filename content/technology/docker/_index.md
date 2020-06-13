+++
title = "Docker"
date = 2020-04-26T17:49:23+02:00
weight = 1
+++

## Introduction

Environments are not the same. For example you develop on a Macbook and server is Ubuntu server. Docker runs on containers. Docker file builds a docker image, which contains all project code,installments of needed programs, complete application wrapped in an image, which is designed to sit on top of a container.

[Video Source](https://www.youtube.com/watch?v=Qw9zlE3t8Ko&t=623s)

[Solid written tutorial](https://tecadmin.net/tutorial/docker/docker-tutorials/)

## Tutorial

Create file called `Dockerfile` 

Take a look at `workspace/tutorial` project.

- `FROM` will take from the Python image for [DockerHub](https://hub.docker.com).
- `COPY` current directory
- `RUN` python specific stuff in requirements.txt
- `CMD` Commands to run, first the python command and then any python files

```dockerfile
FROM python:3-onbuild
COPY . /usr/src/app
RUN pip install -r requirements.txt
CMD ["python", "api.py"]
```

You can run services like:

```bash
docker run 
```

These usually has several arguments like port numbers, which can become tedious that is why it is better to use a `docker-compose.yml` file, like below. `docker-compose` is a yaml file and spins up all the containers we need.

```yml
version: '3'

services:
	# you name the services
    product-service:
    	# Directory where the dockerfile is
        build: ./product
        # sourcedirectory:/directoryonhost
        volumes:
            - ./product:/usr/src/app
        # localhostport:containerport
        ports:
            - 5001:80

    website:
    	# gets from dockerhub
        image: php:apache
        volumes:
            - ./website:/var/www/html
        ports:
            - 5000:80
        depends_on:
            - product-service

```


Run docker-compose file by running this command `docker-compose up`. You can stop the services with `CTRL + C`. The containers can be started up by using `docker-compose up -d` This will allow you to still navigate in the terminal and you can stop it by `docker-compose stop`.

## Commands

- `docker ps -a` : List containers with name, ID, etc
- `docker stop d31a3b925d89` :  Stop container with ID
- `docker system prune` : Remove stopped containers and dangling images
- `docker images` : List images with repository, image ID, etc
- `docker rmi e91727a11cd7` : Remove image with image ID
- `docker build -t webserver-image:v1 .` :  Build image with name: web server-image version: v1
- `docker run -d -p 5000:80 webserver-image:v1`  : Run image in container port 5000 locally and port 80 on container
- `docker-compose up` : Build image and run in container based on configuration in docker-compose.yaml file
- `docker-compose up --build` : To do a fresh build of images. Needed to update files.
- `docker-compose up -d` : Create containers and `-d` to launch in daemon mood (still navigate cmd)
- ` docker-compose stop ` : Stop all containers



## Deploy Static website as container

Medium article](https://medium.com/myriatek/using-docker-to-run-a-simple-nginx-server-75a48d74500b)

### dockerfile

```dockerfile
FROM nginx:alpine

RUN mkdir /www
COPY dist/index.html /www/index.html
COPY dist/css /www/css
COPY dist/js /www/js
COPY dist/img /www/img
COPY nginx.conf /etc/nginx/nginx.conf

```

The first line defines our base image. The second line copies the content of the current directory into a particular location inside the container.

### nginx.conf

```nginx
events {}

http {
    server {
        listen 80;

        root /www;
        index index.html;

        location / {
            include  /etc/nginx/mime.types;
            try_files $uri $uri/ /index.html;
        }
    }
}

```

### docker-compose.yaml

```yaml
version: '3.7'

services:
    web-service:
        build: ./
        ports:
            - 5000:80
      	volumes: ['./server/src:/app'] # To auto-reload new code from server/src to Docker app

```




