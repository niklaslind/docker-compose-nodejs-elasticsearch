
# Docker-compose for elasticsearch with data volume and nodejs

Use [https://docs.docker.com/compose/](docker-compose) to start docker containers:

 - nodejs
 - elasticsearch
 - data container for elasticsearch


## Purpose

A simple demo project for docker-compose config for
nodejs+elasticsearch that we will use as base for other projects based
on nodejs+elasticsearch.

## Manage docker host with docker-machine (OSX)

Get docker host settings:

    eval "$(docker-machine env default)"

Check "default" machine with

    docker-machine ls

create new default host:

    docker-machine create -d virtualbox default

or just start the default host:

    docker-machine start default


## Manage dockers with docker-compose


List dockers, bring them up, down...

    docker-compose ps
    docker-compose up
    docker-compose down


## Access services (nodejs and elasticsearch)

Since we are using docker-machine to run the docker host on OSX we
need to use docker host ip:

    eval "$(docker-machine env default)"
    export DOCKER_HOST_IP=$(docker-machine ip default)

open web browser to elasticsearch:

    open http://$DOCKER_HOST_IP:9200
    
open web browser to nodejs:    
    
    open http://$DOCKER_HOST_IP:3000
    
   
