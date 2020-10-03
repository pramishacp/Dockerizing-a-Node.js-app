<h1 align="center">Welcome to Dockerizing Node.js Application 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="#" target="_blank">
    <img alt="License: ISC" src="https://img.shields.io/badge/License-ISC-yellow.svg" />
  </a>
</p>

> The goal of this example is to show you how to get a Node.js application into a Docker container. The guide is intended for development, and not for a production deployment. 

## Building your image - Build with PATH

```sh
# Go to the directory that has your Dockerfile and run the following command to build the Docker image. 
# The -t flag lets you tag your image so it's easier to find later using the docker images command:
$ docker build -t <tag name> .

```
## Check the image

```sh
# The docker images command lists all the Docker images you have in your computer's local Docker image registry. 
$ docker images

#The output from running the above command will look similar to this:
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
docker-node-app     latest              923659800e1e        28 seconds ago      921MB
node                12                  28faf336034d        2 weeks ago         918MB

```

## Run the image

```sh
# Running your image with -d runs the container in detached mode, leaving the container running in the background. 
# The -p flag redirects a public port to a private port inside the container

$ docker run -p 49160:1000 -d <image name or image id>

```
## Check containers

```sh
# Get container ID
$ docker ps

# Print app output
$ docker logs <container id>

# Example
Running on http://localhost:8080

If you need to go inside the container you can use the exec command:

# Enter the container
$ docker exec -it <container id> /bin/bash

```

## Test

```sh
To test your app, get the port of your app that Docker mapped:

$ docker ps

# Example
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                               NAMES
8f4f83bc22e1        docker-node-app     "docker-entrypoint.s…"   9 minutes ago       Up 9 minutes        8080/tcp, 0.0.0.0:49160->1000/tcp   naughty_dewdney

Now you can call your app using curl (install if needed via: sudo apt-get install curl):

$ curl -i localhost:49160

HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
ETag: W/"c-M6tWOb/Y57lesdjQuHeB1P/qTV0"
Date: Mon, 13 Nov 2017 20:53:59 GMT
Connection: keep-alive

Hello world

```

## Author

👤 **Pramisha C P**

* Website: www.pramishacp.com
* Github: [@pramishacp](https://github.com/pramishacp)
* LinkedIn: [@pramishacp](https://linkedin.com/in/pramishacp)
* Stack Overflow: [@pramisha-c-p] 

## Show your support

Give a ⭐️ if this project helped you!
