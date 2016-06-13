
# Docker-compose for nodejs and elasticsearch with data volume

Use [docker-compose](https://docs.docker.com/compose/) to start docker containers:

 - nodejs
 - Kibana
 - elasticsearch
 - data container for elasticsearch


## Purpose

A simple demo project for docker-compose config for
nodejs+kibana+elasticsearch that we will use as base for other
projects based on nodejs+elasticsearch.


## Prereq

The stuff you need to get going:

    install [docker-machine](https://docs.docker.com/machine/) (OSX)
    install [docker-compose](https://docs.docker.com/compose/)
    git clone <this project>
        
Note: You do not need nodejs or elasticsearch installed on your host
machine. It's all installed in the docker containers.    
    

## Manage docker host with [docker-machine](https://docs.docker.com/machine/) (OSX)

Get docker host settings:

    eval "$(docker-machine env default)"

Check "default" machine with

    docker-machine ls

create new default host:

    docker-machine create -d virtualbox default

or just start the default host:

    docker-machine start default


## Manage dockers with docker-compose


Using [docker-compose config file](./docker-compose.yml). List dockers, bring them up, down...

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
    
    
open web browser to kibana:    
   
    open http://$DOCKER_HOST_IP:5601
