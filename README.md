# DevOpsified

Knowledge from the course DevOps Foundations: Your First Project on LinkedIn learning

## 1. Introduction

You are going to be moving a project from local to prod. It will use containers, integration tests, IaC (infrastructure
as a code) with Terraform, AWS, and Jenkins.
Your goal will be to embrace devops, with 100% automated deploys through CI.

## 2. Testing Locally with Docker

Everything about docker can be found on my other project [Docker Study](https://github.com/ErickBRAlessi/docker-study).
But you basically just need to install docker and having it working on bash. If you are using Mac you can use homebrew
to install it. With the command `brew cask install docker`.

Dockerfiles are manifest which describe the image that the container will run.
We will build our application over a nginx image [Docker Hub](https://hub.docker.com/_/nginx). Where I will be the
maintainer. And we will be coping the website and the nginx.conf to the image. Also, it should be exposed on port 80.

Now lets try to build our application `docker build -f ./2/Dockerfile --tag website:1.0.0 ./2`

Now lets run it mapping our port 1234 to the port 80 in container `docker run -p 1234:80 website:1.0.0`

Now we can access it on http://localhost:1234.

If you need to run multiple containers, the easiest way is using docker-compose. So let's create a docker-compose.yml.
The version says which version o the docker-compose it is written. Services are the applications that will be run. 

To run it use the command  `docker-compose -f ./2/docker-compose.yml up`

One can check the containers running: `docker ps` or `docker-compose -f ./2/docker-compose.yml down` 

Or to stop them and remove the network `docker-compose -f ./2/docker-compose.yml down`

*if you are in the folder of the docker-compose, you do not need to specify the path every time*





