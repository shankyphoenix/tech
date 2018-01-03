# Docker Commands

## General Commands
> sudo docker start <puppetmaster>
> sudo docker exec -it <22aff7bb152b> bash
> docker kill $(docker ps -q)
> docker rm $(docker ps -a -q)
> docker rm $(docker images -q)
> docker container rename CONTAINER NEW_NAME

### pattern
> docker <container> <ps|exec|rm|ls|restart|start|stop|cp> 
> docker <run|build> 


### Run docker
sudo docker run -d --name=<any name> -p <host port number>:<container port number> -p 222:22 -p 33306:3306 -v <host port path>:<container port path>
>sudo docker run -td -p 8802:80 -v /var/www/html:/var/www/docker/bildhive/app bildhive

### Pull images locally
> sudo docker pull <docker image name>


### stop all docker container
  stop all containers: docker kill $(docker ps -q)
  remove all containers. docker rm $(docker ps -a -q)
  remove all docker images. docker rm $(docker images -q)

### copy from container
>sudo docker cp 22aff7bb152b:/var/www/orocrm /var/www/html/orocrm

### copy to container all files and floder to container
> docker cp /var/www/html/orocrm/orocrm/. 22aff7bb152b:/var/www/orocrm

### Create a docker machine and then create containers inside docker machine
```
  docker-machine create --driver=virtualbox <container-name> `create a docker machine in virtual box`
  docker-machine env <container-name> # set the docker machine to enu
  eval "$(docker-machine env <container-name>"
  docker run -d -p 8000:80 nginx #previous command set "env"
  docker-machine ip <container-name> #get the ip address of the virtual machine/docker machine
  docker-machine stop <container-name>
  docker-machine start <container-name>
```

### Run to update
>git diff --name-only --cached | while read line ; do  eval "sudo docker cp \`readlink -f $line\` 22aff7bb152b:/var/www/orocrm/$line";  done

## Run on docker machine and docker
```
docker-machine create --driver=virtualbox vbox-test1
docker-machine start shanky
docker-machine env shanky
eval $(docker-machine env shanky)
docker-machine ls
docker-machine ip shanky
```