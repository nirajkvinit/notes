## Stop and remove all docker containers

`docker rm $(docker ps -aq)`

## Docker list all containers

`docker container ls`

## Docker List all container processes

`docker ps -a`

## Docker list all images

`docker images` or `docker image ls`

# Create a docker image

In order to create a docker image you need to create a Dockerfile inside the folder based which will contain the docker build configurations.
i.e.
ref. https://docs.docker.com/get-started/part2/#dockerfile

```
# Use an official Python runtime as a parent image
FROM python:2.7-slim

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
ADD . /app

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
```

## Building the docker image based off the above docker file

`docker build -t <imagename> .` e.g. `docker build -t friendlyhello .`

## To run the docker image

`docker run -p <host_port>:<guest_port> <image_name>` e.g. `docker run -p 4000:80 friendlyhello`
To run the image in the background i.e. detached mode add -d flag. e.g. `docker run -d -p 4000:80 friendlyhello`

## Docker Compose

sudo curl -L https://github.com/docker/compose/releases/download/1.21.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose

`sudo ifconfig vboxnet0 down && sudo ifconfig vboxnet0 up` is the easies fix at this point. https://github.com/docker/kitematic/issues/1193

## Run mongodb in docker

mkdir ~/data
docker pull mongo
sudo docker run -d -p 27017:27017 -v ~/data:/data/db --name mongodb mongo
docker exec -it mongodb bash

### Install the MongoDB client

sudo apt-get install mongodb-clients

### Change mydb to the name of your DB

mongo localhost/mydb

sudo docker ps
sudo docker stop mongodb

Alternatively, you can also execute `sudo docker stop \$(sudo docker ps -q)` as a shortcut to stop all running containers.
