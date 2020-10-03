<h1 align="center">Welcome to Dockerizing Node.js Application 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="#" target="_blank">
    <img alt="License: ISC" src="https://img.shields.io/badge/License-ISC-yellow.svg" />
  </a>
</p>

> The goal of this example is to show you how to get a Node.js application into a Docker container. The guide is intended for development, and not for a production deployment. 

## Building your image

```sh
Go to the directory that has your Dockerfile and run the following command to build the Docker image. The -t flag lets you tag your image so it's easier to find later using the docker images command:

docker build -t <your username>/node-app .

```
## Run the image

```sh
Running your image with -d runs the container in detached mode, leaving the container running in the background. The -p flag redirects a public port to a private port inside the container. Run the image you previously built:

docker run -p 49160:1000 -d <your username>/node-web-app

```
## Test

```sh
To test your app, get the port of your app that Docker mapped:
docker run -p 49160:1000 -d <your username>/node-web-app

docker ps

```

## Run tests

```sh
npm run test
```

## Author

👤 **Pramisha C P**

* Website: www.pramishacp.com
* Github: [@pramishacp](https://github.com/pramishacp)
* LinkedIn: [@pramishacp](https://linkedin.com/in/pramishacp)
* Stack Overflow: @pramisha-c-p

## Show your support

Give a ⭐️ if this project helped you!
