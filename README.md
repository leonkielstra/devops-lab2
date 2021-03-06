# Swagger generated server

## Overview
This server was generated by the [swagger-codegen](https://github.com/swagger-api/swagger-codegen) project. By using the
[OpenAPI-Spec](https://github.com/swagger-api/swagger-core/wiki) from a remote server, you can easily generate a server stub.  This
is an example of building a swagger-enabled Flask server.

This example uses the [Connexion](https://github.com/zalando/connexion) library on top of Flask.

## Requirements
Python 3.5.2+

## Usage
To run the server, please execute the following from the root directory:

```
pip3 install -r requirements.txt
python3 -m swagger_server
```

and open your browser to here:

```
http://localhost:8080/service-api/ui/
```

Your Swagger definition lives here:

```
http://localhost:8080/service-api/swagger.json
```

To launch the integration tests, use tox:
```
sudo pip install tox
tox
```

## Running with Docker

To run the server on a Docker container, please execute the following from the root directory:

```bash
# building the image
docker build -t swagger_server .

# starting up a container
docker run -p 8080:8080 swagger_server
```

## Docker repo
After a successful build on the `main` branch, this docker image is pushed to `leonkielstra/devops-lab2`.

```bash
# Pull docker image
docker pull leonkielstra/devops-lab2

# Run docker image
docker run -p 8080:8080 leonkielstra/devops-lab2
```

## Run Postman tests
```bash
# install newman
npm install newman@4.6.1

# Run postman tests, make sure you have the api server running
node_modules/.bin/newman run swagger_server/test/postman_collection.json -e swagger_server/test/postman_environment.json
```
